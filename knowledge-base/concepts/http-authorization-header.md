---
concept: http-authorization-header
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T09:47:07Z
---

## Definition
The `Http Authorization Header` is a part of the `HTTP` request sent to a server for authentication purposes. It is commonly used with the `JWT` json-web-token, leveraging its capability for secure, stateless authentication to identify and verify the identity of the user attempting to access a resource. 

## How it works
This header works by embedding a token, typically a `JWT` json-web-token, within the `Authorization` field of the `HTTP` request. The basic structure involves a user first logging into the system where the server generates an authentication token if such credentials are valid. This token is then saved by the client, commonly in `localStorage` or `Cookie`. On every request to the server, the client includes this token in the `Authorization` header of the `HTTP` request:
```http
Authorization: Bearer <your-jwt-token>
```
Upon receipt of the request, the server examines the token within the `Authorization Header`, validates its authenticity, and uses it to determine the identity of the user and the access rights afforded to that user. If the `JWT` is deemed invalid or has expired, the server typically responds with an `HTTP 401 Unauthorized` status.

In scenarios involving `CORS` cross-origin-resource-sharing, where cross-origin requests might be restricted, a correctly configured `Authorization Header` plays a crucial role in establishing mutual trust through authentication.

## Variants
While `JWT` is one of the most prevalent ways to populate the `Authorization Header`, there are other methods and alternatives. For instance, `OAuth` tokens are also frequently employed, extending the functionality with finer-grained access controls. Moreover, the `Basic Auth` method authenticates using a simple username and password combination, which contrasts with the token-based approach of a `JWT`.

## Trade-offs
The use of `Authorization Header` comes with trade-offs. On the one hand, the header provides a flexible means of user authentication and is widely supported by web frameworks and libraries, json-web-token builds on it by enhancing security through signing and encryption of tokens. On the other hand, the reliance on tokens in headers can pose significant security risks if not properly managed, such as through the loss or theft of a token leading to unauthorized access. Additionally, the handling of tokens can become complex, particularly in single-page applications, due to strategies such as renewing tokens without user interaction.

## See also
The concept of `Http Authorization Header` significantly trades off with `CORS` cross-origin-resource-sharing in contexts where authenticating cross-origin requests is essential. Similarly, it contradicts the use of traditional cookie-based sessions in stateful authentication schemes.