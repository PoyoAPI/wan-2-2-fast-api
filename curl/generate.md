# Wan 2.2 Fast cURL Examples

Use these requests to submit a Wan 2.2 Fast task and poll for the result.

## Generate

```bash
export POYO_API_KEY="YOUR_POYO_API_KEY_HERE"
export POYO_BASE_URL="https://api.poyo.ai"

curl --fail-with-body --request POST \
  --url "$POYO_BASE_URL/api/generate/submit" \
  --header "Authorization: Bearer $POYO_API_KEY" \
  --header "Content-Type: application/json" \
  --data '{
  "model": "wan2.2-text-to-video-fast",
  "input": {
    "prompt": "A fast draft video of a small ceramic lantern on a wooden desk, soft daylight, slow push-in camera, realistic motion, no text, no logo, no watermark.",
    "duration": 5,
    "resolution": "720p",
    "aspect_ratio": "16:9"
  }
}'
```

Store the returned `data.task_id`, then poll:

```bash
curl --fail-with-body --request GET \
  --url "$POYO_BASE_URL/api/generate/status/task-unified-example" \
  --header "Authorization: Bearer $POYO_API_KEY"
```

## Image To Video With Guide Frames

```json
{
  "model": "wan2.2-image-to-video-fast",
  "input": {
    "prompt": "Animate this product reference into a subtle desk-scene motion draft, no text, no logo, no watermark.",
    "image_urls": [
      "https://example.com/start-frame.png",
      "https://example.com/end-frame.png"
    ],
    "resolution": "720p",
    "duration": 5,
    "aspect_ratio": "16:9"
  }
}
```

## Expected Submit Response

```json
{
  "code": 200,
  "data": {
    "task_id": "task-unified-example",
    "status": "not_started",
    "created_time": "2026-07-06T08:00:00"
  }
}
```

## Expected Status Response

```json
{
  "code": 200,
  "data": {
    "task_id": "task-unified-example",
    "status": "finished",
    "progress": 100,
    "files": [
      {
        "file_url": "https://storage.poyo.ai/generated/output-file",
        "file_type": "media"
      }
    ],
    "error_message": null
  }
}
```
