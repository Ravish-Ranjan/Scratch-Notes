# Userfacet Interview Preparation

> **Purpose:** A resume-specific interview question bank with strong,  
> truthful answer frameworks for the next Userfacet rounds.
>
> **Prepared from:** Ravish Ranjan's submitted resume, the 12 Userfacet
> interview experiences/questions supplied in this conversation, and a
> current review of Userfacet's official website for the "Why
> Userfacet?" section.
>
> **Important:** The answers are deliberately written to stay within
> what the resume supports. Do not claim an implementation, metric,
> technology, or responsibility that you cannot explain in detail.

---

# 0. How to Use This Guide

Userfacet interviews in the supplied experiences repeatedly follow this
pattern:

1. Introduction
2. Resume/project deep dive
3. DSA or coding
4. Core CS fundamentals
5. Role-specific stack
6. Scenario/design questions
7. CEO/CTO technical + behavioral discussion
8. COO/HR behavioral discussion

The interviewers frequently reopen projects/code and ask the candidate
to explain or implement a feature. Therefore, **project depth is as
important as memorizing fundamentals**.

### Answering rule

For technical questions:

> **Definition → Why it matters → Example → Trade-off**

For project questions:

> **Problem → Your decision → Implementation → Trade-off → Result**

For behavioral questions:

> **Claim → Concrete example → What you learned → How it affects your
> work now**

---

# 1. Your Resume: What the Interviewer Will Notice

Your resume gives the interviewer several obvious paths:

### Strongest interview hooks

- Full-stack internship
- Accessibility/Lighthouse 90+ 
  - first contentful paint
  - largest contentful paint
  - total blocking time
  - speed index
  - cumulative layout shift
  - timt to interactive
- Leadership of 7+ events / 10--12 people
- Next.js
- Nextjs routing
  - simple
  - nested
  - dynamic
  - catch all
  - optional catch all
  - grouped
  - parallel
  - api/route
  - intercepting route
- Node.js / Express.js
- Socket.IO
- MongoDB / PostgreSQL / Prisma / Mongoose / MySQL / Redis
- Docker / Git / GitHub / Linux
- OAuth
- HugnLove Crochet
- Encode QR API
- Redis caching and 70% response-time reduction
- Streaming QR images directly
- NPM cart package with zero peer dependencies
- Dual-storage support
- Open-source PR
- Client-facing requirements gathering
- C/C++/Python/Java
- OS/DSA/DBMS/OOP coursework

**Expect questions to start from the resume and then branch outward.**

---

# 2. The 60-Second Introduction

## Q1. Tell me about yourself.

### Best answer

> I'm Ravish Ranjan, currently pursuing my MCA at the University of
> Delhi, after completing my Bachelor's in Computer Science from Delhi
> University.
>
> I primarily work around full-stack web development, with a stronger
> interest in backend and product engineering. I have worked with
> technologies such as Next.js, Node.js, Express, React, MongoDB,
> PostgreSQL, Redis and Docker.
>
> During my internship at Ram Lal Anand College, I built accessible and
> responsive websites for faculty members and worked on improving their
> accessibility scores. Outside that, I have built projects like
> HugnLove Crochet, where I worked end-to-end with a client, and Encode,
> where I built a QR-code generation API and used Redis caching to
> improve response time.
>
> I have also built an NPM cart package and contributed to an
> open-source project, which helped me understand software development
> beyond just building applications for myself.
>
> At this stage, I'm looking for an environment where I can work on real
> products, take ownership of problems, and grow as an engineer.

### Follow-ups to expect

- Why backend?
- Why full-stack?
- Which project are you most proud of?
- What exactly did you do in your internship?
- What is your strongest technology?
- Why Userfacet?
- Why should we hire you?

---

# 3. Resume Cross-Examination

## Q2. Walk me through your resume.

### Best answer

> I would divide my experience into three parts: professional
> experience, personal engineering projects, and additional technical
> work.
>
> Professionally, I worked as a full-stack web development intern at Ram
> Lal Anand College, where I built responsive and accessible websites
> for faculty members.
>
> My main personal projects demonstrate different parts of engineering.
> HugnLove Crochet involved client communication, requirements
> gathering, Next.js, Supabase, authentication, CRUD APIs and image
> handling. Encode focused more on backend API design, QR-code
> generation, Redis caching and streaming responses. My cart package was
> more library-oriented, where I focused on reusable functionality and
> integration.
>
> I also have an open-source contribution, where I worked with
> maintainers through code review and got the PR merged.
>
> Academically, my coursework covers OS, DSA, DBMS and OOP, which gives
> me the fundamentals behind the technologies I use.

---

# 4. Questions About Your Internship

## Q3. What did you do during your internship?

### Best answer

> I worked on full-stack web development, primarily building responsive
> and accessible resume websites for faculty members at Ram Lal Anand
> College.
>
> One of the important aspects was accessibility. I focused on semantic
> structure, responsive behavior and other accessibility-related
> improvements, and the sites reached 90+ Lighthouse accessibility
> scores.
>
> The experience also taught me that building a website isn't only about
> making the UI look correct. It has to work across devices, be usable
> by different users, and be maintainable.

## Q4. What does accessibility mean to you?

> Accessibility means designing and developing an application so that
> people with different abilities can use it effectively.
>
> Technically, that includes semantic HTML, proper labels, keyboard
> navigation, meaningful alt text, sufficient contrast, focus states and
> avoiding interactions that depend only on a mouse.
>
> I think accessibility should be considered during development rather
> than added as a final checklist.

## Q5. What is Lighthouse?

> Lighthouse is a tool that audits web pages across areas such as
> performance, accessibility, best practices and SEO.
>
> In my internship, I specifically focused on the accessibility score. I
> would use the audit to identify issues, fix them, and rerun the audit
> to verify the improvement.

## Q6. How did you achieve 90+ accessibility?

> I focused on the issues identified by the accessibility audit and
> improved the underlying HTML and UI implementation rather than trying
> to optimize only the score.
>
> That included semantic HTML, accessible controls, appropriate labels
> and alternative text, keyboard usability, and other issues reported by
> the audit.
>
> The important part was treating the score as feedback about actual
> usability rather than as the objective itself.

## Q7. What was the hardest part of the internship?

> The challenge was balancing the visual requirements with
> responsiveness and accessibility. A design that looks correct visually
> can still have poor keyboard navigation, semantics or mobile behavior.
>
> It taught me to evaluate a UI from more than one perspective: visual
> appearance, responsiveness, accessibility and maintainability.

---

# 5. Leadership / Secretary Experience

## Q8. You were a secretary. What exactly did you do?

> I was involved in organizing and coordinating society events, working
> with a team of around 10--12 people. My responsibilities included
> coordination, technical problem solving, team management and helping
> with event setup.
>
> The experience was useful because I had to make decisions under time
> constraints and coordinate people with different responsibilities
> rather than doing everything myself.

## Q9. You claim setup time was reduced by 70+%. How?

> The reduction came from improving the way the event setup was
> organized and coordinated. Instead of treating each task
> independently, we streamlined responsibilities and solved recurring
> technical and setup issues more systematically.
>
> I would be happy to explain the exact workflow I used, because the
> important lesson for me was that process optimization is often about
> removing repeated manual work and ambiguity rather than simply working
> faster.

