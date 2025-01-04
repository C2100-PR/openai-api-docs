# Chat Completions API

Create chat completions using OpenAI's most advanced language models.

## Creating Chat Completions

### Basic Request
```bash
curl https://api.openai.com/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "model": "gpt-4o-mini",
    "messages": [
      {"role": "system", "content": "You are a helpful assistant."},
      {"role": "user", "content": "Hello world!"}
    ]
  }'
```

### Request Parameters

- `model` (string, required): ID of the model to use
- `messages` (array, required): List of messages in the conversation
- `temperature` (number, optional): Controls randomness. Higher values = more random
- `top_p` (number, optional): Alternative to temperature, controls diversity
- `stream` (boolean, optional): Stream responses back in real time

### Response Format
```json
{
  "id": "chatcmpl-123",
  "object": "chat.completion",
  "created": 1677652288,
  "choices": [{
    "index": 0,
    "message": {
      "role": "assistant",
      "content": "Hello! How can I assist you today?"
    },
    "finish_reason": "stop"
  }]
}
```