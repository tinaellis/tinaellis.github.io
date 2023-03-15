---
layout: default
title: APT News
---
## Advanced Persistent Threat (APT) Newsfeed
<div id="google-alerts-feed"></div>

<script>
  const googleAlertsFeedUrl = 'https://s5tvejj1hh.execute-api.us-east-1.amazonaws.com/therealrss3/rssFeedProxy';
  const googleAlertsFeedContainer = document.getElementById('google-alerts-feed');
  
  fetch(googleAlertsFeedUrl)
    .then(response => response.text())
    .then(data => {
      const parser = new DOMParser();
      const xml = parser.parseFromString(data, 'application/xml');
      const items = xml.querySelectorAll('entry');
      
      let html = '';
      items.forEach(item => {
        const date = new Date(item.querySelector('published').textContent).toLocaleDateString();
        html += `
          <h2>${item.querySelector('title').textContent}</h2>
          <p>${item.querySelector('content').textContent}</p>
          <p>Published on: ${date}</p>
          <a href="${item.querySelector('link').getAttribute('href')}" target="_blank">Read More</a>
        `;
      });
      
      googleAlertsFeedContainer.innerHTML = html;
    });
</script>