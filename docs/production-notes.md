# Production Notes

Use these examples from a backend service, not from browser code.

## Required Pattern

1. Keep `POYO_API_KEY` on the server.
2. Submit the generation task.
3. Store `data.task_id` in your database.
4. Poll status while testing.
5. Use `callback_url` webhooks in production.
6. Treat `finished` and `failed` as terminal states.

## Model-Specific Notes

- Use the image-to-video model when composition needs to stay anchored.
- Use the second guide image only when you need a planned ending frame.
- Treat failed or low-quality drafts as expected iteration, not final output.

## Reliability

- Retry only when the failure reason is transient.
- Avoid duplicate user charges by storing idempotency state in your own system.
- Copy final files to your own storage when your product needs long-term access.
