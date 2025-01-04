# Assistants API

The Assistants API provides a flexible way to create AI assistants that can use tools and perform complex tasks.

## Creating an Assistant

```bash
curl https://api.openai.com/v1/assistants \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "instructions": "You are a personal math tutor. Write and run Python code to solve math problems.",
    "name": "Math Tutor",
    "tools": [{"type": "code_interpreter"}],
    "model": "gpt-4o"
  }'
```

## Available Tools

- `code_interpreter`: Execute Python code in a sandbox environment
- `file_search`: Search through uploaded files
- `function`: Call custom functions you define

## Threads and Runs

Assistants use threads to maintain conversation context and runs to process tasks:

### Create a Thread
```bash
curl https://api.openai.com/v1/threads \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d ''
```

### Create a Message
```bash
curl https://api.openai.com/v1/threads/{thread_id}/messages \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "role": "user",
    "content": "Solve this algebra problem: 2x + 3 = 7"
  }'
```

### Run the Assistant
```bash
curl https://api.openai.com/v1/threads/{thread_id}/runs \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -d '{
    "assistant_id": "asst_abc123"
  }'
```