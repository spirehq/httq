# What is HTTQ?

HTTQ is a specialized task queue for API integrations and µicroservices. It allows you to queue HTTP requests. It also provides built-in rate limiting and retry mechanisms.

In short, HTTQ helps you build reliable software faster.

# The story

Sam is a developer. He wants to download the data from Trello API. For that, he needs to make 500 requests. But Trello API has a rate limit of 300 requests per 10 seconds, so he can't issue 500 requests at once, in parallel. Instead, Sam puts 500 requests on a queue, with a rate limit matching Trello's. HTTQ sends requests on Sam's behalf. It retries failed requests, and saves successful responses. When all requests succeed, HTTQ builds a single "response bucket", and delivers it to Sam's endpoint.

# How it works

1. 
