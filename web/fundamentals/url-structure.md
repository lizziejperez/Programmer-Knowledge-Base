# URL Structure

A URL (Uniform Resource Locator) identifies the location of a resource on the internet.

Example:
```
https://example.com:443/item?id=3#section
```

## Components

### 1. Protocol (Scheme)
```
https
```

Common protocols:
- http
- https
- ftp
- file

### 2. Domain Name
```
example.com
```

Maps to an IP address via DNS.

### 3. Port (Optional)
```
:443
```

Common ports:
- 80 → HTTP
- 443 → HTTPS

### 4. Path
```
/item
```

Specifies resource location on server.

### 5. Query Parameters
```
?id=3
```

Used to **send additional data**.

Format:
```
?key=value&key2=value2
```

### 6. Fragment (Anchor)
```
#section
```

Used to navigate within a page.

## Summary Structure
```
protocol://domain:port/path?query#fragment
```