> **Warning:** If asked for exact before/after numbers, use only the
> numbers you can substantiate.

## Q10. What did you learn from managing 10--12 people?

> I learned that delegation is more effective than trying to control
> every task myself. I also learned to communicate expectations clearly
> and identify blockers early.
>
> In technical projects, I apply the same principle: define ownership,
> communicate interfaces clearly, and surface problems before they
> become larger blockers.

## Q11. What if a teammate is not cooperating?

> I would first try to understand whether the issue is lack of clarity,
> disagreement, workload, or something personal. I would discuss the
> specific task and expected outcome rather than making it personal.
>
> If the problem continues and affects the project, I would communicate
> the blocker to the appropriate lead with facts and possible solutions.
> My goal would be to solve the project problem rather than win an
> argument.

---

# 6. HugnLove Crochet --- Highest Priority Project

## Q12. Explain HugnLove Crochet.

### Best answer

> HugnLove Crochet is a portfolio/showcase website I built for a crochet
> business. I worked directly with the client, so the project included
> requirements gathering as well as development and deployment.
>
> I used Next.js and TypeScript on the application side and Supabase for
> backend/database functionality. I implemented an admin panel with
> JWT-based authentication, CRUD APIs for categories, reviews and site
> configuration, and an image upload and thumbnail pipeline for the
> gallery.
>
> The project was useful because it exposed me to the complete
> lifecycle: understanding requirements, designing the implementation,
> building it, handling content management, and deploying it.

## Q13. Why Next.js?

> I chose Next.js because it provides a structured React framework with
> routing, server-side capabilities and a production-oriented
> application structure.
>
> For a client-facing website, I also value the ability to choose
> between server-rendered and client-rendered behavior depending on the
> page and requirement.
>
> I would not say Next.js is universally better than React. React is the
> UI library, while Next.js provides a broader application framework
> around React.

## Q14. Why TypeScript?

> TypeScript adds static typing on top of JavaScript. It helps catch
> many errors during development, improves editor support, and makes
> larger codebases easier to understand.
>
> For example, if an API returns a particular object shape, defining
> that shape makes it harder to accidentally access a property that
> doesn't exist.
>
> The trade-off is additional type definitions and a compilation step,
> but for a maintainable application I generally consider that
> worthwhile.

## Q15. Why Supabase?

> I used Supabase because I wanted managed backend capabilities without
> building every piece of infrastructure from scratch. It provides
> PostgreSQL-based data storage and backend services.
>
> For this project, it allowed me to focus more on the application and
> client requirements while still using a relational database.

## Q16. Why PostgreSQL instead of MongoDB for this project?

> The data involved structured entities such as categories, reviews and
> configuration, and a relational database gives strong consistency and
> relationships when those become important.
>
> I would choose based on the data model and access patterns rather than
> choosing MongoDB or PostgreSQL by default.

## Q17. Explain the architecture.

> At a high level:
>
> **Client → Next.js application → API/backend logic →
> Supabase/PostgreSQL**
>
> The admin functionality is protected by authentication, while public
> pages consume the content that the admin manages.
>
> The image pipeline handles uploaded media separately from the
> textual/content data, so the database doesn't need to store large
> image binaries directly.

## Q18. Explain your admin authentication.

> The admin authenticates and receives an authenticated session/token.
> Protected routes verify that authentication before allowing
> content-management operations.
>
> The important distinction is that authentication answers "who are
> you?", while authorization answers "what are you allowed to do?"
>
> For a production system I would also care about secure cookie
> configuration, token expiry, refresh/revocation strategy, password
> protection, rate limiting and audit logging.

## Q19. Why JWT?

> JWT is useful when I want a signed token carrying claims that can be
> verified by the server without storing the complete session state in
> the token itself.
>
> However, JWT isn't automatically more secure than sessions. The
> storage strategy, expiry, signing key management, transport security
> and revocation strategy matter.

## Q20. Where should JWT be stored?

> For a browser-based application, I prefer secure, HttpOnly cookies for
> sensitive authentication tokens because JavaScript cannot directly
> read an HttpOnly cookie, which reduces exposure to token theft through
> XSS.
>
> I would combine that with Secure and appropriate SameSite settings,
> HTTPS, CSRF protection where applicable, short-lived access tokens and
> a controlled refresh-token strategy.

## Q21. How would you improve the authentication system?

> I would consider short-lived access tokens, secure HttpOnly cookies,
> refresh-token rotation, server-side revocation for refresh tokens,
> rate limiting on authentication endpoints, strong password hashing,
> email verification and audit logs.
>
> I would also make sure authentication errors don't reveal unnecessary
> information.

---

# 7. HugnLove CRUD APIs

## Q22. What APIs did you create?

> I created CRUD REST APIs for categories, reviews and site
> configuration.
>
> The basic pattern was to expose endpoints for creating, reading,
> updating and deleting the relevant resources, validate input,
> authenticate protected operations, interact with the database, and
> return appropriate HTTP status codes and response bodies.

## Q23. What makes a REST API good?

> Clear resource-oriented URLs, correct HTTP methods, meaningful status
> codes, validation, consistent response formats, authentication and
> authorization where needed, proper error handling, idempotency where
> relevant, and good documentation.
>
> I also care about pagination, rate limiting, logging and observability
> when the API is expected to grow.

## Q24. PUT vs PATCH?

> PUT generally represents replacing the resource representation, while
> PATCH represents a partial modification.
>
> For example, updating only a user's display name would naturally be a
> PATCH operation.

## Q25. What status codes would you use?

> 200 for successful reads or updates, 201 for successful creation, 204
> when a successful operation has no response body, 400 for invalid
> input, 401 when authentication is missing/invalid, 403 when the user
> is authenticated but not allowed, 404 when the resource doesn't exist,
> 409 for conflicts, and 500 for unexpected server errors.

## Q26. How do you validate an API request?

> Validate at the API boundary before passing data deeper into the
> application. I would validate types, required fields, formats, lengths
> and allowed values.
>
> Validation should not replace database constraints; both
> application-level and database-level protection are useful.

---

# 8. Image Upload / Thumbnail Pipeline

## Q27. Explain your image pipeline.

> The purpose was to accept uploaded images, process them into
> appropriate thumbnail representations, and make them available for the
> gallery without forcing every page load to use the original
> high-resolution asset.
>
> The key optimization is that the application should serve an
> appropriately sized image for the use case rather than always
> downloading the largest original.

## Q28. Why thumbnails?

> Thumbnails reduce bandwidth, memory usage and image decoding work on
> the client. This improves page loading, especially for a gallery with
> many images.

## Q29. What would you do for a production image pipeline?

> I would validate file type and size, generate thumbnails or responsive
> variants, store objects in object storage/CDN-backed storage, keep
> metadata in the database, generate stable URLs, and possibly process
> large uploads asynchronously.
>
> I would also prevent arbitrary file uploads from becoming a security
> issue.

---

# 9. Encode --- Very High Priority

## Q30. Explain Encode.

