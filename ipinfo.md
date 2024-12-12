---
layout: page
permalink: /ipinfo/
title: ""
---
<div id="ip-details" class="small-text">
  <!-- IP details go here -->
</div>

<script>
  // Function to fetch IP details from APIs  
async function fetchIpDetails() {  
  // List of API URLs to fetch IP details from  
  const apiUrls = [  
   'https://ipapi.co/json/', // Primary API  
   'http://ip-api.com/json/?fields=continent,country,regionName,city,district,timezone,isp,org,mobile,proxy,hosting,query' // Fallback API  
  ];  
  const maxRetries = 3; // Maximum number of retries  
  const retryDelay = 1000; // Delay between retries (1 second)  
  
  let ipData = null; // Initialize IP data variable  
  let retries = 0; // Initialize retry counter  
  
  // Loop until IP data is fetched or maximum retries are reached  
  while (!ipData && retries < maxRetries) {  
   try {  
    // Fetch IP data from API  
    const response = await fetch(apiUrls[retries % apiUrls.length]);  
    if (response.ok) {  
      // If response is OK, parse JSON data  
      ipData = await response.json();  
    } else {  
      // If response is not OK, increment retry counter and wait for retry delay  
      retries++;  
      await new Promise(resolve => setTimeout(resolve, retryDelay));  
    }  
   } catch (error) {  
    // If error occurs, increment retry counter and wait for retry delay  
    retries++;  
    await new Promise(resolve => setTimeout(resolve, retryDelay));  
   }  
  }  
  
  // Return fetched IP data  
  return ipData;  
}  
  
// Function to create HTML string for IP details  
function createIpDetailsHtml(ipData) {  
  // If IP data is null, return error message  
  if (!ipData) {  
   return '<p>Failed to retrieve IP details.</p>';  
  }  
  
  // Create HTML string for IP details  
  return `  
   <p><strong>ISP:</strong> ${ipData.org || ipData.isp || 'Failed Request'}</p> <!-- ISP name -->  
   <p><strong>IP Address:</strong> ${ipData.query || ipData.ip || 'Failed Request'}</p> <!-- IP address -->  
   <p><strong>Country:</strong> ${ipData.country || ipData.country_name || 'Failed Request'}</p> <!-- Country name -->  
   <p><strong>Timezone:</strong> ${ipData.timezone || 'Failed Request'}</p> <!-- Timezone -->  
   <p><strong>Region:</strong> ${ipData.regionName || ipData.region || 'Failed Request'}</p> <!-- Region name -->  
   <p><strong>City:</strong> ${ipData.city || 'Failed Request'}</p> <!-- City name -->  
   <p><strong>Mobile:</strong> ${ipData.mobile === 'yes' ? 'Yes' : (ipData.mobile ? 'No' : 'No')}</p> <!-- Mobile status -->  
   <p><strong>Proxy:</strong> ${ipData.proxy === 'yes' ? 'Yes' : (ipData.proxy ? 'No' : 'No')}</p> <!-- Proxy status -->  
   <p><strong>Hosting:</strong> ${ipData.hosting === 'yes' ? 'Yes' : (ipData.hosting ? 'No' : 'No')}</p> <!-- Hosting status -->  
   <p><strong>Browser:</strong> ${navigator.userAgent}</p> <!-- Browser user agent -->  
  `;  
}  
  
// Function to show IP details  
async function showIpDetails() {  
  // Get IP details element  
  const ipDetails = document.getElementById('ip-details');  
  
  // Fetch IP details  
  const ipData = await fetchIpDetails();  
  
  // Create HTML string for IP details  
  const html = createIpDetailsHtml(ipData);  
  
  // Set IP details HTML  
  ipDetails.innerHTML = html;  
}  
  
// Add event listener to window load event  
window.addEventListener('load', showIpDetails);


</script>
