# 20 Niche Problems Only Senior Devs Can Solve
Text from the video, recorded 2026-11-25.

1. Double-spend
Idempotency-Key header

2. Ghost read
Row locks, atomic claims

3. Zombie charges
Provider-side idempotency key

4. Timezone drift
Store UTC, convert at edge

5. Poison pill
Dead-letter queue

6. Thundering herd
TTL jitter, request coalescing

7. Float rounding
Integer cents

8. Cascade retry
Backoff, jitter, circuit breaker

9. N+1 query
Eager load, DataLoader

10. Split-brain
Leader election, fencing tokens

11. Clock skew
Monotonic clocks

12. Cache stampede
Single-flight locks

13. Orphaned upload
Lifecycle rules, TTL

14. Lost update
Optimistic locking, version column

15. Hot partition
Write sharding, salting

16. Encoding mismatch
UTF-8 end to end

17. DST overlap
Store offset alongside

18. Partial outage
Bulkheads, timeouts

19. Infinite pagination
Cursor-based pagination

20. Retry duplicate
Dedupe table, unique constraints

Closing line: Which means the gap isn't IQ, it's 8 habits. Screenshot this list and paste it into Claude.
