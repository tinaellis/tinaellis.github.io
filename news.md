---
layout: default
title: Google Alerts Feed
---
<div id="google-alerts-feed"></div>

<script>
  const googleAlertsFeedUrl = 'https://s5tvejj1hh.execute-api.us-east-1.amazonaws.com/therealrss3/rssFeedProxy';
  const googleAlertsFeedContainer = document.getElementById('google-alerts-feed');
  
  fetch(googleAlertsFeedUrl)
    .then(response => response.text())
    .then(data => {
      console.log('Raw data:', data); // Log raw data
      const parser = new DOMParser();
      const xml = parser.parseFromString(data, 'application/xml');
      const items = xml.querySelectorAll('entry');

      console.log('Parsed items:', items); // Log parsed items

      let html = '';
      items.forEach(item => {
        html += `
          <h2>${item.querySelector('title').textContent}</h2>
          <p>${item.querySelector('content').textContent}</p>
          <a href="${item.querySelector('link').getAttribute('href')}" target="_blank">Read More</a>
        `;
      });

      googleAlertsFeedContainer.innerHTML = html;
    })
    .catch(error => {
      console.error('Error fetching or parsing the data:', error); // Log any errors
    });
</script>