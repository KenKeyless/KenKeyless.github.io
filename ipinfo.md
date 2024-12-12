---
layout: page
permalink: /ipinfo/
title: ""
---
<div id="ip-details" class="small-text">
  <!-- IP details go here --> 
</div>

<script>
  // Function to fetch and display IP details from both APIs
  async function showIpDetails() {
      const ipDetails = document.getElementById('ip-details');
      
      let ipApiData = null;
      let ipApiComData = null;
      let ipApiError = false;
      let ipApiComError = false;

      // Try fetching data from ipapi.co
      try {
          const ipApiResponse = await fetch('https://ipapi.co/json/');
          if (ipApiResponse.ok) {
              ipApiData = await ipApiResponse.json();
          } else {
              ipApiError = true;
          }
      } catch (error) {
          ipApiError = true;
      }

      // Try fetching data from ip-api.com if the first API failed
      if (!ipApiData) {
          try {
              const ipApiComResponse = await fetch('http://ip-api.com/json/?fields=continent,country,regionName,city,district,timezone,isp,org,mobile,proxy,hosting,query');
              if (ipApiComResponse.ok) {
                  ipApiComData = await ipApiComResponse.json();
              } else {
                  ipApiComError = true;
              }
          } catch (error) {
              ipApiComError = true;
          }
      }

      // If both fail, fall back to a delayed fetch from ipapi.co
      if (!ipApiData && !ipApiComData) {
          setTimeout(async () => {
              try {
                  const fallbackResponse = await fetch('https://ipapi.co/json/');
                  if (fallbackResponse.ok) {
                      const data = await fallbackResponse.json();
                      ipDetails.innerHTML = `
                          <p><strong>IP Address:</strong> ${data.ip}</p>
                          <p><strong>Country:</strong> ${data.country_name}</p>
                          <p><strong>Timezone:</strong> ${data.timezone}</p>
                          <p><strong>Region:</strong> ${data.region}</p>
                          <p><strong>City:</strong> ${data.city}</p>
                          <p><strong>ISP:</strong> ${data.org}</p>
                          <p><strong>Browser:</strong> ${navigator.userAgent}</p>
                      `;
                  } else {
                      ipDetails.innerHTML = '<p>Failed to retrieve IP details from fallback source.</p>';
                  }
              } catch (error) {
                  ipDetails.innerHTML = '<p>Failed to fetch fallback IP details.</p>';
              }
          }, 3000); // 3-second delay for fallback
      } else {
          // If ipApiData is available, use that data
          const ipData = ipApiData || ipApiComData;
          
          ipDetails.innerHTML = `
              <p><strong>ISP:</strong> ${ipData.isp || 'Fetch Failed'}</p>
              <p><strong>IP Address:</strong> ${ipData.query || ipData.ip || 'Fetch Failed'}</p>
              <p><strong>Continent:</strong> ${ipData.continent || 'Fetch Failed'}</p>
              <p><strong>Country:</strong> ${ipData.country || ipData.country_name || 'Fetch Failed'}</p>
              <p><strong>Timezone:</strong> ${ipData.timezone || 'Fetch Failed'}</p>
              <p><strong>Region:</strong> ${ipData.regionName || 'Fetch Failed'}</p>
              <p><strong>City:</strong> ${ipData.city || 'Fetch Failed'}</p>
              <p><strong>Mobile:</strong> ${ipData.mobile ? 'Yes' : 'No'}</p>
              <p><strong>Proxy:</strong> ${ipData.proxy ? 'Yes' : 'No'}</p>
              <p><strong>Hosting:</strong> ${ipData.hosting ? 'Yes' : 'No'}</p>
              <p><strong>Browser:</strong> ${navigator.userAgent}</p>
          `;
      }
  }

  // Call the function when the page loads
  window.addEventListener('load', showIpDetails);
</script>