> Encode is an API for generating QR codes in multiple formats. I built
> it using Node.js and Express and supported formats such as VCard,
> WiFi, SMS, location, events, Bitcoin and UPI.
>
> I designed routes and parsers for GET and POST requests. I also added
> Redis caching to avoid regenerating identical requests unnecessarily,
> which reduced response time by roughly 70%.
>
> Another design decision was streaming the generated QR image directly
> as the HTTP response so the result could be consumed as a URL rather
> than requiring a separate client-side download step.

## Q31. Why Redis?

> QR generation can be deterministic for the same input. If the same
> request arrives repeatedly, regenerating the same QR image is
> unnecessary work.
>
> Redis gives me a fast key-value cache where I can store the generated
> result for a period of time.
>
> The important part is choosing a good cache key, setting an
> appropriate TTL, and making sure stale data is acceptable for the
> operation.

## Q32. How did Redis improve response time?

> Instead of executing the QR-generation path every time, repeated
> requests can be served from Redis. That avoids repeated computation
> and reduces the latency of the request.
>
> In my project the measured improvement was approximately 70%, but I
> would treat that as a project-specific benchmark rather than a
> universal number.

## Q33. What is cache-aside?

> The application first checks the cache. If the value exists, it
> returns it. If it doesn't, the application retrieves or computes the
> value, stores it in the cache, and then returns it.
>
> This is often called cache-aside or lazy caching.

## Q34. What if Redis is down?

> Redis should not become a single point of failure for QR generation.
> The API should be able to fall back to generating the QR directly if
> the cache is unavailable.
>
> I would log the Redis failure and monitor it, but the core API should
> remain functional unless caching is a hard requirement.

## Q35. How do you choose a Redis cache key?

> The key should uniquely represent the inputs that affect the generated
> QR code.
>
> For example, I could canonicalize the request parameters and hash
> them:
>
> `qr:<hash-of-normalized-input>`
>
> Canonicalization matters because semantically identical inputs should
> produce the same key where appropriate.

## Q36. Why normalize input before hashing?

> If two requests contain the same logical data but differ only in
> ordering or representation, hashing the raw request can create
> different keys. Normalization gives equivalent requests the same cache
> key.

## Q37. What is cache invalidation in Encode?

> Because the output is determined by the request data, invalidation is
> relatively simple compared with mutable business data. I can use a TTL
> to automatically expire cached entries.
>
> If the generation algorithm changes and old outputs must not be
> served, I can version the cache key, for example:
>
> `qr:v2:<hash>`

---

# 10. Streaming QR Images

## Q38. What does "stream the image directly" mean?

> Instead of returning a file that the client has to download
> separately, the API writes the generated image bytes directly to the
> HTTP response with the appropriate content type.
>
> The browser or consuming application can then use the endpoint as the
> image source.

## Q39. Why is streaming useful?

> It removes an unnecessary intermediate download step and makes the API
> easier to consume. A client can use the endpoint directly as an image
> URL.

## Q40. What HTTP header matters?

> The `Content-Type` header. For example, if the response is a PNG
> image, it should indicate `image/png`.

---

# 11. GET vs POST in Encode

## Q41. Why support both GET and POST?

> GET is convenient for simple, URL-representable parameters and makes
> the generated image easy to consume as a URL.
>
> POST is better when the request data is larger, structured, or
> shouldn't be represented directly in the URL.
>
> The choice depends on how the endpoint is consumed and the nature of
> the input.

## Q42. Should a GET request modify server state?

> Ideally no. GET should be safe and idempotent from the API consumer's
> perspective. Generating a response or populating a cache as an
> implementation detail is different from creating or modifying a
> business resource.

---

# 12. Cart NPM Package

## Q43. Explain your cart package.

> I built an NPM package that provides cart functionality for vanilla
> JavaScript and React applications.
>
> The core functionality was designed without peer dependencies, and for
> React I exposed it through a context provider. I also supported dual
> storage without requiring a backend.
>
> The goal was to make common cart operations reusable instead of
> rewriting the same logic inside every application.

## Q44. Why did you build an NPM package?

> I wanted to solve a reusable problem rather than build another one-off
> application. A cart is common functionality, so packaging the logic
> forces me to think about API design, backwards compatibility,
> integration and developer experience.

## Q45. What does "zero peer dependencies" mean?

> It means the package doesn't require consumers to install additional
> peer packages for the core functionality.
>
> This reduces integration friction and dependency conflicts, although
> it also means the package needs to avoid assuming libraries that
> aren't guaranteed to exist in the consumer application.

## Q46. Why Context API for React?

> Context provides a way to expose shared state and operations to
> components without passing props through every intermediate component.
>
> For cart functionality, that makes operations such as add, remove and
> update accessible to components that need them.

## Q47. What are the disadvantages of Context API?

> Context can cause unnecessary re-renders when the provider value
> changes and many consumers subscribe to the same context.
>
> For a small cart this can be acceptable. For larger state with complex
> update patterns, I would consider splitting contexts, memoization,
> selectors, or a dedicated state-management library.

## Q48. What does dual-storage support mean?

> It means the cart can persist its state using browser storage
> mechanisms without requiring a backend. The exact choice depends on
> whether persistence across browser sessions is required and whether
> the data is sensitive.

## Q49. localStorage vs sessionStorage?

> `localStorage` persists until explicitly removed, while
> `sessionStorage` generally lasts for the lifetime of the browser
> tab/session.
>
> Neither should be treated as a secure storage mechanism for sensitive
> authentication tokens because JavaScript can access the stored values.

---

# 13. Open Source Contribution

## Q50. Tell me about your open-source contribution.

> I contributed to `Ileriayo/markdown-badges` and had PR #986 merged. I
> implemented the requested feature and went through code review with
> the maintainers.
>
> The important part for me wasn't just getting the code merged; it was
> learning to work within an existing codebase and respond to review
> feedback rather than controlling the entire project myself.

## Q51. What did you learn from code review?

> Code review taught me that code can be functionally correct and still
> be improved in readability, consistency or maintainability.
>
> In a team, the goal isn't to defend my first implementation; it is to
> arrive at a solution that fits the project's standards.

## Q52. What if a reviewer rejects your approach?

> I would first understand the reasoning. If the reviewer has a better
> technical or project-specific argument, I would change the
> implementation.
>
> If I disagree, I would explain the trade-off with evidence and discuss
> it rather than treating the review as personal criticism.

---

# 14. Node.js Questions

## Q53. What is Node.js?

> Node.js is a JavaScript runtime built on the V8 engine that allows
> JavaScript to run outside the browser. It is particularly useful for
> I/O-heavy applications because it uses an event-driven, non-blocking
> architecture.

## Q54. Is Node.js single-threaded?

> JavaScript execution in the main Node.js event loop is
> single-threaded, but Node itself is not limited to one OS thread. It
> uses libuv and a worker pool for certain operations, and applications
> can also use worker threads or multiple processes.
>
> So "Node.js is single-threaded" is an oversimplification.

## Q55. How does Node handle concurrency?

> Node uses an event loop to coordinate asynchronous operations. Instead
> of blocking the main thread while waiting for I/O, it can continue
> processing other work and later execute the callback or continuation
> when the operation completes.
>
> Some operations are delegated to the operating system or libuv's
> worker pool.

## Q56. What happens when a request reaches Express?

> The request reaches the Node HTTP server, which passes it into the
> Express application. Express executes the middleware chain, matches
> the route, runs the relevant handler, performs business logic or
> database operations, and eventually sends a response.
>
> Error-handling middleware can handle errors that propagate through the
> chain.

