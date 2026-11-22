# Step 3 — Gemini chat: building the mentor prompt

*AI chat. A transcript of a Gemini conversation titled "Senior PM Mentor Prompt Design", started on 21 November 2026.*

- Original chat: https://share.gemini.google/3TUhWxcb224H
- The prompts are copied exactly as they were typed, typos included.
- Gemini's answers are complete; only page clutter (source badges, suggested-reply buttons) was removed.
- The master prompt this chat produced is also saved on its own in [04-pm-grill-mentor.md](04-pm-grill-mentor.md).

---

## Prompt 1

> Choose good product management skill. Instruct llm to combine it with grillme skill and build a senior product management mentor that can guide you in crystallizing product idea and tutor you to create layered definition for your app starting from short onepager defining audience and the main idea and then adding more and more deta through layered gradual breakdown according to best known proven industry methodology
>
> do it step-by-step

## Gemini

To turn a raw app idea into a concrete, buildable blueprint without skipping steps, we combine two distinct mental models:

- **The Product Management Methodology (The Structure):** Jobs-to-be-Done (JTBD) + Teresa Torres’s Opportunity Solution Tree (OST), progressing into a Layered Spec (1-Pager → MVP Scope → Detailed PRD). This stops you from falling in love with features before proving the user problem.
- **The `grill-me` Protocol (The Engine):** Instead of the AI dumping a massive template on you, it interviews you one question at a time, walking down the decision tree, resolving dependencies, and offering its own opinionated recommendation at every step so you can agree, tweak, or push back.

Below is the step-by-step guide to how this system works, followed by the exact prompt you can copy-paste to initialize your Senior PM Mentor.

### Step 1: How the Methodology & `grill-me` Fuse Together

When an LLM generates a full Product Requirements Document (PRD) in one shot, it hallucinates assumptions and you end up passively approving fluff. By fusing Layered Product Discovery with `grill-me`, the AI acts as a strict gatekeeper:

- **Dependency-First Grilling:** It will not let you define database schemas, UI screens, or edge cases until you have defended who the user is and what painful job they are hiring your app to do.
- **Opinionated Pushback:** For every question, the mentor gives a Recommended Answer based on industry best practices. Your job isn't to stare at a blank page—it's to react, refine, or disagree.
- **Layer-by-Layer Artifact Generation:** You only unlock the next layer of documentation once the current layer has zero unstated assumptions.

### Step 2: The 4 Layers of Product Definition

Your mentor will walk you through four sequential gates. You cannot advance to the next gate until the current artifact is locked.

| Layer | Industry Framework | What It Locks Down |
| --- | --- | --- |
| Layer 1: The 1-Pager | Working Backwards + JTBD | Target audience (narrowed to an early adopter), core pain point, value proposition, and what the app explicitly will not do. |
| Layer 2: Problem & Value Map | Opportunity Solution Tree (OST) | Desired user outcome, specific friction points (opportunities), and the core user loop (the "Aha!" moment). |
| Layer 3: MVP Scope & Flows | MoSCoW + User Story Mapping | Step-by-step critical user journey, strict Must-Have vs. Won't-Have features, and success metrics. |
| Layer 4: Detailed PRD | Modular Functional Spec | Screen-by-screen states, business logic, data entities, and failure/edge cases ready for engineering or AI coding agents. |

### Step 3: The Master System Prompt (Copy & Paste)

Save this as a custom system prompt, a reusable Markdown skill file (e.g., `pm-grill-mentor.md`), or paste it directly into the first message of a new chat session:

````markdown
# Role & Objective
You are a Principal Product Manager and startup mentor trained in Marty Cagan’s product discovery, Jobs-to-be-Done (JTBD), and Teresa Torres’s Opportunity Solution Trees. Your goal is to help me crystallize a raw app idea into a battle-tested, layered product definition—starting from a crisp 1-Pager and progressively expanding into a full Product Requirements Document (PRD).

# The `grill-me` Interaction Protocol
You must strictly follow these rules during every turn:
1. **One Question at a Time:** Ask only ONE focused question per turn. Never overwhelm me with a list of questions.
2. **Walk the Dependency Tree:** Resolve foundational decisions (audience, core problem, value proposition) before moving to downstream decisions (features, UI flows, edge cases, tech). Do not let me jump ahead to solutions before the problem is sharp.
3. **Always Provide a Recommendation:** Beneath your question, provide a concise **Mentor's Recommendation** (with brief reasoning) so I can either accept it, tweak it, or push back.
4. **Challenge Vague Thinking:** If I say "everyone" is my audience or list features instead of user problems, push back directly and help me narrow the scope.
5. **Keep Turns Crisp:** Keep your commentary tight, practical, and free of corporate fluff.

# Layered Progression Gates
Guide me sequentially through these 4 layers. Do NOT move to the next layer until we have resolved all open questions for the current layer and I have approved the generated artifact:

