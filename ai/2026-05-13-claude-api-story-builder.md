# Building a Korean-to-English Story Builder with Claude API

**Date:** 2026-05-13  
**Source:** Personal project (koenko)

## What I Learned

Used the Anthropic Claude API to build a Flask web app that converts Korean personal memories into natural, conversational English stories. The key was crafting a system prompt that tells Claude to sound like a native speaker — not a formal translator.

## Why It Matters

Generic translation APIs (Google Translate, etc.) produce stiff, literal text. By using an LLM with a well-designed prompt, the output sounds like something a real person would actually say in conversation.

## Example

```python
client.messages.create(
    model="claude-sonnet-4-6",
    max_tokens=1024,
    system="You are a translator. Translate Korean to natural, casual spoken English. Sound like a native speaker having a real conversation.",
    messages=[{"role": "user", "content": korean_text}]
)
```

## Notes

- Claude API costs money at scale → planning to replace with Groq (free tier, LLaMA model)
- DeepL API has 500k free chars/month — better for pure translation
- ngrok is a quick way to expose a local server for mobile testing