## Q57. What is middleware?

> Middleware is a function that participates in the request-response
> pipeline. It can inspect or modify the request/response, perform
> authentication or validation, log requests, or terminate the request.
>
> In Express, middleware commonly receives `req`, `res`, and `next`.

## Q58. What happens if middleware never calls next()?

> If it doesn't send a response and doesn't call `next()`, the request
> can remain pending because the pipeline cannot continue.

## Q59. What is callback hell?

> Callback hell is deeply nested callback-based asynchronous code that
> becomes difficult to read, maintain and handle errors in.
>
> Promises and async/await make asynchronous control flow easier to
> structure.

## Q60. What is the event loop?

> The event loop is the mechanism that allows Node.js to coordinate
> asynchronous work while JavaScript executes on the main thread. When
> asynchronous operations complete, their callbacks or continuations
> become eligible to run according to the event loop's scheduling rules.

---

# 15. Express Questions

## Q61. How would you structure an Express application?

> I would separate concerns into routes, controllers, services/business
> logic, data-access/models, middleware and configuration.
>
> For example:
>
> `routes → controllers → services → repositories/models`
>
> This makes the code easier to test and prevents route handlers from
> becoming large blocks containing every responsibility.

## Q62. How would you implement global error handling?

> I would use centralized error-handling middleware and consistent error
> objects. Controllers should pass unexpected errors to the error
> handler rather than duplicating response logic everywhere.
>
> I would also avoid exposing stack traces or internal details in
> production responses.

## Q63. How would you secure an Express API?

> Authentication, authorization, input validation, secure headers, rate
> limiting, CORS configuration, safe error responses, logging, HTTPS,
> secure cookies where applicable, and protection against injection or
> unsafe file uploads.

---

# 16. MongoDB

## Q64. Why MongoDB?

> MongoDB is useful when the data model benefits from flexible documents
> and the application doesn't need every relationship to behave like a
> traditional relational schema.
>
> It can also be convenient for rapidly evolving application models.
>
> I wouldn't choose MongoDB simply because it is popular. I would look
> at the relationships, transactions, query patterns, consistency
> requirements and scaling model first.

## Q65. What are MongoDB's limitations?

> Compared with relational databases, complex relationships and joins
> can be less natural, schema flexibility can become a problem if not
> controlled, and transaction-heavy relational workloads may fit SQL
> databases better.
>
> MongoDB has improved its transaction capabilities, so I wouldn't claim
> that MongoDB cannot do transactions.

## Q66. What is a document?

> A document is MongoDB's basic data record, represented using a BSON
> document. It is conceptually similar to a row but can contain nested
> objects and arrays.

## Q67. What is a collection?

> A collection is a group of MongoDB documents and is roughly analogous
> to a table in a relational database, although the data model is
> different.

## Q68. MongoDB vs Mongoose?

> MongoDB is the actual database. Mongoose is an ODM for Node.js that
> provides schema definitions, validation, middleware, models and other
> abstractions for working with MongoDB.
>
> MongoDB itself doesn't require Mongoose.

## Q69. Why Mongoose?

> Mongoose gives a more structured programming model on top of MongoDB.
> Schemas and validation can make application data more predictable,
> while middleware and models can centralize common logic.

## Q70. What is Mongoose middleware?

> Mongoose middleware, or hooks, are functions that execute at
> particular stages of document or query operations. They can be used
> for tasks such as validation, transformations, logging or related
> business behavior.

---

# 17. PostgreSQL / SQL

## Q71. SQL vs NoSQL?

> SQL databases are relational and typically use structured schemas,
> relationships and powerful query capabilities. NoSQL is a broad
> category including document, key-value and other models.
>
> I would choose based on the problem. Strong relationships, constraints
> and complex queries often favor PostgreSQL. Flexible document-oriented
> data and certain scaling/access patterns can favor MongoDB.

## Q72. Why PostgreSQL?

> PostgreSQL is a strong relational database with transactions,
> constraints, joins, indexes, advanced SQL functionality and
> extensibility. It is a good choice when data integrity and
> relationships are important.

## Q73. What is an index?

> An index is an additional data structure that helps the database
> locate rows/documents faster for particular access patterns.
>
> The trade-off is that indexes consume storage and make writes more
> expensive because the index must also be maintained.

## Q74. What should you index?

> Columns frequently used in filtering, joins, sorting or uniqueness
> constraints can be candidates. But I would base indexing on actual
> query patterns and execution plans rather than indexing everything.

## Q75. What are ACID properties?

> Atomicity: a transaction is all-or-nothing.
>
> Consistency: the transaction preserves database rules.
>
> Isolation: concurrent transactions should not incorrectly interfere
> with each other.
>
> Durability: committed changes survive failures according to the
> database's guarantees.

## Q76. What is normalization?

> Normalization is organizing relational data to reduce unnecessary
> duplication and update anomalies.
>
> The trade-off is that highly normalized schemas can require more
> joins, so controlled denormalization can sometimes improve read
> performance.

## Q77. What is a transaction?

> A transaction groups operations into a unit that should follow the
> database's transaction guarantees. For example, transferring money
> should not leave one account debited if the corresponding credit
> fails.

---

# 18. Redis

## Q78. What is Redis?

> Redis is an in-memory data store commonly used for caching, counters,
> queues, rate limiting, sessions and other low-latency use cases.

## Q79. Why is Redis fast?

> It primarily operates in memory and uses efficient data structures and
> a simple access model, so many operations have very low latency.

## Q80. Redis vs database?

> Redis is often used as a fast auxiliary data store rather than a
> replacement for the primary database.
>
> A common architecture is:
>
> `Application → Redis cache → Primary DB`
>
> The database remains the source of truth unless the architecture
> deliberately uses Redis as a primary store.

---

# 19. Socket.IO

## Q81. What is Socket.IO?

> Socket.IO is a library for real-time, bidirectional communication
> between clients and servers. It commonly uses WebSocket when possible
> while providing additional abstractions such as events, rooms and
> reconnection behavior.

## Q82. WebSocket vs HTTP?

> HTTP is primarily request-response, while WebSocket provides a
> persistent bidirectional connection after the handshake.
>
> WebSockets are useful for real-time communication such as chat, live
> notifications or collaborative applications.

## Q83. What are Socket.IO rooms?

> Rooms allow sockets to join logical groups so the server can emit
> events to a specific group rather than broadcasting to every connected
> client.

---

# 20. REST API

## Q84. What is REST?

> REST is an architectural style for designing networked resources
> around stateless interactions and standard HTTP semantics.
>
> In practice, a REST API generally exposes resources through
> predictable URLs and uses HTTP methods appropriately.

## Q85. What does stateless mean?

> Each request contains the information required to process it. The
> server should not depend on hidden per-client request state stored in
> the server between requests, although external systems such as
> databases or caches can of course store data.

---

# 21. OAuth

## Q86. What is OAuth?

> OAuth is an authorization framework that allows an application to
> obtain limited access to resources on behalf of a user without
> receiving the user's password.
>
> OAuth 2.0 is primarily about authorization; OpenID Connect builds
> authentication on top of OAuth 2.0.

## Q87. Authentication vs authorization?