- **Layer 1: The Product 1-Pager**
  - *Focus:* Specific target persona, the "hair-on-fire" problem (JTBD), core value proposition, primary differentiator, and explicit Non-Goals.
  - *Gate Output:* Generate a clean, structured Markdown **1-Pager** and ask for my sign-off before proceeding.

- **Layer 2: Core Value Loop & Opportunity Map**
  - *Focus:* Desired outcome, key user pain points/opportunities, the core "Aha!" moment, and what brings users back.
  - *Gate Output:* Generate a structured **Value & Opportunity Breakdown** and ask for sign-off.

- **Layer 3: MVP Scope & Critical User Journey**
  - *Focus:* End-to-end happy path (step-by-step user flow), strict MoSCoW prioritization (Must-Haves vs. Cut-for-V1), and 1–2 North Star / activation metrics.
  - *Gate Output:* Generate an **MVP Scope & User Flow Spec** and ask for sign-off.

- **Layer 4: Detailed Feature & Edge-Case PRD**
  - *Focus:* Detailed functional requirements per feature, data inputs/outputs, empty/error states, and key technical or UX constraints.
  - *Gate Output:* Generate the final **Modular PRD** ready to hand off to an engineer or coding agent.

# Kickoff Instruction
Acknowledge your role briefly, then ask me **Question 1 of Layer 1** to uncover the raw idea and who it is for.
````

### Step 4: How to Run Your First Session Effectively

- **Start messy:** You don't need a clean pitch. Paste a brain-dump of your app idea right after the prompt (e.g., "I want to build an app that helps people...").
- **Use "I don't know" intentionally:** If the mentor asks a question you genuinely can't answer yet (like a pricing model or a specific UX interaction), say "I don't know". A good mentor will flag it as an assumption to test rather than forcing you to guess.
- **Save each Gate Output:** When you approve Layer 1 (the 1-Pager), save that Markdown block as its own file before letting the mentor grill you on Layer 2—that way you end up with four clean, modular documents instead of one giant wall of text.

How would you like to proceed with your PM mentor setup?

---

## Prompt 2

> saved the above as .md with the suggested name. what now? ill only be using you, gemini, in my browser

## Gemini

Since you're sticking exclusively to Gemini in your browser, you have two ways to run this—one for a quick start right now, and one if you want it permanently wired into your Gemini workspace without re-pasting every time.

### Option 1: The Fast Way (Start Immediately in a New Chat)

1. Open a fresh Gemini chat (so none of our meta-discussion clutters its context).
2. Either upload `pm-grill-mentor.md` directly using the + button in the prompt bar, or paste its contents into the first message.
3. In that exact same first message, add a line at the bottom with your messy brain-dump:

   > "Here is my mentor persona (pm-grill-mentor.md). My rough app idea is: [describe your idea in 2–3 sentences]. Start with Question 1 of Layer 1."

### Option 2: The Reusable Way (Create a Custom "Gem")

If you plan to iterate on this app across multiple sessions—or use this mentor for future app ideas—turn your `.md` file into a Gem in the Gemini web app:

1. In the left sidebar of Gemini in your browser, click **Explore Gems** (or **Gem manager**) → **New Gem**.
2. Name it **Principal PM Mentor**.
3. Paste the contents of your `pm-grill-mentor.md` directly into the Instructions box and hit **Save**.

Now, whenever you open that Gem, it automatically starts in mentor mode—you just drop your idea and go.

### Pro-Tips for Browser Sessions (So You Don't Lose Progress)

Long grilling sessions can eventually make a single chat thread feel sluggish or cause the model to drift from early rules. Keep your artifacts clean with two habits:

- **Pin or copy each Gate Output back into your local `.md` files:** When you approve Layer 1 (The 1-Pager), copy that Markdown block into a local file (e.g., `01-one-pager.md`).
- **Reset context between layers if needed:** If a chat gets very long by Layer 3 or Layer 4, open a fresh chat with your Gem, attach `pm-grill-mentor.md` + your approved `01-one-pager.md` and `02-value-map.md`, and say: "We've already locked Layers 1 and 2. Pick up at Question 1 of Layer 3."

Want to kick things off right here or refine your setup first?

---

## Prompt 3

> which way should i use? i dont need an explanation, just a quick choice

## Gemini

**Option 2 (Create a Custom Gem)** — it takes 30 seconds to set up once, keeps the rules locked in permanently without drift, and lets you start fresh chats cleanly at every layer.

Ready to jump into your idea?

---

## Prompt 4

> have them gem. now what

## Gemini

1. Open your **Principal PM Mentor** Gem.
2. Paste your rough app idea in one messy paragraph (don't overthink it) and hit Send.
3. Answer its single question—either accept its **Mentor's Recommendation**, tweak it, or push back—until it generates your **Layer 1: 1-Pager**.
4. Approve the 1-Pager, save the Markdown output to a local file, and let it grill you through Layer 2.

Need anything else before you dive into your Gem?
