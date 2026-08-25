# Learning Plan: APIs, Inference & Upstream Provider APIs

## Intro

This is a resource-discovery catalog, not a tutorial. It inventories the best specs, docs,
courses, tools, repos, communities, and practice ideas for mastering APIs end-to-end: designing
them (REST/GraphQL/gRPC/webhooks), securing them (auth, rate limiting), documenting them
(OpenAPI), testing them, and — specifically for this field — **consuming upstream model-inference
APIs** (OpenAI, Anthropic, Google Gemini, Groq, Hugging Face, etc.) including streaming,
token billing, embeddings, and function/tool calling. Every item below lists a real URL, a
one-line description, and Free/Paid status. A future agent should use this as the master index
when building actual learning notebooks, code-along exercises, and docs for the "APIs, Inference,
Upstream" item on the LearningRoadmap.

---

## 1. Foundational Docs & Specs

- **OpenAPI Specification (current, 3.2.0 / 3.1.2)** — https://spec.openapis.org/oas/ — the
  official, canonical REST API description-format spec; start here for anything OpenAPI/Swagger.
  Free.
- **OpenAPI Specification GitHub repo** — https://github.com/OAI/OpenAPI-Specification — spec
  source, changelogs, and release history (3.0 → 3.2). Free.
- **Swagger.io "What is OpenAPI"** — https://swagger.io/specification/ — more approachable
  explainer version of the spec with examples. Free.
- **GraphQL Specification (spec.graphql.org)** — https://spec.graphql.org/ — official language,
  type-system, validation, and execution spec, with versioned releases and a working draft. Free.
- **GraphQL.org "Learn" docs** — https://graphql.org/learn/ — official conceptual docs (queries,
  schema, mutations, subscriptions) that sit above the raw spec. Free.
- **gRPC official docs** — https://grpc.io/docs/ — getting-started guides, concepts, and
  per-language quickstarts (Go, Python, Java, C++, etc.). Free.
- **Protocol Buffers (protobuf) docs** — https://protobuf.dev/ — official IDL docs used to define
  gRPC services and messages. Free.
- **gRPC codelabs** — https://codelabs.developers.google.com/grpc — hands-on "Getting Started"
  labs for Go, Java, Python, Rust, C++. Free.
- **JSON:API specification** — https://jsonapi.org/format/ — spec for standardizing REST
  request/response shape (`application/vnd.api+json`), includes extensions/profiles. Free.
- **RFC 9110 — HTTP Semantics** — https://www.rfc-editor.org/rfc/rfc9110.html — current IETF spec
  defining HTTP methods, status codes, headers, content negotiation (obsoletes RFC 7231). Free.
- **RFC 9112 — HTTP/1.1 Message Syntax** — https://httpwg.org/specs/ — wire-format companion to
  9110; the HTTP Working Group's spec index links HTTP/2 (RFC 9113) and HTTP/3 (RFC 9114) too.
  Free.
- **MDN HTTP reference & specs** — https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Resources_and_specifications
  — practitioner-friendly HTTP reference cross-linked to the underlying RFCs. Free.
- **OAuth 2.0 official site** — https://oauth.net/2/ — canonical OAuth2 framework overview and
  RFC links (RFC 6749 etc.). Free.
- **OAuth 2.0 Simplified (Aaron Parecki)** — https://www.oauth.com/ — widely recommended plain-
  English guide to every OAuth2 grant type and flow. Free (book also sold as paid print/PDF).
- **jwt.io** — https://jwt.io/ — official JWT debugger/decoder plus the JWT spec (RFC 7519)
  reference and library list. Free.

## 2. Best Websites / Blogs for API Design Best Practices

- **Postman Blog — REST API Best Practices** — https://blog.postman.com/rest-api-best-practices/
  — practical, frequently updated best-practices writeup from the biggest API tooling vendor.
  Free.
- **Swagger/SmartBear Blog — API Design Best Practices** — https://swagger.io/blog/api-design-best-practices/
  — OpenAPI-centric design guidance. Free.
- **Microsoft Azure Architecture — API Design Guidance** — https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design
  — enterprise-grade REST design guidance (resources, versioning, HATEOAS). Free.
  Companion: https://microsoft.github.io/code-with-engineering-playbook/design/design-patterns/rest-api-design-guidance/