> Authentication asks **who are you?**
>
> Authorization asks **what are you allowed to do?**

---

# 22. Docker / DevOps

## Q88. What is Docker?

> Docker packages an application and its dependencies into a container
> image so the application can run consistently across environments.

## Q89. Container vs VM?

> A VM virtualizes a complete operating-system environment, while
> containers generally share the host kernel and isolate processes.
>
> Containers are typically lighter and start faster, while VMs provide
> stronger OS-level isolation and can run different operating systems.

## Q90. What is a Docker image?

> An image is an immutable template containing the application and
> required filesystem layers. A container is a running instance of an
> image.

## Q91. Why use Docker for a Node application?

> It gives a reproducible environment for the Node version, dependencies
> and system-level requirements. It also makes deployment and local
> environment consistency easier.

---

# 23. Git / GitHub

## Q92. Git vs GitHub?

> Git is the distributed version-control system. GitHub is a platform
> that hosts Git repositories and provides collaboration features such
> as pull requests, reviews and issue tracking.

## Q93. Merge vs rebase?

> Merge preserves the branch history and creates a merge commit when
> necessary. Rebase moves commits onto a new base and produces a more
> linear history.
>
> Rebase rewrites commit history, so I would be careful using it on
> shared branches.

## Q94. What is a pull request?

> A pull request is a proposed change from one branch/repository into
> another. It provides a place for review, discussion, automated checks
> and eventually merging.

---

# 24. Linux / Bash

## Q95. Why do you use Linux?

> I like Linux for development because of its command-line tooling,
> scripting capabilities, package ecosystem and similarity to many
> server environments.

## Q96. Commands you should know

Be ready to explain:

```text
ls
cd
pwd
cp
mv
rm
mkdir
cat
less
grep
find
chmod
chown
ps
top
kill
curl
ssh
tar
tail
head
sort
uniq
awk
sed
```

---

# 25. TypeScript

## Q97. TypeScript vs JavaScript?

> JavaScript is the language executed by the runtime. TypeScript is a
> superset of JavaScript that adds static type checking and is
> compiled/transformed into JavaScript.
>
> TypeScript helps catch many mistakes before runtime and improves
> maintainability in larger projects.

## Q98. Interface vs type?

> Both can describe object shapes. Interfaces are particularly useful
> for object-oriented or extendable contracts, while type aliases are
> more flexible for unions, intersections and other type expressions.
>
> I choose based on the type I'm modeling rather than treating one as
> universally better.

---

# 26. React

## Q99. State vs props?

> Props are inputs passed from a parent to a component. State is data
> managed by the component or a state-management mechanism.
>
> Props are generally read-only from the receiving component's
> perspective, while state changes can trigger re-rendering.

## Q100. What is Virtual DOM?

> It is an in-memory representation of the UI that React uses to reason
> about updates. React compares the new representation with the previous
> one and commits the necessary changes to the actual DOM.
>
> It should not be described simply as "the Virtual DOM makes everything
> faster"; performance depends on the overall rendering strategy.

## Q101. What is reconciliation?

> Reconciliation is React's process of determining what needs to change
> between renders and applying the necessary updates.

## Q102. useState?

> `useState` lets a functional component maintain state. Updating that
> state schedules a re-render so the UI can reflect the new value.

## Q103. useEffect?

> `useEffect` is used to synchronize a component with external systems
> or perform side effects after rendering, such as subscriptions,
> network interactions or integrating with browser APIs.
>
> It shouldn't be treated as a generic replacement for event handlers or
> ordinary computation.

## Q104. What is prop drilling?

> Prop drilling is passing data through intermediate components that
> don't actually need the data, simply because a deeper component needs
> it.
>
> Context, composition or state-management solutions can reduce it
> depending on the problem.

## Q105. How do you optimize React rendering?

> First I would identify the actual bottleneck. Then possible techniques
> include component decomposition, stable keys, memoization where
> justified, `useMemo`, `useCallback`, virtualization for long lists,
> reducing unnecessary state updates, and avoiding unnecessary
> context-wide re-renders.

---

# 27. Next.js

## Q106. Next.js vs React?

> React is a UI library. Next.js is a framework built around React that
> provides routing, rendering strategies, server-side capabilities and
> production tooling.
>
> React can be used without Next.js; Next.js uses React as its UI layer.

## Q107. SSR vs CSR?

> CSR initially sends JavaScript and the browser renders much of the UI.
> SSR generates HTML on the server for a request and then the client can
> hydrate it.
>
> SSR can improve initial rendering and SEO for suitable pages, while
> CSR can be simpler for highly interactive application interfaces.

## Q108. What is hydration?

> Hydration is the process where client-side JavaScript attaches
> behavior and event handlers to server-rendered HTML so the page
> becomes interactive.

---

# 28. DSA --- Must Practice

The supplied Userfacet experiences contain questions such as right-view
of a binary tree, merge-two-sorted-lists, longest consecutive sequence,
3Sum variants, maximal square, greedy/max-profit variants and array
duplicate removal.

## Q109. Right view of a binary tree

### Answer approach

> The right view contains the last visible node at each depth.
>
> With BFS, I process the tree level by level and take the last node of
> each level.
>
> Time complexity is O(n) because every node is visited once. Space
> complexity is O(w), where w is the maximum width of the tree.

Be ready to implement it.

### Recursive version

> With DFS, I traverse right before left and keep track of the deepest
> level already added. When I reach a new level for the first time, I
> add that node.
>
> Time is O(n), with O(h) recursion stack excluding the output.

---

# 29. Merge Two Sorted Linked Lists

### Best explanation

> I can maintain two pointers, one for each list, and repeatedly attach
> the smaller current node to the result. When one list ends, I attach
> the remaining nodes of the other list.
>
> This gives O(n + m) time and O(1) auxiliary space for the iterative
> version.

Then be ready for:

- Recursive solution
- Empty lists
- One-node lists
- Equal values
- Complexity

---

# 30. Longest Consecutive Sequence

### Best explanation

> I would put all numbers in a hash set. Then for every number, I only
> start building a sequence if `number - 1` isn't present. From there I
> count upward.
>
> This avoids repeatedly starting the same sequence and gives expected
> O(n) time with O(n) space.

---

# 31. Remove Duplicates While Preserving Order

### Best answer

> I would maintain a Set of values already seen and iterate through the
> array. If the value isn't in the set, I add it to the result and mark
> it as seen.
>
> That gives expected O(n) time and O(n) additional space.
>
> If the interviewer specifically asks for a `filter` solution, I can
> also explain the `filter` + `indexOf` approach, but I would point out
> that it can become O(n²).

---

# 32. Clock Angle

## Q113. Find the angle between hour and minute hands.

### Formula

> Minute hand angle = `6 × minutes`
>
> Hour hand angle = `30 × hour + 0.5 × minutes`
>
> Difference = absolute difference between the two.
>
> Final answer is `min(diff, 360 - diff)`.

---

# 33. OS Questions

## Q114. Process vs thread?

> A process has its own address space and resources, while threads
> within a process share the process's memory and resources.
>
> Threads are generally cheaper to create and communicate between, but
> shared memory introduces synchronization concerns.

## Q115. What is a race condition?

