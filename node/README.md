# Node.js example

Run a backend-only Wan 2.2 Fast API request with polling.

## Usage

```bash
cp ../.env.example ../.env
# edit ../.env and set POYO_API_KEY
npm start
```

The script submits a task, prints the returned task ID, then polls until the task reaches `finished` or `failed`.

Do not put `POYO_API_KEY` in frontend code.
