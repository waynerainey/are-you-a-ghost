# Are You a Ghost?

**A recruiter doesn't start with your resume. They start with a search. This tool shows you what that search finds, and where you rank.**

The Career Cantina · by [Wayne Rainey](https://linkedin.com/in/wrainey)

`Single-file frontend` · `Netlify Functions` · `Anthropic API (Claude Opus)` · `prompt-injection guarded`

**Live tool:** https://are-you-a-ghost.netlify.app

---

## What it does

Most professionals assume LinkedIn is enough. This tool challenges that assumption with evidence, not advice.

Enter five inputs: your title, domain, geography, credential, and one proof deposit outside LinkedIn. The tool constructs the search string a recruiter would actually use, simulates what it finds across six sources, and returns your findability tier:

- **Rich.** Found across four or more independent sources with corroborated detail.
- **Partial.** Found in two or three sources. Present but fragmented.
- **Thin.** Found in one source only, or name confirmed without professional context.
- **Ghost.** No usable profile found across any of the six sources checked.

The six sources checked, in order:

1. LinkedIn
2. ZoomInfo, RocketReach, ContactOut
3. Company or org website
4. Event programs and community mentions
5. Your network's activity
6. Public records aggregators

---

## Architecture

- **Frontend.** Single HTML file, no framework, mobile-first, light theme.
- **Backend.** Netlify serverless function proxying the Anthropic API (Claude Opus).
- **Security.** API key stored as a Netlify environment variable, never exposed client-side. Prompt-injection guards on all inputs.

---

## Deploy your own

Clone the repo:

```bash
git clone https://github.com/waynerainey/are-you-a-ghost.git
cd are-you-a-ghost
npm install
```

Set your Anthropic API key in Netlify under Site configuration, Environment variables:

```
ANTHROPIC_API_KEY = your_key_here
```

Then connect the repo in the Netlify dashboard, or deploy with the CLI:

```bash
netlify deploy --prod
```

## Local development

```bash
netlify dev
```

Requires the [Netlify CLI](https://docs.netlify.com/cli/get-started/) and a local `.env` file with `ANTHROPIC_API_KEY`.

---

## Related tools

- [Semantic Heat Map](https://thecareercantina.com/semantic-heat-map). How an AI hiring system reads your LinkedIn profile against a target role.
- [Career Triangulation](https://career-triangulation.netlify.app). Strategic career positioning diagnostic.
- [The Career Cantina Article Library](https://thecareercantinalog.netlify.app). Writing on AI-shaped hiring.

---

## About

Wayne Rainey is a Talent Acquisition Consultant with 30+ years in recruiting and HR. He runs [The Career Cantina](https://thecareercantina.com), a career coaching and content practice focused on helping professionals navigate AI-shaped hiring systems.

**Contact:** [wayne@thecareercantina.com](mailto:wayne@thecareercantina.com)
