Use this skill when you need to interact with the Agnes AI API for text, image, or video generation. The skill wraps the Agnes OpenAI-compatible endpoints.

## Setup
Ensure you have the following credentials stored in `credentials.yaml` under the `agnes` key:
- `AGNES_API_KEY`: your API key
- `AGNES_BASE_URL`: base URL (e.g., https://gptload.babo.pp.ua/proxy/agnes/v1)

## Usage
### Text generation
Use the `agnes` model (e.g., `agnes-2.0-flash`, `agens-2.5-pro-alpha`) via the chat/completions endpoint.

### Image generation
Use `agnes-image-2.1-flash` or similar via the images/generations endpoint.

### Video generation
Use `agnes-video-v2.0` via appropriate endpoint (if available).

## Example
```bash
curl -X POST "$AGNES_BASE_URL/images/generations" \
  -H "Authorization: Bearer $AGNES_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"agnes-image-2.1-flash","prompt":"A cute 3-year-old girl in a head-and-shoulders portrait, 512x512 square, Japanese 2D cartoon style inspired by Hayao Miyazaki, soft even studio lighting with gentle natural shadows, crisp edges, high resolution, expressive facial details. She wears the official Japan national football jersey (samurai blue base with white and red accents) and has 1-2 themed accessories: a small Japanese flag pin on the collar and a matching blue-white hair tie. Randomized traits: hairstyle (twin-tails, bob, or short curls), hair color (black, dark brown, or auburn), eye shape (large, rounded, slightly angled 15° to the right), eye color (bright hazel, green, or brown), face shape (oval or round), and a unique detail like freckles, dimples, or a tiny hair clip. Mood: playful, lively, cheerful with a bright authentic smile. Background: clean, subtle muted geometric pattern in team-complementary tones (soft blues and whites). No watermark, pure illustration.","n":1,"size":"512x512"}'
```