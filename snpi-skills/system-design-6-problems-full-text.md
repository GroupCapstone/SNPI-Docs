# System Design, 6 Problems
Spoken text from the video, recorded 2026-11-25.

Intro: I wish someone told me this on day one. System design is not a hundred things, it's six problems.

1. Scale reads
Too many reads? Add cache, add read replicas, index your database. Caching: hot data from memory. Read replicas: copies share the reads. DB indexing: skip full-table scans

2. Scale writes
Too many writes? Batch them, shard the database, or save it later. Batching: many writes, one trip. Sharding: split data across DBs. Async writes: ack now, save later

3. Real-time
Real-time? WebSockets, server-sent events, or long polling. WebSockets: two-way, always open. Server-sent events: server pushes, one-way. Long polling: hold until there's news

4. Background jobs
Slow jobs? Queue them. Workers pick them up. Message queue: park the work. Worker pool: jobs run in parallel

5. Reliability
Things will fail. Retries with backoff, idempotency, circuit breakers. Retries + backoff: wait longer each time. Idempotency: safe to run twice. Circuit breaker: stop calling the dead

6. Split reads & writes
Reads and writes fighting. Split them. That's CQRS

Closing line: Every system you'll ever design is one of these six. Which one scares you the most? Comment the number. And if this helped, hit like + follow for more.
