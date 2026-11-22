# groceries

An example of application idea development in an area that has been a pain point for a long time.

This repo does not contain an app. It shows the first steps of turning a rough idea into a clear product definition with the help of an AI chat, and it keeps every step so you can see how each one led to the next.

## How to read this

Read the five files in `docs/` in order. Each one is a single step, and each is marked by how it was made: by hand, in an AI chat, or AI-assisted. Take what is useful and adapt the process to your own idea and your own needs.

| Step | File | How it was made | What to notice |
| --- | --- | --- | --- |
| 1 | [The raw idea](docs/01-raw-idea.md) | Written by hand | Two short paragraphs are enough to start. |
| 2 | [Chat: finding skills](docs/02-chat-finding-skills.md) | AI chat (Gemini) | Asking what "skills" exist and how to use them in a free web chat. |
| 3 | [Chat: building the mentor prompt](docs/03-chat-building-mentor.md) | AI chat (Gemini) | Combining a product-management method with the grill-me interview style into one prompt. |
| 4 | [The master mentor prompt](docs/04-pm-grill-mentor.md) | Extracted from the chat in step 3 | A reusable prompt: one question at a time, four layers, sign-off before moving on. |
| 5 | [Layer 1: product 1-pager](docs/05-layer1-one-pager.md) | AI-assisted | What the raw idea became after one question-and-answer session with the mentor. |

A good way to see the effect is to compare step 1 with step 5: the same idea, before and after being questioned.

## Try it yourself

1. Write your own idea down in a few sentences, without AI.
2. Copy the prompt from [step 4](docs/04-pm-grill-mentor.md) into a new chat in any AI assistant and add your idea underneath.
3. Answer one question at a time. Agree with the mentor's recommendation, change it, or push back. "I don't know" is a valid answer.
4. When the mentor produces the 1-pager, save it as a file before going further.

## What's next

The mentor prompt defines four layers. Only Layer 1 is done here. Layers 2–4 (value map, MVP scope, detailed requirements) are still to come.
