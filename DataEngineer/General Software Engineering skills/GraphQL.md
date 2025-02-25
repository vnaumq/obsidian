[[General Software Engineering skills]]

GraphQL is a **query language** and a **server-side runtime** (typically served over HTTP).

**GraphQL is a language for querying data.** Unlike most query languages (such as SQL), you _don’t_ use GraphQL to query a particular type of data store (such as a MySQL database). Instead, **you use GraphQL to query data from any number of different sources.**
![[graphql.png]]
### Served over HTTP

GraphQL is typically served over HTTP. This means operations are just plain ol’ strings, and we don’t need a special tool to query data from a GraphQL server.

## A brief history

Facebook created GraphQL in 2012. They needed a better data-fetching approach that they could use across the entirety of the company’s products and services. They also wanted something that was understandable by developers, designers, as well as non-technical folk. After using it internally for some time, Facebook

## Key features of GraphQL

### [](https://www.apollographql.com/blog/what-is-graphql-introduction#performance)Performance

**Prevents over-fetching:** In traditional approaches like REST, you often end up _over-fetching_ — asking for more data than you need. With GraphQL, you can ask for exactly what you need. The benefit is reduced bandwidth, which may be especially important on mobile and low-energy devices.

**Prevents under-fetching (multiple round-trips):** The other end of the fetching problem in REST is _not_ getting all the data you need in a single round-trip. Consider fetching your friends list in a social media app and needing to batch individual queries to get each friend’s profile picture. GraphQL helps solve this problem.

### [](https://www.apollographql.com/blog/what-is-graphql-introduction#developer-experience)Developer experience

**Hierarchical & declarative:** GraphQL data is inherently _graphical_ and declarative. This makes your queries easier to understand and your data easier to work with. By nesting, we can ask for related data, keeping queries cohesive, and spending zero time stitching together multiple responses like we sometimes have to do with REST.

**Strongly typed (stable API):** GraphQL is strongly typed. This means a more stable API with fewer bugs in development and introduces the possibility of more intelligent tooling.

**GraphQL versioning:** GraphQL favors the notion of a single, incrementally developed graph. You can give deprecation hints when you add, remove, and change fields on your existing graph. Compare this to the coarse-grained approach to versioning in a REST context with version numbers across an entire API.

## Conclusion

- GraphQL is a query language and a server runtime that typically runs over HTTP
- It was designed to be more efficient, performant, and provide a better developer experience for working with data in a client-server architecture
- GraphQL adoption has significantly grown since it was first open-sourced and it doesn’t look like it’s going anywhere soon.