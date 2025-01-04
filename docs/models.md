# Models

The OpenAI API offers a variety of models with different capabilities and price points.

## Available Models

### GPT-4o Series
- `gpt-4o-mini`: Fastest and most cost-effective
- `gpt-4o`: Balanced performance and capabilities
- `gpt-4o-max`: Most capable model with highest context window

### Audio Models
- `whisper-1`: Speech to text transcription
- `tts-1`: Text to speech synthesis

### Image Models
- `dall-e-3`: Most advanced image generation
- `dall-e-2`: Legacy image generation

## Model Selection

Choose models based on your needs:
- For basic tasks: `gpt-4o-mini`
- For complex reasoning: `gpt-4o`
- For specialized tasks: Domain-specific fine-tuned models

## API Reference

### List Available Models
```bash
curl https://api.openai.com/v1/models \
  -H "Authorization: Bearer $OPENAI_API_KEY"
```

### Retrieve Model Information
```bash
curl https://api.openai.com/v1/models/gpt-4o \
  -H "Authorization: Bearer $OPENAI_API_KEY"
```