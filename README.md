# BabyBeeAGI 🐝

BabyBeeAGI is a **lightweight “OG mod”** of the original BabyAGI.

I’m using a naming pattern of **Baby<animal>AGI** for these classic mods, and I picked **Bee** this time because it’s centered on **task management** (and yep… it’s buggy 😅).

---

## What this is

At a high level, BabyBeeAGI is a task-driven loop that:

* Starts from an **objective**
* Generates a **task list**
* Executes tasks one at a time
* Uses a **task manager** to clean up / reprioritize / add tasks as results come in
* Keeps a running **session summary** of what happened

It’s small (roughly a few hundred lines) and intentionally “classic”—easy to read, easy to tinker with.

---

## What’s new vs OG BabyAGI

### 1) Stronger task management

The task manager’s job is to keep the list sane:

* Don’t remove tasks
* Only reorder + dedupe incomplete tasks
* Keep IDs chronological
* Cap the list (max 7 tasks)
* Always end with a “final summary report” task

### 2) Tool framework for the execution agent

BabyBee includes a simple framework for the execution agent to use tools:

* **`text-completion`** (default)
* **`web-scrape`** (default)
* **`web-search`** (optional) — enabled automatically if you add a **SERPAPI** key

So:

* **No SERPAPI key** → web-search is disabled
* **SERPAPI key set** → web-search turns on

---

## Quick start

1. Set these variables at the top:

* `OPENAI_API_KEY`
* `SERPAPI_API_KEY` (optional)
* `OBJECTIVE`
* `YOUR_FIRST_TASK`

2. Run the script.

You’ll see:

* The current **objective**
* The **next task** chosen
* The **task result**
* The updated **task list**
* The rolling **session summary**

---

## Read the “paper”

I also had GPT-4 write up a short explainer / “paper” about the approach here:

* [https://yoheinakajima.com/babybeeagi-task-management-and-functionality-expansion-on-top-of-babyagi/](https://yoheinakajima.com/babybeeagi-task-management-and-functionality-expansion-on-top-of-babyagi/)

(And here’s the earlier Task-Driven Autonomous Agents thread too: [https://x.com/yoheinakajima/status/1640934493489070080](https://x.com/yoheinakajima/status/1640934493489070080))

---

## Repo + where this lives

This project now lives in its own repo:

* [https://github.com/yoheinakajima/babybeeagi](https://github.com/yoheinakajima/babybeeagi)

The original OG BabyAGI codebase can be found here:

* [https://github.com/yoheinakajima/babyagi_og](https://github.com/yoheinakajima/babyagi_og)

BabyAGI core has evolved quite a bit since the OG days, which is part of why I’m breaking these classic mods out into their own repos rather than trying to keep them in sync with the modern core.

---

## If you try it

If you play around with BabyBee, I’d love to hear:

* What did you like more than OG BabyAGI?
* What did you like less?
* Any questions about the new approach?
* What new ideas did it spark?

👋
