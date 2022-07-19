# REST vs SDK vs tRPC vs GraphQ

### REST 

#### Pros

- The most basic approach
- Authentication layer is typically REST so won't require a special treatment here.
- Ecosystem of testing, QA, editor/IDE plugins etc. tools like Postman.
- Caching is a solved problem. Check tools like [React-Query](https://tanstack.com/query/v3/) or [SWR](https://swr.vercel.app/).

#### Cons

- Any non-trivial API will require to write your own SDK.
- API is untyped, Swagger etc. "types" are just conventions that can be violated.
- No realtime primitives. 

### SDK (meaning official, open-source distributions) 

#### Pros

- Most often is built on top of REST so REST pros can apply.
- Easier to use than REST.

#### Cons

- Caching is typically an unsolved question. :fearful:
- Bundle size increase. Some SDKs are quite heavy.
- Typically comes with realtime primitives.

### tRPC (and other similar tools)

https://trpc.io/
 
#### Pros

- ...All benefits of REST
- Statically typed API

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
