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
  const apiUrls = [  
   'https://ipapi.co/json/',  
   'http://ip-api.com/json/?fields=continent,country,regionName,city,district,timezone,isp,org,mobile,proxy,hosting,query'  
  ];  
  const maxRetries = 3;  
  const retryDelay = 1000; // 1 second  
  
  let ipData = null;  
  let retries = 0;  
  
  while (!ipData && retries < maxRetries) {  
   try {  
    const response = await fetch(apiUrls[retries % apiUrls.length]);  
    if (response.ok) {  
      ipData = await response.json();  
    } else {  
      retries++;  
      await new Promise(resolve => setTimeout(resolve, retryDelay));  
    }  
   } catch (error) {  
    retries++;  
    await new Promise(resolve => setTimeout(resolve, retryDelay));  
   }  
  }  
  
  if (!ipData) {  
   ipDetails.innerHTML = '<p>Failed to retrieve IP details.</p>';  
   return;  
  }  
  
  ipDetails.innerHTML = `  
   <p><strong>ISP:</strong> ${ipData.org || ipData.isp || 'Failed Request'}</p>  
   <p><strong>IP Address:</strong> ${ipData.query || ipData.ip || 'Failed Request'}</p>  
   <p><strong>Continent:</strong> ${ipData.continent || 'Failed Request'}</p>  
   <p><strong>Country:</strong> ${ipData.country || ipData.country_name || 'Failed Request'}</p>  
   <p><strong>Timezone:</strong> ${ipData.timezone || 'Failed Request'}</p>  
   <p><strong>Region:</strong> ${ipData.regionName || ipData.region || 'Failed Request'}</p>  
   <p><strong>City:</strong> ${ipData.city || 'Failed Request'}</p>  
   <p><strong>Mobile:</strong> ${ipData.mobile === 'yes' ? 'Yes' : (ipData.mobile ? 'No' : 'No')}</p>  
   <p><strong>Proxy:</strong> ${ipData.proxy === 'yes' ? 'Yes' : (ipData.proxy ? 'No' : 'No')}</p>  
   <p><strong>Hosting:</strong> ${ipData.hosting === 'yes' ? 'Yes' : (ipData.hosting ? 'No' : 'No')}</p>  
   <p><strong>Browser:</strong> ${navigator.userAgent}</p>  
  `;  
}  
  
window.addEventListener('load', showIpDetails);

</script>