- **Zuplo Learning Center** — https://zuplo.com/learning-center/ — deep, current articles on
  versioning, backward compatibility, mocking frameworks, gateways. Free.
- **Speakeasy API Design guides** — https://www.speakeasy.com/api-design/versioning/ — modern,
  SDK-generation-informed API design articles (versioning, schemas). Free.
- **ByteByteGo — REST API Cheatsheet & guides** — https://bytebytego.com/guides/rest-api-cheatsheet/
  — visual, widely shared system-design-style API guides. Free (ByteByteGo newsletter is free;
  their in-depth courses are paid).
- **APIs You Won't Hate** — https://apisyouwonthate.com/ — long-running, opinionated blog/book
  series specifically about pragmatic REST/JSON API design. Free blog, paid book bundle.
- **Stripe API docs (as a design reference)** — https://docs.stripe.com/api — treated by the
  industry as the gold-standard example of resource-oriented, versioned, well-documented REST
  API design; study its patterns directly. Free to read.
- **OWASP API Security Project** — https://owasp.org/www-project-api-security/ — home of the API
  Security Top 10 (see §8). Free.
- **Svix "Webhook University" & best-practices guides** — https://www.svix.com/resources/webhook-best-practices/
  and https://www.svix.com/resources/webhook-university/ — the most complete open guide to
  webhook design: signing, retries, idempotency, security. Free.

## 3. Free Courses (structured courses / YouTube series / MOOCs)

