---
concept: localstorage
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T07:57:16Z
---

## Definition
Localstorage is a property of the web browser's Window object that provides a way to store key-value pairs in the user’s browser. Unlike cookies, LocalStorage data is not included in the HTTP requests sent to the server auth. This makes it a preferred choice for applications where persistent storage of user data is required without involving the server in every data access and modification operation.

## How it works
Localstorage provides an API to store data with the `setItem` method and retrieve it with the `getItem` method. The data stored in localstorage is string-based, thus if one wishes to store more complex data types, they need to be serialized into strings before storing and deserialized after retrieval. The data persists across sessions and is accessible from JavaScript on the same origin (protocol, hostname, port) as the Window object which set it. However, since localstorage is persisted on the user's machine, it can be cleared by the user or manually deleted as a part of their web browsing settings. Localstorage does not have any built-in security features, meaning that the stored data can be accessed by any script running in the same origin context cryptography.

### Example Usage
Localstorage can be used to store user authentication tokens after the user logs in. For instance, in an application that uses JSON Web Tokens (JWT) for authentication, the JWT string can be stored in localstorage for subsequent requests. This is commonly implemented by setting the token upon successful login and then including it in the `Authorization` header of each HTTP request to identify the user. This process relies on the framework or library that handles the API requests to correctly include the token in each request:

```javascript
localStorage.setItem('token', 'your-jwt-token-here');
axios.get('/api/protected', {
  headers: {
    'Authorization': `Bearer ${localStorage.getItem('token')}`
  }
});
```

## Variants
There are several ways to store data in a web browser, and the choice of mechanism often depends on the application requirements. **Cookies** are another popular storage mechanism that has to be sent with every HTTP request to the server, whereas **SessionStorage** is a browser storage similar to Localstorage but data is only available for the window or tab that created it, and gets cleared when the tab or window is closed. **IndexedDB** provides high-performance local storage and is the preferred option when dealing with large amounts of structured data, though it requires more complex data handling logic.

## Trade-offs
Using Localstorage for storing data comes with its trade-offs. While it provides a simple and session-less way to store data, it is vulnerable to overwriting by any other script with the same origin. Moreover, it does not offer any expiration policies by default, which means data can occupy disk space indefinitely. In contrast, Cookies have built-in mechanisms for setting an expiration time, but they require network traffic on every request, unlike Localstorage which is accessed from the client-side storage without server involvement cryptography.

Localstorage's reliance on the JavaScript environment can introduce security concerns if not managed correctly, making it important to ensure that sensitive information stored there is properly handled and secured cryptography.

## See also
[[cors]], api, [[jwt]]