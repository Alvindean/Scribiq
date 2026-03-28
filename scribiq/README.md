# Scribiq — AI Writing Studio

A single-page AI writing app with 80+ tools across 10 specialized writing tabs. Deployed on Vercel with real-time streaming via Claude (Anthropic or OpenRouter).

---

## Project Structure

```
scribiq/
├── api/
│   ├── generate.js   ← AI API proxy (non-streaming)
│   └── stream.js     ← Streaming SSE endpoint
├── public/
│   └── index.html    ← Full app (HTML + CSS + JS)
├── vercel.json
└── package.json
```

---

## Writing Tabs

| Tab | Description |
|---|---|
| **Write** | General-purpose writing tools — blog posts, articles, outlines, intros, conclusions, and more |
| **Copy** | Copywriting tools — headlines, taglines, product descriptions, CTAs, ad copy, and sales pages |
| **Email** | Email writing — cold outreach, follow-ups, newsletters, subject lines, and auto-replies |
| **Social** | Social media content — posts, captions, thread ideas, bios, and platform-specific copy |
| **Script** | Video and podcast scripts — YouTube scripts, explainer videos, intros/outros, and voiceovers |
| **Screen** | Screenwriting tools — scene descriptions, dialogue, loglines, treatments, and character bios |
| **Book** | Long-form book writing — chapter drafts, blurbs, back-cover copy, query letters, and synopses |
| **Story** | Creative fiction — short stories, prompts, character development, world-building, and plot outlines |
| **Edit** | Editing and rewriting — proofreading, tone adjustments, simplification, expansion, and rewrites |
| **Tools** | Utility tools — summarization, translation, keyword extraction, rephrasing, and content ideas |

---

## Deploy to Vercel

1. Push this repo to GitHub.
2. Go to [vercel.com](https://vercel.com) and import the repository.
3. Add the required environment variables (see table below).
4. Click **Deploy**.

---

## Local Development

```bash
npm install
cp .env.example .env.local   # add your API keys
npx vercel dev
```

The app runs at `http://localhost:3000`.

---

## Environment Variables

| Variable | Required | Description |
|---|---|---|
| `ANTHROPIC_API_KEY` | One of the two is required | API key from [console.anthropic.com](https://console.anthropic.com) |
| `OPENROUTER_API_KEY` | One of the two is required | API key from [openrouter.ai](https://openrouter.ai) |

At least one key must be set. If both are present, the app will use whichever is configured as the active provider.

---

## API Endpoints

| Endpoint | Description |
|---|---|
| `POST /api/generate` | Standard request/response generation |
| `POST /api/stream` | Server-sent events (SSE) for real-time streaming output |
