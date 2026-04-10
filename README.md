# Are You a Ghost?

**A recruiter doesn't start with your resume. They start with a search. This tool shows you what that search finds — and where you rank.**

Built by [Wayne Rainey](mailto:wayne@thecareercantina.com) · [The Career Cantina](https://thecareercantina.com)

---

## What It Does

Most professionals assume LinkedIn is enough. This tool challenges that assumption with evidence, not advice.

Enter five inputs — your title, domain, geography, credential, and one proof deposit outside LinkedIn. The tool constructs the search string a recruiter would actually use, simulates what it finds across six sources, and returns your findability tier:

- **Rich** — Found across 4+ independent sources with corroborated detail
- **Partial** — Found in 2–3 sources. Present but fragmented
- **Thin** — Found in 1 source only, or name confirmed without professional context
- **Ghost** — No usable profile found across any of the six sources checked

The six sources checked, in order:
1. LinkedIn
2. ZoomInfo / RocketReach / ContactOut
3. Company or org website
4. Event programs & community mentions
5. Your network's activity
6. Public records aggregators

---

## Architecture

- **Frontend** — Single HTML file, no framework, mobile-first, light theme
- **Backend** — Netlify serverless function proxying the Anthropic API (Claude Opus)
- **Security** — API key stored as Netlify environment variable, never exposed client-side. Prompt injection guards on all inputs.

---

## Deploy Your Own

### 1. Clone the repo
```bash
git clone https://github.com/waynerainey/are-you-a-ghost.git
cd are-you-a-ghost
```

### 2. Install dependencies
```bash
npm install
```

### 3. Set your Anthropic API key in Netlify
In your Netlify dashboard → Site configuration → Environment variables:
```
ANTHROPIC_API_KEY = your_key_here
```

### 4. Deploy to Netlify
Connect the repo in the Netlify dashboard or use the CLI:
```bash
netlify deploy --prod
```

---

## Local Development
```bash
netlify dev
```
Requires the [Netlify CLI](https://docs.netlify.com/cli/get-started/) and a local `.env` file with `ANTHROPIC_API_KEY`.

---

## Related Tools

- [Career Triangulation Tool](https://career-triangulation.netlify.app) — Strategic career positioning diagnostic
- [The Career Cantina Article Library](https://thecareercantinalog.netlify.app) — Writing on AI-shaped hiring

---

## About

Wayne Rainey is a Talent Acquisition Consultant with 30+ years in recruiting and HR. He runs [The Career Cantina](https://thecareercantina.com), a career coaching and content practice focused on helping professionals navigate AI-shaped hiring systems.

**Contact:** [wayne@thecareercantina.com](mailto:wayne@thecareercantina.com)
