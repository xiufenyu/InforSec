What is X-Forwarded-For?
The "X-Forwarded-For" (XFF) header is a standard HTTP header that is used to identify the originating IP address of a client connecting to a web server through a proxy or load balancer.

When a client sends a request to a server through a proxy, the server receives the request from the proxy IP address rather than the client's IP address. The XFF header is used by the proxy to pass the client's IP address along to the server in the HTTP request headers.

The XFF header can contain a comma-separated list of IP addresses, where the first IP address is the original client IP address, followed by the IP addresses of any subsequent proxies or load balancers that the request passed through. This allows the server to identify the true client IP address and determine the client's location or other relevant information.

However, it's worth noting that the use of XFF header is optional and some proxies or load balancers may not add it to the HTTP request headers.

## Security and privacy concerns

This header, by design, exposes privacy-sensitive information, such as the IP address of the client. Therefore the user's privacy must be kept in mind when deploying this header.

The X-Forwarded-For header is untrustworthy when no trusted reverse proxy (e.g., a load balancer) is between the client and server. If the client and all proxies are benign and well-behaved, then the list of IP addresses in the header has the meaning described in the Directives section. 

But if there's a risk the client or any proxy is malicious or misconfigured, then it's possible any part (or the entirety) of the header may have been spoofed (and may not be a list or contain IP addresses at all). Any security-related use of X-Forwarded-For (such as for rate limiting or IP-based access control) must only use IP addresses added by a trusted proxy. Using untrustworthy values can result in rate-limiter avoidance, access-control bypass, memory exhaustion, or other negative security or availability consequences.