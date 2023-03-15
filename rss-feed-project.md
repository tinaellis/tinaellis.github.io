# Integrating a Google Alerts RSS Feed with a Static Website

In this post, I'll share my experience integrating a Google Alerts RSS feed into a static website hosted on GitHub Pages. I'll discuss the challenges I faced, the troubleshooting process, and how I leveraged AWS services to overcome these challenges.

<ul>
    <li>View the final result <a href="news">APT RSS Newsfeed</a></li>
</ul>

## Goal
My goal for this project was to use Google Alert's RSS feed on my website as a convenient and easily accessible way to monitor and stay informed on the latest threat intelligence and news.

## Challenges and Troubleshooting
### CORS Policy Error
The first challenge I encountered was a CORS (Cross-Origin Resource Sharing) policy error. My initial approach was to fetch the RSS feed directly from the Google Alerts URL, but this resulted in a CORS error, which prevented the feed from being displayed on the website. I discovered this issue while inspecting the website and checking the console tab for errors.

<strong>The console error looked like this with my info removed.</strong>
```
Access to fetch at 'https://www.google.com/alerts/feeds/blahblahblah' from origin 'https://yourwebsite.com' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
www.google.com/alerts/feeds/blahblahblah
```

I was unfamiliar with this policy error and after a few failed Google searches, I decided to ask ChatGPT for help. I copied the console errors directly into ChatGPT and explained what I was trying to do. Like magic, the chatbot knew exactly what the error was and how to fix it.

> The issue is caused by a CORS (Cross-Origin Resource Sharing) policy blocking the request. To resolve this, you can use a CORS proxy.

#### <em>Okay great, what's a CORS Proxy?</em>
As I probed ChatGPT to learn more about using a public proxy to solve my issue, I realized that there were significant security concerns with this approach. Instead I decided to go the more difficult route and set up a serverless function using AWS Lambda, which acted as a proxy to fetch the RSS feed on my behalf. This allowed me to control the CORS headers and ensure the website could fetch and display the feed correctly.

### AWS Lambda and API Gateway Configuration
Setting up the Lambda function and API Gateway involved several steps, including creating a Lambda function, configuring an API Gateway to invoke the Lambda function, and setting up CORS headers on the API Gateway. I had to ensure the Lambda function had the correct handler, runtime, and necessary permissions.

I also had to configure the API Gateway's CORS settings by adding appropriate Access-Control-Allow-Origin, Access-Control-Allow-Methods, and Access-Control-Allow-Headers headers to allow my website to interact with the API.

I have no shame telling you that this process was new to me and took several hours of Googling and asking ChatGPT for help. I appreciate that ChatGPT doesn't just provide you with the answer, but also tells you the "why". Here's a snippet from one of our converations:

<strong><em>When creating the integration in AWS, which HTTP method should I select?</em></strong>
> When creating the integration in AWS API Gateway, you should select the GET HTTP method. This is because the Lambda function is fetching the RSS feed using a GET request, and your website is also expected to make a GET request to the API Gateway URL to retrieve the feed data.

### Parsing and Displaying the RSS Feed
Just when I thought I was done, I encountered an issue where no items were being displayed on the website even though the raw XML data was being fetched correctly.

After exploring every AWS API setting I could think of, I discovered that the issue was with the Google Alerts feed itself, which didn't contain any items in its XML data.

Everything I read online said that you could use boolean logic to query multiple terms for your feed. Originally, I had wanted a newsfeed that was specific to Russian APTs and had put together the following query:
```
"russia" AND ("fin11" OR "temp.armageddon" OR "UNC4393" OR "coldriver" OR "sandworm" OR "fin7" OR "APT28" OR "APT29" OR "APT43" OR "Turla Group" OR "Energetic Bear" OR "FIN7" OR "FIN8" OR "Inception" OR "Dragonfly" OR "Advanced Persistent Threat" OR "APT" OR "hackers") 
```
<strong>As it turns out, the internet lies.</strong> Google was not having it, even when I simplified my search query. To resolve this, I adjusted the search terms used in the Google Alerts configuration to just search broadly for "Advanced Persistent Threats", which resulted in a populated RSS feed.

## Final Thoughts
Integrating a Google Alerts RSS feed into a static website presented several challenges, but with the help of ChatGPT, and AWS services like Lambda and API Gateway, I was able to create a serverless solution that fetched and displayed the RSS feed without running into CORS policy issues. This <a href="rss-feed-project">project</a> showcased the power of serverless architecture and demonstrated how it can be used to overcome limitations typically encountered when working with static websites.