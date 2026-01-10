Date: 2025-06-23
Tags: [[security]]

Some modern browser has features with cookies like:
- You can define a cookie as ```HttpOnly``` making it only available to send in http requests, avoiding things like ```localStorage.getItem('accessToken')``` 
- Cross-Site Request Forgery (CSRF) can happen, this occurs when malicious site refers itself as the original in the request, with ```SameSite=strict``` flag, cookies are only available to be sent in that particular DNS.

Also browser attaches the cookies automatically to each request in that domain.