> A race condition occurs when the result depends on the timing/order of
> concurrent operations accessing shared state.
>
> For example, two requests reading the same balance and both writing an  
> updated balance can overwrite each other's changes.

## Q116. What is deadlock?

> Deadlock is a state where processes or threads are waiting
> indefinitely for resources held by each other.

### Four necessary conditions

1. Mutual exclusion
2. Hold and wait
3. No preemption
4. Circular wait

## Q117. What is starvation?

> Starvation occurs when a process keeps getting denied the resources or
> CPU time it needs because other processes are continually prioritized.
>
> Scheduling strategies such as aging can help reduce starvation.

---

# 34. DBMS Questions

## Q118. What is a primary key?

> A primary key uniquely identifies a record in a relational table. It
> must be unique and cannot be NULL.

## Q119. What is a foreign key?

> A foreign key references a key in another table and is used to
> maintain referential integrity between related records.

## Q120. What are joins?

Know:

- INNER JOIN
- LEFT JOIN
- RIGHT JOIN
- FULL OUTER JOIN
- CROSS JOIN
- SELF JOIN

## Q121. JOIN vs subquery?

> Neither is universally better. The optimizer may transform them
> internally depending on the database.
>
> I would choose based on readability and the query semantics, then
> inspect the execution plan if performance matters.

## Q122. What is a trigger?

> A trigger is database logic automatically executed when specified
> events occur, such as INSERT, UPDATE or DELETE.
>
> Triggers can enforce or automate certain behavior, but excessive use
> can make application behavior harder to understand and test.

---

# 35. OOP

## Q123. Explain the four pillars of OOP.

> Encapsulation groups data and behavior and controls access to internal
> state.
>
> Abstraction exposes essential behavior while hiding implementation
> details.
>
> Inheritance allows one type to derive behavior from another.
>
> Polymorphism allows the same interface to represent different
> implementations.

## Q124. Composition vs inheritance?

> Inheritance expresses an "is-a" relationship. Composition expresses a
> "has-a" relationship by combining objects.
>
> I generally prefer composition when it reduces coupling and makes
> behavior easier to change.

---

# 36. Scenario Questions

## Q125. How would you design an admin panel?

### Best answer structure

> I would start with authentication and RBAC. Users would have roles or
> permissions, and every sensitive API would enforce authorization
> server-side rather than relying only on frontend hiding.
>
> I would add audit logs for important actions, pagination/filtering for
> activity data, validation, rate limiting, and appropriate database
> indexes.
>
> For concurrent updates, I would define whether last-write-wins is
> acceptable or whether optimistic locking/version checks are needed.

---

## Q126. Payment gateway gets stuck. What do you do?

> I would not treat a client-side timeout as proof that the payment
> failed.
>
> I would create a payment record with a pending state and use the
> gateway's webhook or verification API to determine the final status.
>
> I would use an idempotency key so retries don't create duplicate
> payments.
>
> The client can safely show a pending state while the server reconciles
> the transaction.

---

## Q127. Design a Google Docs-like application.

### Best answer

> I would first clarify whether the requirement is simultaneous
> collaborative editing, offline editing, version history, comments, or
> just document sharing.
>
> For real-time collaboration, I would use persistent WebSocket
> connections and a conflict-resolution model such as operational
> transformation or CRDTs.
>
> Documents and metadata could live in a database, while changes could
> be represented as operations. I would need authentication,
> authorization, versioning, persistence, presence information, conflict
> resolution and recovery.
>
> I would avoid designing the system around simply broadcasting the
> entire document on every keystroke because that would become
> inefficient as the document and number of collaborators grow.

---

# 37. Behavioral Questions

## Q128. Why Userfacet?

### Best answer

> I am interested in Userfacet because it sits at the intersection of
> product engineering and user experience, rather than treating
> engineering as only writing backend or frontend code.
>
> I also like the kind of work where engineers have to understand the
> actual user problem and ship something usable. From my own projects,
> especially HugnLove Crochet, I enjoyed working directly with a client
> and translating requirements into a working product.
>
> Userfacet's current focus on designing and shipping AI experiences
> also interests me because I want to understand how AI features are
> integrated into real products rather than treating AI as an isolated
> model or API. Verify current company details before the interview.
>
> I think that combination of product thinking, UX and engineering is a
> good fit for how I want to grow.

## Q129. Why should we hire you?

> I think I bring a combination of hands-on development, willingness to
> learn and ownership.
>
> I have not only built applications; I have worked directly with a
> client, built and deployed APIs, optimized an API using Redis, created
> a reusable NPM package, worked with an existing open-source codebase,
> and handled a project end-to-end.
>
> I also know that I am still early in my career. So rather than
> claiming to know everything, I focus on being able to learn quickly,
> understand the problem and take responsibility for delivering a
> solution.

## Q130. What makes you stand out?

> One thing that differentiates me is that I like building reusable
> engineering solutions rather than only completing application
> features.
>
> My NPM cart package is an example: I had to think about API design and
> integration rather than only making a UI work. Encode also made me
> think about caching and response delivery. The open-source
> contribution exposed me to code review in an existing project.
>
> So my interest isn't limited to making something work once; I like
> thinking about how other developers and users will interact with it.

---

# 38. Strengths

## Q131. Give me 5 strengths.

### Strong answer

> I would say:
>
> 1. **Ownership** --- I like taking a feature from requirements to a
>   working deployment.
> 2. **Learning by building** --- I usually understand technologies
>   fastest when I apply them to a real problem.
> 3. **Problem solving** --- I enjoy breaking ambiguous problems into
>   smaller technical decisions.
> 4. **Adaptability** --- I have worked across frontend, backend,
>   databases, deployment and tooling.
> 5. **Team coordination** --- my society experience taught me to
>   communicate and delegate while working with a team.

### If asked for examples

Have one concrete example ready for each.

---

# 39. Weaknesses

## Q132. Give me 5 weaknesses.

Do not say five fake strengths.

### Safer answer

> One weakness I have been working on is that I can spend too much time
> trying to make an implementation cleaner than the requirement actually
> needs. I have been improving that by first defining the required
> outcome and time constraint.
>
> Another is that when I am learning something technically interesting,
> I can go too deep into it. I now try to separate what is necessary for
> the current task from what can be explored later.
>
> I also used to try to solve some problems independently for too long
> before asking for input. Working in teams has taught me that raising a
> blocker early is usually better.
>
> I am also continuing to improve my ability to communicate technical
> ideas concisely.
>
> Finally, because I work across many technologies, I am deliberately
> focusing on deeper expertise in backend/product engineering instead of
> trying to become equally advanced in everything.

---

# 40. Where do you see yourself in 5 years?

### Best answer

> In five years, I want to be a strong product-focused engineer who can
> independently own significant parts of a system, from understanding
> requirements through architecture, implementation, deployment and
> maintenance.
>
> I would like to have deeper expertise in backend and distributed
> application development while still understanding the frontend and
> product side well enough to make good end-to-end decisions.
>
> I am less focused on a specific title and more focused on reaching a
> point where I can be trusted with technically and product-wise
> important problems.

---

# 41. Would you leave Userfacet for a higher offer?

### Best answer

