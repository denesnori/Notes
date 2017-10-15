### URLs

get the current url
```
window.location.href
document.URL
```

```
<protocol>//<hostname>:<port>/<pathname><search><hash>
```
- protocol: protocol used to access the resource. HTTP (without SSL), HTTPS (with SSL)
- hostname: specifies the host that owns the resource. eg.www.stackoverflow.com
- port: used to recognize a specific process to which an internet or other network message is forwarded when arrives at the server.
- pathname: specifies what the clients want to access within the host
- search: string of information
- query: anchor part of the url, includes the #


### window.location
```
window.location.hash // hash part of the url
window.location.host // hostname and port of url
window.location.hostname // hostname of url
widow.location.href // return the entire url
window.location.pathname // path
window.location.port //port
window.location.protocol // protocol
window.location.search // query
```
