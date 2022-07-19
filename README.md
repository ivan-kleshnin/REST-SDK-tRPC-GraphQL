# REST vs SDK vs tRPC vs GraphQL

WIP: mostly client-side concerns so far...

### REST 

#### Pros

- The most basic approach.
- Authentication layer is typically REST so won't require a special treatment here.
- Ecosystem of testing, QA, editor/IDE plugins etc. tools like Postman.
- Caching is a solved problem. Check tools like [React-Query](https://tanstack.com/query/v3/) or [SWR](https://swr.vercel.app/).
- BE and FE are decoupled: can be written in different languages.

#### Cons

- Any non-trivial API will require to write your own SDK.
- API is untyped, Swagger etc. "types" are just conventions that can be violated.
- No realtime primitives. 

### SDK (meaning official, open-source distributions) 

#### Pros

- ...Most REST benefits (if built on top of REST which is typically the case).
- Easier to use than REST – saves time to write your own SDK and/or support low-level code.
- Typically comes with realtime primitives.

#### Cons

- Can be incompatible with caching layer (if SDK wraps promises with custom datatypes)
- Bundle size increase. Some SDKs are quite heavy.

### tRPC (and other similar tools)

https://trpc.io/
 
#### Pros

- ...All benefits of REST.
- Statically typed API.

#### Cons

- Requires BE and FE to be written in the same statically typed language (e.g TypeScript). :exclamation:

### GraphQL

#### Pros

- Statically typed API.
- Growing ecosystem.
- Realtime support with Subscriptions.
- Static types allow smarter cache invalidation mechanics.

#### Cons

- The most complex approach.
- Type duplication concern: which types are the source of truth – TypeScript or GraphQL.
- Auth layer logic is often REST and requires its own caching, etc. babysitting tasks.
