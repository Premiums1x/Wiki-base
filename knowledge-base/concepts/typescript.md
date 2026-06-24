---
concept: typescript
entity_type: concept
aliases: []
sources: ["raw\\03-frontend-development\\frontend_roadmap.md"]
confidence: high
created_at: 2026-06-24T07:56:40Z
---

## Typescript

Typescript is a programming language that extends JavaScript by adding static types and other features to support large-scale applications. It javascript (RelExtends) the JavaScript syntax and builds on it by incorporating optional static types, interfaces, enums, and other language constructs that facilitate development in large and complex projects.

## How it works

In Typescript, variables, functions, and objects are annotated with types to provide type safety. This means that the compiler can check your code for type errors at compile time, which helps in catching bugs earlier. Types can be explicit or can be inferred from contexts. For example:

```typescript
let myName: string = "Alice";
```

Here, `myName` is explicitly typed as a `string`. Alternatively, Typescript can infer the type from the assignment if not explicitly stated.

Typescript also supports interfaces which can define a structure for the objects:

```typescript
interface Person {
  firstName: string;
  lastName: string;
}

let user: Person = { firstName: "Alice", lastName: "Smith" };
```

In this snippet, the `Person` interface defines a structure expected for any object used in its place. The `user` variable is annotated to indicate it conforms to the `Person` interface.

When compiled, Typescript code is translated into valid JavaScript, which can then be run on any platform that supports JavaScript. Types are optional and do not affect runtime behavior, thus making it easy to integrate with existing JavaScript codebases. To use Typescript, a Typescript compiler (tsc) performs the checking and conversion to JavaScript.

## Variants
Typescript is regularly updated with new features and improvements. Some key variants include:

- **Typescript 4.x**: This version is known for its support of newer JavaScript features like optional chaining and nullish coalescing.
- **Typescript with Flow**: Some developers integrate Facebook's Flow for static type checking alongside Typescript, though Flow is now less commonly used due to Typescript's broader adoption.

## Trade-offs
While Typescript offers significant benefits, there are trade-offs to consider:
- **Development Overhead**: The overhead of defining types can be seen as a burden, especially for small-scale or simple projects.
- **Learning Curve**: Adding types adds additional complexity and may require developers to adapt their approach.
- **Compile Time vs Runtime**: With Typescript, issues are caught at compile time, which means that runtime errors are reduced, but it also means that developers need access to a Typescript environment for development.

## See also
- typescript-and-eslint
- [[react]]