> Compensation is obviously one factor in a career decision, but it
> wouldn't be the only one.
>
> If I join a company, I want to learn, contribute and grow there. I
> wouldn't join with the intention of immediately leaving for the next
> offer.
>
> At the same time, I think it is unrealistic to promise that
> compensation or opportunities will never matter. My preference would
> be to build a strong long-term relationship where both sides continue
> to find value in working together.

---

# 42. What if Google/Microsoft/a bigger company offers you more?

### Best answer

> I would evaluate the actual opportunity rather than the brand name
> alone.
>
> I would look at the work, learning, ownership, team, engineering
> culture, growth and compensation together.
>
> A bigger brand is attractive, but it isn't automatically the better
> engineering opportunity for me at every point in my career.

---

# 43. What annoys you?

### Best answer

> Repeated avoidable problems caused by poor communication can frustrate
> me, especially when they affect other people.
>
> But I've learned that being frustrated doesn't solve the problem. I
> try to identify whether the issue is unclear requirements, ownership,
> communication or process and address that specifically.

---

# 44. What motivates you?

> I am motivated by building something that actually works for someone
> and by understanding why the solution works.
>
> I enjoy the point where a problem goes from being ambiguous to
> something I can break down, implement and test.
>
> That is one reason I enjoy projects where I can see the full path from
> requirement to deployment.

---

# 45. How do you learn a new technology?

> I usually start with the official documentation and a small working
> example. Then I apply the technology to a concrete problem.
>
> Once I understand the basic model, I look at common production
> patterns, limitations and failure cases.
>
> Finally, I try to build something with it rather than stopping at
> tutorials.

---

# 46. What if you don't know the answer?

### Best answer

> If I don't know, I would say that directly rather than guessing.
>
> If I understand related concepts, I would explain what I know and how
> I would approach finding the answer.
>
> For example: "I don't remember the exact API or implementation detail,
> but based on how this system works, I would approach it by..."

This is consistent with the supplied Userfacet experiences, which
explicitly advise candidates not to bluff.

---

# 47. Why Backend?

### Best answer

> I like backend development because I enjoy thinking about how the
> system behaves underneath the interface: data modeling, APIs,
> authentication, performance, concurrency and failure handling.
>
> Projects like Encode made that especially interesting for me because I
> could think about caching, request design and response performance.
>
> At the same time, I don't want to become disconnected from the
> frontend or user experience. I prefer being able to understand the
> complete product.

---

# 48. Why Full Stack?

> I like full-stack development because it gives me visibility into the
> complete system.
>
> When I build something, I can understand the user's interaction, the
> API, the database and the deployment rather than treating each part
> independently.
>
> My longer-term direction is deeper backend engineering, but I want
> enough frontend understanding to make good end-to-end decisions.

---

# 49. Questions About Your Skill Ratings

If asked:

> "Rate yourself in JavaScript/Node/MongoDB/etc."

Do **not** claim 10/10.

### Better response

> I would rate myself based on practical ability rather than how much of
> the technology exists.
>
> For example, I am comfortable building applications and APIs with
> JavaScript/Node.js, but I would still consider myself learning
> advanced internals and large-scale production patterns.
>
> So I would give myself a realistic rating and be prepared to explain
> exactly what I can and cannot do at that level.

---

# 50. Resume Technology Rapid-Fire

You list many technologies. Prepare at least one question for each.

## Backend

- What is Next.js?
- What is Node.js?
- How does Express work?
- What is Socket.IO?
- What is Flask?
- What is a REST API?

## Frontend

- React vs Next.js?
- Why Tailwind?
- Why TypeScript?
- What is Electron?
- What is Tauri?
- Electron vs Tauri?

## Database

- MongoDB vs PostgreSQL?
- Prisma vs Mongoose?
- MySQL vs PostgreSQL?
- SQLite use cases?
- Supabase?
- Redis?

## DevOps

- Git?
- Docker?
- Container?
- Image?
- CI/CD?
- Cloud deployment?

## Languages

- C vs C++?
- Python vs JavaScript?
- Java vs C++?
- Static vs dynamic typing?

## Other

- Zustand?
- OAuth?
- Makefile?
- Linux?

**Important:** If you cannot answer a technology confidently, be ready
to explain why it appears on the resume and what you actually used it
for.

---

# 51. Prisma vs Mongoose

## Q133. Prisma vs Mongoose?

> Mongoose is an ODM primarily used with MongoDB and provides schemas,
> validation, models and middleware.
>
> Prisma is an ORM that supports relational databases and provides a
> type-safe database client and schema-driven workflow.
>
> They solve related developer-experience problems but target different
> database models and workflows.

---

# 52. MySQL vs PostgreSQL

> Both are mature relational databases. PostgreSQL has particularly
> strong SQL features, extensibility and advanced data types, while
> MySQL is also widely used and can be a strong choice depending on the
> application and ecosystem.
>
> I would choose based on the team's ecosystem, required features,
> workload and operational requirements.

---

# 53. Supabase

> Supabase provides managed services around PostgreSQL, including
> database access and additional backend capabilities.
>
> I used it in HugnLove Crochet because it reduced the amount of backend
> infrastructure I needed to manage for a client project.

---

# 54. Zustand

> Zustand is a lightweight state-management library for React
> applications. It can be useful when shared state needs to be accessed
> across components without pushing everything through props or Context.
>
> I would choose it when the state complexity justifies centralized
> state and keep local UI state local where possible.

---

# 55. Electron vs Tauri

> Both can be used to build desktop applications using web technologies.
>
> Electron packages a Chromium browser and Node.js, which gives a mature
> ecosystem but can result in larger applications.
>
> Tauri uses the system webview with a Rust backend, which can produce
> smaller binaries and a different security/performance model.

---

# 56. AI / Current Userfacet Direction

Userfacet's current official site emphasizes **designing and shipping AI
experiences into production**, including real-time captions, AI
summaries, enterprise data answers, adaptive learning and other
production AI experiences. It explicitly frames AI as a
product/experience problem rather than only a model problem.

## Q134. Why are you interested in Userfacet's AI direction?

### Best answer

> What interests me is the product side of AI. A model being capable
> isn't enough; the AI has to be integrated into a useful workflow,
> provide reliable output and create a good user experience.
>
> My background is primarily web and backend engineering, so I see AI
> product engineering as an opportunity to combine what I already
> know
> ---APIs, data, frontend interaction and deployment
> ---with AI
> capabilities.
>
> I would like to learn how AI features are evaluated, guarded,
> integrated and shipped to real users rather than treating an LLM API
> call as the entire product.

---

# 57. Questions They Can Ask About Your Numbers

Your resume contains quantified claims. Be prepared to defend every one.

## Q135. How did you measure the 70% Encode improvement?

### Answer framework

> I compared response time before and after introducing Redis caching
> under the same or comparable request conditions. The improvement was
> approximately 70%.
>
> The exact number depends on the workload and cache-hit rate, so I
> would describe it as a measured project result rather than a universal
> benchmark.

## Q136. How did you measure 90+ Lighthouse accessibility?

> I ran Lighthouse accessibility audits against the deployed/working
> pages and used the reported accessibility issues to guide fixes. The
> resulting audit score was above 90.

## Q137. How did you measure 5-minute package integration?

> The goal was to keep the API and integration surface simple enough
> that a developer could install the package, initialize it and use the
> exposed cart functionality quickly. The five-minute figure is an
> integration target rather than a claim that every developer will
> always finish in exactly five minutes.

