What is SNI (Server Name Indication)?

SNI is somewhat like mailing a package to an apartment building instead of to a house. When mailing something to someone's house, the street address alone is enough to get the package to the right person. But when a package goes to an apartment building, it needs the apartment number in addition to the street address; otherwise, the package might not go to the right person or might not be delivered at all.

Many web servers are more like apartment buildings than houses: They host several domain names, and so the IP address alone is not enough to indicate which domain a user is trying to reach. This can result in the server showing the wrong SSL certificate, which prevents or terminates an HTTPS connection – just like a package can't be delivered to an address if the correct person doesn't sign for it.

When multiple websites are hosted on one server and share a single IP address, and each website has its own SSL certificate, the server may not know which SSL certificate to show when a client device tries to securely connect to one of the websites. This is because the SSL/TLS handshake occurs before the client device indicates over HTTP which website it's connecting to.

Server Name Indication (SNI) is designed to solve this problem. SNI is an extension for the TLS protocol (formerly known as the SSL protocol), which is used in HTTPS. It's included in the TLS/SSL handshake process in order to ensure that client devices are able to see the correct SSL certificate for the website they are trying to reach. The extension makes it possible to specify the hostname, or domain name, of the website during the TLS handshake, instead of when the HTTP connection opens after the handshake.

More simply put, SNI makes it possible for a user device to open a secure connection with https://www.example.com even if that website is hosted in the same place (same IP address) as https://www.something.com, https://www.another-website.com, and https://www.example.io.

SNI prevents what's known as a "common name mismatch error": when a client (user) device reaches the right IP address for a website, but the name on the SSL certificate doesn't match the name of the website. Often this kind of error results in a "Your connection is not private" error message in the user's browser.

SNI was added as an extension to TLS/SSL in 2003; it was not originally a part of the protocol. Almost all browsers, operating systems, and web servers support it, with the exception of some of the very oldest browsers and operating systems that are still in use.

ref: https://www.cloudflare.com/learning/ssl/what-is-sni/
