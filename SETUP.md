# GitHub setup — step by step

This is how to push the three projects and this profile README to GitHub, and link GitHub on LinkedIn. **Nothing has been pushed yet — no GitHub account is connected.** Do these steps in order, on your own computer (or here, once you share your GitHub username).

## 0. What you need first

- A GitHub account. If you don't have one yet, create it at https://github.com/signup
- Your GitHub **username** — you will need it in step 4. Write it down here: `____________________`
- Git installed (`git --version` to check)

## 1. Push the three project repos

Do this once per project. The local folders are:

- `~/workspace/projects/krishnateja-rag-chatbot/` → repo `krishnateja-rag-chatbot`
- `~/workspace/projects/krishnateja-langgraph-agent/` → repo `krishnateja-langgraph-agent`
- `~/workspace/projects/krishnateja-research-paper-agent/` → repo `krishnateja-research-paper-agent`

For each project:

### a. Create the repo on GitHub (in the browser)

1. Go to https://github.com/new
2. Repository name: exactly `krishnateja-rag-chatbot` (then `krishnateja-langgraph-agent`, then `krishnateja-research-paper-agent`)
3. Description (copy from the project README):
   - RAG: `RAG doc chatbot with citations — Python, FastAPI, LangChain, ChromaDB. Runs with no API key.`
   - LangGraph: `Multi-step LangGraph agent: plan, research, draft, critique, revise — with structured outputs and evals.`
   - Research paper agent: `PhD research paper agent: summaries, contradictions, and a literature review outline with citations.`
4. Public, **do not** tick "Add a README" (the project already has one)
5. Create repository

### b. Push the local code

```bash
cd ~/workspace/projects/krishnateja-rag-chatbot

# LICENSE: krishnateja-langgraph-agent and krishnateja-research-paper-agent already
# have an MIT LICENSE. This one does not yet — copy it in first:
cp ~/workspace/projects/github-profile/LICENSE ./LICENSE

git init
git add .
git commit -m "RAG doc chatbot: FastAPI + LangChain + ChromaDB, eval 5/5 in mock mode"
git branch -M main
git remote add origin https://github.com/krishnatejaganesh97/krishnateja-rag-chatbot.git
git push -u origin main
```

Repeat for the other two, changing the folder, commit message, and repo name:

```bash
cd ~/workspace/projects/krishnateja-langgraph-agent
git init
git add .
git commit -m "LangGraph agentic workflow: plan, research, draft, critique, revise — eval 5/5 in mock mode"
git branch -M main
git remote add origin https://github.com/krishnatejaganesh97/krishnateja-langgraph-agent.git
git push -u origin main

cd ~/workspace/projects/krishnateja-research-paper-agent
git init
git add .
git commit -m "PhD research paper agent: summaries, contradictions, literature review outline — eval 5/5 in mock mode"
git branch -M main
git remote add origin https://github.com/krishnatejaganesh97/krishnateja-research-paper-agent.git
git push -u origin main
```

Replace `krishnatejaganesh97` with your real username in every command.

### c. Safety check before every push

- Never commit a `.env` file or an API key. Each project has a `.gitignore` that excludes `.env`, `.venv/`, and `__pycache__/` — but check with `git status` before committing, and make sure no `.env` file is listed.
- Never commit uploaded papers or documents from `data/uploads/` — those are git-ignored too.

## 2. Create the special profile repo

GitHub shows the README of a repo named **exactly the same as your username** on your profile page.

1. Go to https://github.com/new
2. Repository name: **exactly your username** — e.g. if your username is `krishnatejaganesh`, the repo is `krishnatejaganesh`
3. Public, do not tick "Add a README"
4. Create repository

Then push this folder's README:

```bash
cd ~/workspace/projects/github-profile
git init
git add README.md LICENSE
git commit -m "GitHub profile: AI Developer, PhD in AI, featured LLM projects"
git branch -M main
git remote add origin https://github.com/krishnatejaganesh97/krishnatejaganesh97.git
git push -u origin main
```

5. In `README.md`, replace every `krishnatejaganesh97` with your real username (the three project links), commit, and push again:

```bash
git add README.md
git commit -m "Link featured projects to real repos"
git push
```

6. Check your profile at `https://github.com/krishnatejaganesh97` — the README should now appear above your repositories.

## 3. Link GitHub on LinkedIn

1. LinkedIn → your profile → **Contact info** (pencil icon) → add your GitHub profile URL: `https://github.com/krishnatejaganesh97`
2. LinkedIn → **Add section → Projects** → add each project, one at a time:
   - Name: `krishnateja-rag-chatbot` / `krishnateja-langgraph-agent` / `krishnateja-research-paper-agent`
   - Project URL: the GitHub repo URL
   - Description: copy the one-line description from step 1a
3. Optional: pin the three repos on your GitHub profile (profile page → Customize your pins) so they show at the top.

## 4. License

All three projects and this profile repo are **MIT licensed** — free for anyone to use, copy, and improve. The `LICENSE` file in this folder is the MIT license text; it is already in `krishnateja-langgraph-agent` and `krishnateja-research-paper-agent`, and step 1b copies it into `krishnateja-rag-chatbot` before its first push.