---

# 58. Questions Designed to Challenge Your Resume

Be ready for:

1. Why do you have so many technologies listed?
2. Which technology are you strongest in?
3. Which one are you weakest in?
4. What have you actually used in production?
5. Which project demonstrates your backend ability?
6. Which project demonstrates your frontend ability?
7. Which project demonstrates system design?
8. Which project demonstrates teamwork?
9. Which project demonstrates performance optimization?
10. Which project demonstrates reusable engineering?
11. What did you personally write?
12. What did you copy or adapt?
13. What would you rebuild differently?
14. What is the biggest mistake in your projects?
15. Which project would you delete from your resume?
16. Why should we believe the metrics on your resume?
17. Which technology did you learn most recently?
18. What technology would you learn next?
19. What is missing from your resume?
20. Which skill is only theoretical?

---

# 59. High-Probability Coding Problems

Practice these before the interview:

### Arrays

- Two Sum
- Three Sum
- Remove duplicates
- Longest consecutive sequence
- Maximum subarray
- Subarray sum
- Merge intervals
- Product except self
- Sliding window

### Strings

- Longest palindrome
- Longest substring without repetition
- Valid anagram
- Group anagrams
- Character frequency

### Linked Lists

- Reverse linked list
- Merge two sorted lists
- Detect cycle
- Middle node
- Remove nth node

### Trees

- Level order
- Right view
- Left view
- Height
- Diameter
- LCA
- Balanced tree
- BST validation

### Common interview problems

- Clock angle
- Producer/consumer reasoning
- LRU cache
- Rate limiter
- Pagination
- Duplicate detection
- Top K frequent elements

---

# 60. Final 30 Questions to Practice Out Loud

If you have limited time, practice these first:

1. Tell me about yourself.
2. Explain HugnLove Crochet.
3. Explain Encode.
4. Why did you use Redis?
5. How did Redis give you 70% improvement?
6. Why MongoDB/PostgreSQL?
7. Explain JWT authentication.
8. How would you implement refresh tokens?
9. Explain your CRUD APIs.
10. Write one of your APIs.
11. Explain your database schema.
12. What happens when a request reaches Node/Express?
13. How does Node handle concurrency?
14. Explain middleware.
15. Explain event loop.
16. Explain MongoDB vs Mongoose.
17. Explain SQL vs NoSQL.
18. What is an index?
19. What is a transaction?
20. What is a race condition?
21. Solve right-view of a binary tree.
22. Merge two sorted linked lists.
23. Longest consecutive sequence.
24. Remove duplicates while preserving order.
25. Why Userfacet?
26. Why backend/full-stack?
27. What makes you different?
28. Five strengths and weaknesses.
29. Where do you see yourself in five years?
30. Would you leave for a higher offer?

---

# 61. Interviewer's Likely Follow-Up Chain

A very important preparation technique is to practice **chains**, not
isolated questions.

For example:

> "Why Redis?"

Be prepared for:

```text
Why Redis?
  ↓
Why not database?
  ↓
What is cache-aside?
  ↓
What is TTL?
  ↓
What if Redis goes down?
  ↓
How do you choose a cache key?
  ↓
What causes cache stampede?
  ↓
How would you prevent it?
```

For MongoDB:

```text
Why MongoDB?
  ↓
Limitations?
  ↓
MongoDB vs Mongoose?
  ↓
Schema?
  ↓
Indexes?
  ↓
Transactions?
  ↓
Replication?
  ↓
Sharding?
```

For JWT:

```text
Why JWT?
  ↓
Where store it?
  ↓
Why HttpOnly cookie?
  ↓
XSS?
  ↓
CSRF?
  ↓
Access vs refresh token?
  ↓
Logout?
  ↓
Token revocation?
```

For Encode:

```text
Explain Encode
  ↓
Why Redis?
  ↓
How caching works?
  ↓
What if cache misses?
  ↓
What if Redis is down?
  ↓
How cache key works?
  ↓
How did you benchmark 70%?
  ↓
How would you scale it?
```

---

# 62. Your Strongest Narrative

Your resume can tell a coherent story if you present it correctly:

> **"I started with full-stack development, then gradually moved deeper
> into reusable backend/product engineering."**

The evidence:

```text
Internship
   ↓
Real users + accessibility
   ↓
HugnLove
   ↓
Client + end-to-end ownership
   ↓
Encode
   ↓
Backend + caching + performance
   ↓
Cart package
   ↓
Reusable engineering
   ↓
Open source
   ↓
Existing codebase + code review
```

That is much stronger than saying:

> "I know React, Node, MongoDB, Redis, Docker, Python, Java, C++, etc."

The second statement sounds like a list. The first demonstrates
progression.

---

# 63. Things NOT to Say

Avoid:

- "MongoDB is better than SQL."
- "JWT is more secure than sessions."
- "Node.js is single-threaded, so it can't do multiple things."
- "Virtual DOM makes React faster."
- "Redis is a database replacement."
- "NoSQL doesn't have schemas."
- "MongoDB doesn't support transactions."
- "PUT and PATCH are exactly the same."
- "GET is always faster than POST."
- "I know everything in my tech stack."
- "I can learn anything instantly."
- "My weakness is perfectionism."
- "I will definitely stay for exactly X years."
- "I want Userfacet because it is a good company."

Prefer nuanced answers that explain **trade-offs**.

---

# 64. Final Preparation Strategy

## If you have 1 day

### First 3 hours

- HugnLove deep dive
- Encode deep dive
- Cart package
- Internship

### Next 3 hours

- JavaScript
- Node
- Express
- MongoDB/Mongoose
- Redis

### Next 2 hours

- SQL/DBMS
- OS
- DSA

### Final 1--2 hours

Speak answers aloud:

- Introduction
- Why Userfacet
- Why backend/full-stack
- Strengths
- Weaknesses
- 5-year plan
- Higher offer question
- Project explanation

---

# 65. Final Rules

### Rule 1 --- Know your code

If it is on the resume, assume they can ask you to open the repository
and write it again.

### Rule 2 --- Never bluff

A strong:

> "I don't remember the exact detail, but here's how I would approach
> it..."

is better than a confidently incorrect answer.

### Rule 3 --- Explain trade-offs

Instead of:

> "I used Redis because it is fast."

say:

> "The QR output is deterministic, so repeated identical requests don't
> need to regenerate the image. Redis lets me cache that result with low
> latency. The trade-off is cache memory and the need to handle cache
> misses/failures."

### Rule 4 --- Think aloud during coding

Explain:

- assumptions
- brute force
- optimized approach
- complexity
- edge cases
- implementation

### Rule 5 --- Behavioral answers must be consistent

Your answers about:

- why backend
- why Userfacet
- five-year plan
- strengths
- weaknesses
- commitment

should not contradict each other.

### Rule 6 --- Don't memorize this document word-for-word

Use the answers as **answer structures**. Your spoken version should
sound like you.

---

# Sources

- Ravish Ranjan submitted resume --- primary source for all
resume-specific questions and claims.
- Userfacet interview experiences supplied in the conversation ---
used to identify recurring interview patterns and actual questions.
- Userfacet official website --- used only to update the "Why
Userfacet?" / current company-direction section.

 