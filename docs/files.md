# Files API

The Files API allows you to upload and manage files that can be used with other OpenAI features.

## Uploading Files

```bash
curl https://api.openai.com/v1/files \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -F purpose="fine-tune" \
  -F file="@mydata.jsonl"
```

## File Limits

- Individual files: Up to 512 MB
- Total organization storage: Up to 100 GB
- File types: Depends on usage (fine-tuning, assistants, etc.)

## Listing Files

```bash
curl https://api.openai.com/v1/files \
  -H "Authorization: Bearer $OPENAI_API_KEY"
```

## Retrieving File Content

```bash
curl https://api.openai.com/v1/files/{file_id}/content \
  -H "Authorization: Bearer $OPENAI_API_KEY" > file.jsonl
```

## Deleting Files

```bash
curl https://api.openai.com/v1/files/{file_id} \
  -X DELETE \
  -H "Authorization: Bearer $OPENAI_API_KEY"
```