- **freeCodeCamp — "APIs for Beginners" (Full Course)** — https://www.youtube.com/watch?v=WXsD0ZgxjRw
  (article: https://www.freecodecamp.org/news/apis-for-beginners-full-course/) — beginner-
  friendly full course: what APIs are, Postman, JS/Python clients, building a small API. Free.
- **freeCodeCamp — "Python API Development – Comprehensive Course for Beginners"** —
  https://www.freecodecamp.org/news/creating-apis-with-python-free-19-hour-course/ — ~19 hours,
  FastAPI + SQL + testing + CI/CD, builds a real production-style API. Free.
- **freeCodeCamp — "Full HTTP Networking Course – Fetch and REST APIs in JavaScript"** —
  https://www.youtube.com/watch?v=2JYT5f2isg4 — deep dive on HTTP + Fetch + REST consumption from
  the client side. Free.
- **How to GraphQL** — https://www.howtographql.com/ — free, open-source, fullstack GraphQL
  tutorial site from fundamentals to production, with Apollo Server/Client tracks (JS, TS, Go,
  Ruby backends + React frontend). Free.
- **Postman Academy — "API Fundamentals Student Expert" path** — https://academy.postman.com/path/postman-api-fundamentals-student-expert
  — free, self-paced (1.5–3 hrs), beginner API + Postman certification with a digital badge.
  Free. (Note: some student-badge mechanics have changed per Postman community posts — check
  current status.)
- **Postman Academy — full course catalog** — https://academy.postman.com/page/course-catalog —
  broader set of free self-paced Postman/API courses (API testing, mocking, contract testing).
  Free.
- **roadmap.sh — Backend Developer Roadmap** — https://roadmap.sh/backend — free interactive
  roadmap covering HTTP, REST, auth, caching, and API design as part of the full backend path.
  Free (roadmap.sh also sells paid guided courses/projects).
- **Kong Academy / Kong Gateway "For Beginners"** — https://konghq.com/resources/videos/kong-gateway-for-beginners
  and official docs quickstart https://developer.konghq.com/gateway/get-started/ — free
  hands-on intro to API gateway concepts using Kong. Free.
- **Grafana k6 "Get started with k6" tutorials** — https://grafana.com/docs/k6/latest/examples/get-started-with-k6/
  — free official tutorial series for API load/performance testing. Free.
- **Google Codelabs — Gemini function calling** — https://codelabs.developers.google.com/codelabs/gemini-function-calling
  — free hands-on lab specifically on model-inference function calling. Free.

## 4. Paid Courses (clearly labeled, only if exceptionally well regarded)

- **"REST API Design, Development & Management" (Udemy, Rajeev Sakhuja)** —
  https://www.udemy.com/course/rest-api-analyzedesigndevelopsecuretestandmanage/ — one of the
  longest-running, most comprehensive REST design/dev/security/testing courses on Udemy
  (frequently discounted from ~$120). Paid.
- **"Software Architecture: REST API Design – The Complete Guide" (Udemy)** —
  https://www.udemy.com/course/rest-api-design-the-complete-guide/ — architecture-first REST
  design course, good for intermediate/senior devs. Paid.
- **"Master API Design, Access and Authorization" (Udemy)** —
  https://www.udemy.com/course/master-api-design-authentication-and-authorization/ — focused on
  versioning, error handling, auth/authorization patterns. Paid.
- **Class Central API Design directory** — https://www.classcentral.com/subject/api-design —
  aggregator that surfaces the current best-reviewed paid (Coursera/Udemy/edX) and free courses;
  useful to re-check ratings before enrolling since course quality/pricing shifts. Free to browse
  (courses themselves may be paid).
- **ByteByteGo "System Design Interview" course (includes API/rate-limiter design)** —
  https://bytebytego.com/courses/system-design-interview/design-a-rate-limiter — well-regarded
  premium system-design course with a dedicated rate-limiter/API design module. Paid
  (ByteByteGo Pro subscription).

## 5. Interactive Labs / Sandboxes

- **JSONPlaceholder** — https://jsonplaceholder.typicode.com/ — the most common free fake REST
  API for practicing GET/POST/PUT/DELETE against posts/comments/users/todos. Free, no auth.
- **ReqRes** — https://reqres.in/ — sandbox API modeling login/register flows, good for practicing
  auth-shaped requests. Free.
- **DummyJSON** — https://dummyjson.com/ — richer fake datasets (products, carts, users, quotes)
  for frontend/API practice. Free.
- **GoREST** — https://gorest.co.in/ — more realistic public sandbox: real CRUD persistence,
  bearer-token auth, and rate limits — best for practicing actual auth + rate-limit handling.
  Free tier, paid tier for higher limits.
- **RestSimulator** — https://restsimulator.com/ — simulates slow/flaky/failing/rate-limited APIs
  — great for practicing resilient client code (retries, timeouts, backoff). Free.
- **Mockoon** — https://mockoon.com/ — free desktop app + CLI to spin up your own mock REST API
  locally with a GUI, no coding required. Free (open source), with a paid Cloud tier for team
  sharing.
- **Postman Public API Network / Public Workspaces** — https://www.postman.com/explore — browse
  and fork thousands of public Postman collections against real third-party APIs. Free.
- **Beeceptor virtual sandbox** — https://beeceptor.com/virtual-sandbox/explore/ — instant mock
  APIs and request-inspection sandbox in the browser. Free tier, paid for advanced usage.
- **public-apis / public-apis (GitHub)** — https://github.com/public-apis/public-apis — a huge
  curated list of free real-world public APIs to practice consuming (weather, finance, etc.).
  Free.
- **Apollo GraphQL "Fullstack Tutorial" server** — bundled in howtographql.com above — spins up a
  toy GraphQL server/client for hands-on practice. Free.

## 6. GitHub Repos Worth Studying

- **Kikobeats/awesome-api** — https://github.com/Kikobeats/awesome-api — curated list of RESTful
  API design/implementation resources. Free.
- **yosriady/awesome-api-devtools** — https://github.com/yosriady/awesome-api-devtools — curated
  tools for building RESTful HTTP+JSON APIs. Free.
- **marmelab/awesome-rest** — https://github.com/marmelab/awesome-rest — collaborative list on
  REST architecture, development, testing, performance. Free.
- **Treblle/awesome-api-tools** — https://github.com/Treblle/awesome-api-tools — curated tools,
  tutorials, resources across the whole API ecosystem (design, testing, security, gateways).
  Free.
- **dwyl/learn-api-design** — https://github.com/dwyl/learn-api-design — concise guide/checklist
  on how to design a good API, aimed at learners. Free.
- **stepci/awesome-api-clients** — https://github.com/stepci/awesome-api-clients — curated list
  of API client generation/testing tools. Free.
- **APIs-guru/openapi-directory** — https://github.com/APIs-guru/openapi-directory — the largest
  directory of real-world OpenAPI 2.0/3.x specs (Slack, Twilio, GitHub, etc.) — excellent for
  studying how big companies structure their specs. Free.
- **GitHub REST API OpenAPI description** — https://github.com/github/rest-api-description —
  GitHub's own REST API fully described in OpenAPI — a mature, huge, real-world spec to read.
  Free.
- **stripe/openapi** — https://github.com/stripe/openapi — Stripe's public OpenAPI spec; read
  this alongside their docs to see gold-standard resource modeling in raw spec form. Free.
- **wiremock/wiremock** — https://github.com/wiremock/wiremock (see also https://wiremock.org/) —
  read the source and docs of the most widely used JVM API-mocking/stubbing tool. Free (OSS core,
  paid WireMock Cloud tier exists).
- **grafana/k6** — https://github.com/grafana/k6 — read the source of a modern load-testing tool
  built specifically around scripting realistic API load tests. Free (OSS, paid Grafana Cloud
  k6 tier exists).
- **redocly/redoc** — https://github.com/redocly/redoc — source of the most widely used
  OpenAPI-to-docs renderer; good for understanding how OpenAPI specs map to generated docs. Free
  (OSS core, paid Redocly platform).
- **groq/groq-api-cookbook** — https://github.com/groq/groq-api-cookbook — real example code for
  calling an OpenAI-compatible inference API (Groq), streaming, and tool use. Free.
- **openai/openai-python** and **anthropic/anthropic-sdk-python** (search github.com/openai,
  github.com/anthropics) — first-party official SDK source — read the client internals to see how
  a production inference client handles retries, streaming, and typed schemas. Free.

## 7. Tools Worth Learning Deeply

### API design / testing clients
- **Postman** — https://www.postman.com/ / docs: https://learning.postman.com/ — the
  industry-standard all-in-one API client (design, test, mock, monitor, document, collaborate).
  Free tier; Paid (Basic/Professional/Enterprise) for team features.
- **Insomnia** — https://insomnia.rest/ — fast, lightweight REST/GraphQL/gRPC client, popular
  alternative to Postman. Free (OSS core); Paid Cloud/Team tiers.
- **Bruno** — https://www.usebruno.com/ — Git-native API client that stores collections as plain
  files in your repo instead of a cloud workspace — great fit for version-controlled API testing.
  Free, open source.
- **Stoplight (by SmartBear)** — https://stoplight.io/ — design-first, OpenAPI-centric platform
  for spec editing, mocking, and documentation collaboration. Free tier; Paid for teams.
- **HTTPie** — https://httpie.io/ — friendly CLI HTTP client, excellent for quick terminal-based
  API exploration. Free (CLI); Paid desktop/cloud tiers.
- **curl** — https://curl.se/docs/ — the universal baseline HTTP CLI tool every API developer
  must be fluent in. Free.

### API gateways
- **Kong Gateway** — https://developer.konghq.com/gateway/ — lightweight, plugin-based,
  cloud-native API gateway; strong docs and quickstarts. Free (OSS); Paid Kong Konnect/Enterprise.
- **AWS API Gateway** — https://docs.aws.amazon.com/apigateway/ — fully managed gateway tightly
  integrated with AWS services (Lambda, IAM, etc.). Paid (usage-based AWS pricing).
- **Apigee (Google Cloud)** — https://cloud.google.com/apigee/docs — enterprise-grade API
  management platform with strong governance/analytics. Paid.
- **Kong AI Gateway** — https://developer.konghq.com/ai-gateway/ — gateway features specifically
  for proxying/managing LLM inference API traffic (rate limiting, key management, multi-provider
  routing). Free (OSS core); Paid Enterprise features.

### Mocking / contract tools
- **WireMock** — https://wiremock.org/ — the standard tool for programmable, stateful HTTP
  stubbing in CI/tests, supports fault injection and record/replay. Free (OSS); Paid WireMock
  Cloud.
- **Mockoon** — https://mockoon.com/ — GUI-based local mock server, fastest way to fake an API
  without writing code. Free (OSS); optional paid Cloud.
- **Prism (Stoplight)** — https://github.com/stoplightio/prism — spins up a mock server directly
  from an OpenAPI spec and validates real requests against it. Free, open source.

### Documentation generators
- **Swagger UI** — https://swagger.io/tools/swagger-ui/ — renders OpenAPI specs into an
  interactive "Try it out" console; the most common way to expose live API docs. Free (OSS);
  Paid SwaggerHub for team management.
- **Redoc** — https://github.com/redocly/redoc — clean, read-focused three-column OpenAPI doc
  renderer, popular for public-facing reference docs. Free (OSS core); Paid Redocly platform.
- **Scalar** — https://guides.scalar.com/ — modern OpenAPI doc UI with an integrated request
  console, increasingly popular Swagger UI alternative. Free (OSS); Paid hosted tier.
- **Docusaurus** — https://docusaurus.io/ — general docs-site generator (guides + reference),
  often paired with an OpenAPI plugin for full developer-portal sites. Free, open source.

### Load / performance testing
- **k6 (Grafana)** — https://k6.io/ / docs: https://grafana.com/docs/k6/latest/ — modern,
  JavaScript-scripted load testing tool with thresholds and scenario-based ramping, purpose-built
  for API load testing. Free (OSS); Paid Grafana Cloud k6.

### Security scanning
- **OWASP ZAP** — https://www.zaproxy.org/ — free, open-source API/web security scanner, good for
  hands-on OWASP API Top 10 practice. Free.
- **42Crunch API Security testing** — https://42crunch.com/ — dedicated OpenAPI-spec security
  auditing/linting tooling. Free tier + Paid.

## 8. Authentication / Security Learning Resources

- **OAuth.com ("OAuth 2.0 Simplified")** — https://www.oauth.com/ — the most recommended
  beginner-to-advanced OAuth2 guide, covering every grant type with real examples. Free.
- **OWASP OAuth2 Cheat Sheet** — https://cheatsheetseries.owasp.org/cheatsheets/OAuth2_Cheat_Sheet.html
  — security pitfalls and hardening guidance specific to OAuth2 implementations. Free.
- **jwt.io + JWT Best Current Practice (RFC 8725) guidance** — https://jwt.io/ and Auth0's summary
  https://auth0.com/blog/a-look-at-the-latest-draft-for-jwt-bcp/ — canonical JWT structure debugger
  plus the current JWT security best-practices RFC discussion. Free.
- **Curity — JWT Best Practices** — https://curity.io/resources/learn/jwt-best-practices/ —
  practical checklist: algorithm pinning, claim validation, short lifetimes, key rotation. Free.
- **OWASP REST Security Cheat Sheet** — https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html
  — REST-specific security checklist (input validation, auth, transport security). Free.
- **OWASP API Security Top 10 (2023)** — https://owasp.org/API-Security/editions/2023/en/0x11-t10/
  — the definitive top-10 API vulnerability list (Broken Object Level Authorization, Broken
  Authentication, Unrestricted Resource Consumption, SSRF, etc.) — essential reading for anyone
  building or consuming APIs. Free.
- **Google Cloud — API key best practices** — https://cloud.google.com/docs/authentication/api-keys-best-practices
  — concrete guidance on scoping, restricting, and rotating API keys. Free.
- **OpenAI — Best practices for API key safety** — https://help.openai.com/en/articles/5112595-best-practices-for-api-key-safety
  — provider-specific guidance directly relevant to calling inference APIs safely. Free.
- **GitGuardian — Secrets & API management blog** — https://blog.gitguardian.com/secrets-api-management/
  — practical secrets/vault rotation guidance. Free.
- **Arcjet — Rate Limiting Algorithms Explained (token bucket vs sliding window vs fixed window)**
  — https://blog.arcjet.com/rate-limiting-algorithms-token-bucket-vs-sliding-window-vs-fixed-window/
  — clear comparison with implementation guidance. Free.
- **ByteByteGo — "Design a Rate Limiter"** — https://bytebytego.com/courses/system-design-interview/design-a-rate-limiter
  — deep-dive on production rate-limiter design (token bucket, leaky bucket, sliding window log).
  Paid (part of ByteByteGo's system design interview course).

## 9. Forums / Communities

- **r/webdev** — https://www.reddit.com/r/webdev/ — largest general web/API practitioner
  community; good for real-world implementation questions. Free.
- **r/programming** — https://www.reddit.com/r/programming/ — higher-level API design/architecture
  discussion and link-sharing. Free.
- **r/learnprogramming** — https://www.reddit.com/r/learnprogramming/ — best for absolute beginner
  API questions. Free.
- **r/FastAPI** — https://www.reddit.com/r/FastAPI/ — focused community if building APIs in
  Python/FastAPI. Free.
- **r/softwarearchitecture** — https://www.reddit.com/r/softwarearchitecture/ — good for deeper
  API design/architecture tradeoff discussions. Free.
- **Stack Overflow tags** — `rest`, `api-design`, `graphql`, `grpc`, `openapi`, `oauth-2.0`, `jwt`
  — https://stackoverflow.com/questions/tagged/api-design (and similarly-tagged pages) — the
  default Q&A reference for specific implementation errors. Free.
- **Postman Community Forum** — https://community.postman.com/ — official forum for Postman/API
  testing questions, including certification/program status updates. Free.
- **Discord — Discord Developers server** — https://discord.com/developers/docs/getting%5C-started
  (join link surfaced via Discord Developer Portal) — official community for API support,
  announcements, events. Free.
- **awesome-dev-discord (GitHub list)** — https://github.com/ljosberinn/awesome-dev-discord — a
  curated list of active developer Discord servers, several backend/API focused. Free.

## 10. YouTube Channels

- **Hussein Nasser** — https://www.youtube.com/@hnasr — backend fundamentals: HTTP internals,
  databases, networking, API design/performance tradeoffs, gRPC vs REST deep dives. Free.
- **ByteByteGo** — https://www.youtube.com/@ByteByteGo — visual system-design explainers, several
  specifically on API design, rate limiting, and API gateways. Free (channel); Paid courses/books
  on their site.
- **freeCodeCamp.org** — https://www.youtube.com/@freecodecamp — full-length free courses
  covering REST, GraphQL, FastAPI, and general backend/API development. Free.
- **Traversy Media** — https://www.youtube.com/@TraversyMedia — practical project-based tutorials
  including REST API crash courses across multiple stacks. Free.
- **Apollo GraphQL (official channel)** — search "Apollo GraphQL YouTube" — official talks and
  tutorials on GraphQL server/client patterns. Free.

## 11. Inference / Model-API Specific Resources

### Hosted model-inference provider docs
- **OpenAI API reference & docs** — https://platform.openai.com/docs/api-reference and
  https://developers.openai.com/api/docs — the Responses/Chat Completions APIs, streaming events,
  function/tool calling, embeddings. Free to read; Paid (usage-based) to call.
- **OpenAI — Embeddings guide** — https://developers.openai.com/api/docs/guides/embeddings —
  `POST /v1/embeddings`, vector dimensions, cosine-similarity recommendation. Free docs; Paid API
  usage.
- **OpenAI — Pricing** — https://developers.openai.com/api/docs/pricing — token-based billing
  rates (separate input/output token pricing, cached-input discounts). Free to read.
- **Anthropic (Claude) API docs** — https://platform.claude.com/docs/en/home — Messages API,
  streaming, tool use, fine-grained tool-argument streaming. Free docs; Paid usage.
- **Anthropic — Claude API Primer** — https://platform.claude.com/docs/en/claude_api_primer —
  concise overview of the Messages API request/response model. Free.
- **Google Gemini API docs** — https://ai.google.dev/gemini-api/docs — function calling,
  streaming (`streamGenerateContent`), multimodal input. Free docs; Paid usage (free tier
  available).
- **Google Gemini — Function calling guide** — https://ai.google.dev/gemini-api/docs/function-calling
  and streaming guide https://ai.google.dev/gemini-api/docs/streaming — concept + code for
  tool-calling and streamed responses. Free.
- **Vertex AI generative AI docs (Google Cloud)** — https://docs.cloud.google.com/vertex-ai/generative-ai/docs
  — enterprise-grade hosted inference, same Gemini models via GCP. Paid (GCP usage-based).
- **Groq API docs** — https://console.groq.com/docs/overview — extremely fast inference,
  explicitly OpenAI-compatible (`base_url: https://api.groq.com/openai/v1`), good for learning how
  provider-compatible APIs work. Free tier; Paid for higher throughput.
- **Groq API reference / rate limits** — https://console.groq.com/docs/api-reference and
  https://console.groq.com/docs/rate-limits — concrete example of published per-model rate limits
  on a real inference API. Free to read.
- **Hugging Face Inference Providers / Serverless Inference API** —
  https://huggingface.co/docs/inference-providers/en/index — calling open models via a unified
  serverless API, OpenAI-compatible routing options. Free tier (rate-limited); Paid for dedicated
  Inference Endpoints (https://huggingface.co/docs/inference-endpoints/en/faq).
- **AWS Bedrock — Anthropic Claude model parameters** — https://docs.aws.amazon.com/bedrock/latest/userguide/model-parameters-anthropic-claude-messages.html
  — how a major cloud exposes third-party model APIs behind its own inference API surface. Paid
  (AWS usage-based).

### Core inference concepts
- **Streaming responses (SSE) concept** — covered across OpenAI/Anthropic/Gemini docs above;
  general background: https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events —
  understand Server-Sent Events, since most inference APIs stream tokens this way. Free.
- **Token-based billing explainer** — https://developers.openai.com/api/docs/pricing plus general
  breakdown articles like https://www.solvimon.com/glossary/ai-token-pricing — input vs output
  token pricing, cached-input/batch discounts, ~750 words per 1,000 tokens rule of thumb. Free.
- **Function-calling / tool-calling concept** — https://developers.openai.com/api/docs/guides/function-calling
  (OpenAI) and https://ai.google.dev/gemini-api/docs/function-calling (Gemini) — the model
  returns a structured call; your app executes it and returns the result. Free.
- **Prompt/response schema design (structured outputs)** — https://platform.openai.com/docs/guides/structured-outputs
  — constraining model output to a JSON schema, directly relevant to building reliable API
  integrations around LLMs. Free docs; Paid usage.
- **Local vs upstream inference tradeoffs** — comparative articles:
  https://apidog.com/blog/local-vs-api-ai-models/ and
  https://thebootstrappedfounder.com/when-to-choose-local-llms-vs-apis-a-founders-real-world-guide/
  — cost, latency, privacy, and scaling tradeoffs between self-hosted (vLLM, Ollama, llama.cpp)
  and hosted inference APIs. Free.
- **vLLM docs** — https://docs.vllm.ai/ — high-throughput self-hosted inference server, good to
  study as the "upstream API you'd build yourself" if self-hosting at scale. Free, open source.
- **Ollama docs** — https://ollama.com/ — simplest way to run a local model with an
  OpenAI-compatible local API, good for comparing local vs hosted API shapes hands-on. Free.
- **llama.cpp** — https://github.com/ggml-org/llama.cpp — lightweight local inference engine
  (including its own local HTTP server mode) — useful to read for understanding inference
  serving internals. Free, open source.

## 12. Practice Project Ideas

- **Build and document your own REST API** — e.g. a Task Manager or Expense Tracker API with
  auth, CRUD, pagination/filtering, validation, and a published OpenAPI spec + Swagger UI/Redoc
  docs. See idea lists: https://roadmap.sh/backend/project-ideas and
  https://strapi.io/blog/api-project-ideas.
- **Build a GraphQL API** — follow How to GraphQL's backend track
  (https://www.howtographql.com/) to build a small Apollo Server-based API (e.g. a blog or
  notes app) exposing queries, mutations, and subscriptions.
- **Build a client wrapper/SDK around a public API** — pick one API from
  https://github.com/public-apis/public-apis, write a typed client library with retries, rate-
  limit handling, and pagination helpers — mirrors what real inference SDKs (openai-python,
  anthropic-sdk) do.
- **Build a small API gateway/proxy** — implement a minimal reverse proxy in front of 2+ upstream
  APIs (or Kong https://developer.konghq.com/gateway/) that adds auth, rate limiting, and request
  logging — directly useful background for understanding how inference-API gateways (e.g. Kong
  AI Gateway) work.
- **Build an inference-API wrapper/chat CLI** — call OpenAI/Anthropic/Groq/Gemini via their
  official SDKs, implement streaming output, token-usage tracking/cost estimation, and a
  function-calling tool (e.g. a weather or calculator tool) — the most directly relevant project
  for the "inference/upstream" part of this field.
- **Build a mock-then-real integration** — start against a Prism-generated mock server from an
  OpenAPI spec (https://github.com/stoplightio/prism), then swap in the real upstream API once
  the client is stable — practices contract-first development.
- **Load-test your own API** — write a k6 script (https://k6.io/) against your own REST API to
  practice thresholds, ramping scenarios, and interpreting latency percentiles.
- **Webhook receiver project** — implement an HMAC-signature-verifying webhook receiver following
  Svix's best practices (https://www.svix.com/resources/webhook-best-practices/) with idempotent
  processing and a background job queue.

## 13. Cheat Sheets / Quick-Reference Roadmaps

- **ByteByteGo — REST API Cheatsheet** — https://bytebytego.com/guides/rest-api-cheatsheet/ —
  compact visual cheat sheet covering naming, status codes, pagination, versioning. Free.
- **RestCheatSheet/api-cheat-sheet (GitHub)** — https://github.com/RestCheatSheet/api-cheat-sheet
  — long-running community-maintained REST API design cheat sheet. Free.
- **devhints.io — REST API cheat sheet** — https://devhints.io/rest-api — quick-reference status
  codes/verbs/headers cheat sheet. Free.
- **OWASP REST Security Cheat Sheet** — https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html
  — security-specific quick reference (see §8). Free.
- **roadmap.sh — Backend Developer Roadmap (interactive)** — https://roadmap.sh/backend — visual
  roadmap placing API design/HTTP/auth/versioning in the context of the full backend skill tree.
  Free (paid guided courses optional).
- **api-patterns.org cheatsheet** — https://api-patterns.org/cheatsheet — pattern-oriented
  reference (pagination, filtering, async operations, versioning patterns). Free.

---

## Suggested Learning Progression

### Beginner
1. Read MDN's HTTP reference and skim RFC 9110 section headers to internalize methods/status
   codes (§1).
2. Do freeCodeCamp's "APIs for Beginners" full course (§3) and practice against JSONPlaceholder /
   ReqRes / GoREST (§5).
3. Get the free Postman Academy "API Fundamentals" badge (§3) while learning the Postman client
   (§7).
4. Read the ByteByteGo REST cheat sheet and the RestCheatSheet GitHub list (§13) as a running
   checklist.
5. Learn OAuth2 basics via OAuth.com and JWT structure via jwt.io (§8).

### Intermediate
1. Read the OpenAPI Specification (§1) and practice writing a spec for a toy API; render it with
   Swagger UI and Redoc (§7).
2. Build your own REST API project (§12) with auth, pagination, validation, and versioning
   (read Zuplo's versioning guide, §2).
3. Learn GraphQL via How to GraphQL (§3) and build a small GraphQL API.
4. Study Stripe's and GitHub's real OpenAPI specs (§6) to see production-grade design.
5. Learn rate limiting (token bucket vs sliding window, §8) and implement one in your own API.
6. Read the OWASP API Security Top 10 and retrofit your project against it (§8).
7. Add mocking (Mockoon/Prism) and a k6 load test to your project (§7, §12).

### Advanced
1. Learn gRPC + protobuf (§1) and reimplement one endpoint of your REST API as gRPC to compare
   tradeoffs.
2. Study webhooks end-to-end via Svix's guides and implement a signed webhook receiver (§2, §12).
3. Set up an API gateway (Kong) in front of your services and add auth/rate-limiting plugins
   (§7).
4. Move into the **inference/upstream** track (§11): call OpenAI, Anthropic, Gemini, and Groq
   APIs directly — implement streaming, token-usage/cost tracking, embeddings, and
   function/tool-calling in one client wrapper project.
5. Compare hosted inference vs self-hosted (vLLM/Ollama/llama.cpp) by running the same prompt
   through both and measuring latency/cost/quality (§11).
6. Optionally pursue a well-regarded paid course (§4) or the ByteByteGo rate-limiter/system-design
   material to deepen production-scale API design skills.
