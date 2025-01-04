# Images API

The Images API allows you to generate and edit images.

## Image Generation

```bash
curl https://api.openai.com/v1/images/generations \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "model": "dall-e-3",
    "prompt": "A cute baby sea otter",
    "n": 1,
    "size": "1024x1024"
  }'
```

### Parameters
- `prompt`: Text description of the desired image(s)
- `n`: Number of images to generate (1-10)
- `size`: Image size (256x256, 512x512, or 1024x1024)
- `quality`: Image quality ("standard" or "hd")
- `style`: Image style ("vivid" or "natural")

## Image Editing

```bash
curl https://api.openai.com/v1/images/edits \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -F image="@original.png" \
  -F mask="@mask.png" \
  -F prompt="A cute baby sea otter wearing a beret" \
  -F n=1 \
  -F size="1024x1024"
```

## Image Variations

```bash
curl https://api.openai.com/v1/images/variations \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -F image="@original.png" \
  -F n=2 \
  -F size="1024x1024"
```

### Response Format
```json
{
  "created": 1589478378,
  "data": [
    {
      "url": "https://...",
      "revised_prompt": "A cute baby sea otter floating on its back..."
    }
  ]
}
```