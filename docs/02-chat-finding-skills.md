# Step 2 — Gemini chat: finding skills

*AI chat. A transcript of a Gemini conversation titled "Using Grill-Me in Free Chats", started on 19 November 2026.*

- Original chat: https://share.gemini.google/KdcxrVzM1W3C
- The prompts are copied exactly as they were typed, typos included.
- Gemini's answers are complete; only page clutter (source badges, buttons) was removed.

---

## Prompt 1

> I heard about popular skill grillme. How can i use it in web based chats like chatgpt, gemini, claude, with no paid subscription

## Gemini

`grill-me` (originally created by Matt Pocock in his open-source `mattpocock/skills` repository) is just a structured Markdown prompt/instruction set (`SKILL.md`). Because it is stateless and doesn't require a local code repository or CLI tools to run, you don't need a paid subscription or developer CLI to use it in free web chats—you just feed the instructions directly into the chat.

### How `grill-me` Works

Instead of immediately generating a plan or solution, the model interviews you in rounds about a rough idea, plan, or system design. It asks questions whose prerequisites are already settled, surfaces unstated assumptions and edge cases, gives recommended answers with trade-offs, and keeps going until every decision branch is resolved.

### How to Use It in Free Web Chats (ChatGPT, Gemini, Claude)

1. **Grab the raw skill instructions:** Look up `mattpocock/skills` on GitHub and open the `grill-me` (and `grilling`) `SKILL.md` files to copy their instructions.
2. **Paste it into your first message:** Because free web interfaces don't always support local `/slash` skill commands or plugin marketplaces out of the box, paste the instructions right at the top of a new chat, followed by your idea or plan.
3. **Stay in the same thread:** Don't reset or start a fresh chat mid-session—the model relies on the cumulative decisions and context built across rounds.
4. **Answer honestly (including "I don't know"):** Push back when a recommendation doesn't fit, and say "I don't know" when something can only be answered by testing or prototyping rather than guessing.

### Starter Prompt You Can Paste Directly

If you want to run the core behavior right away in a free web chat without hunting down files first, paste something like this along with your topic:

```text
Act as a rigorous technical and strategic interviewer using the "grill-me" approach. I am going to give you a rough idea or plan. Before writing a final plan or solution, pressure-test my thinking by interviewing me in focused rounds of questions.

Rules:
- Ask questions whose prerequisites are already clear, building on my previous answers.
- For each question, briefly note trade-offs and give a recommended option so I can react to it.
- Surface unstated assumptions, edge cases, failure modes, and ambiguous requirements.
- If a question cannot be answered well without building/testing something first, flag it instead of making me guess blindly.
- Continue in rounds until the decision branches are resolved and we have a shared, concrete plan—then summarize the decisions and open questions.

Here is what I want to work through: [PASTE YOUR IDEA OR PLAN HERE]
```

### Practical Tips on Free Tiers

- **Watch message and context limits:** Free tiers on ChatGPT, Claude, and Gemini have tighter message caps and context windows. Keep your initial scope focused so you don't burn through your quota or hit "context rot" over dozens of back-and-forth turns.
- **Use your strongest available model for grilling:** The quality of the pushback depends heavily on the model's ability to spot edge cases and trade-offs. Once the grilling finishes and you have a clear spec or decision list, you can take that summary into a fresh chat (or another tool) to execute.
- **Save your reusable prompt:** Keep a clean copy of the instructions in a local note (like an Obsidian note) so you can paste it into any web chat in seconds.

What kind of idea, project, or decision are you thinking of running through `grill-me` first?

---

## Prompt 2

> Im starting to develop an app. I have an idea, and i want llm with experience ekof senior product manager to guide and critique be. What skills can i use?

## Gemini

To get a Senior Product Manager to pressure-test your app idea, guide your discovery, and stop you from building features nobody wants, you can combine a few open-source `SKILL.md` repositories (all written in plain Markdown, so you can copy-paste their instructions directly into free web chats).

### 1. Best Open-Source Skill Libraries for PM Guidance

| Repository / Skill | Focus | Best Specific Skills to Grab |
| --- | --- | --- |
| `deanpeters/Product-Manager-Skills` | End-to-end Senior PM coaching (explicitly designed without CLI-only syntax so you can paste the raw Markdown straight into web chats) | • `pm-skills-navigator` (routes you to the right framework based on your stage)<br>• Framing, customer discovery, prioritization, and PRD skills |
| `phuryn/pm-skills` (Product Trio) | Initial product discovery & validation for brand-new apps | • `brainstorm-ideas-new` (simulates a PM + Designer + Engineer trio focused on core value delivery and validation) |
| `anthropics/product-brainstorming` | High-level product strategy & sparring before writing specs | • `product-brainstorming` (uses Jobs-to-be-Done, SCAMPER, and OODA loops to keep the model opinionated and inquisitive) |
| `pmprompt/claude-plugin-product-management` | Shaping, scoping & anti-bloat | • `shape-up` (forces fixed time/scope appetite and risk boundaries before coding)<br>• `jobs-to-be-done-jtbd`<br>• `working-backwards` |
| `mattpocock/skills` | Turning a validated idea into an executable build plan | • `grill-me` (adversarial Q&A to resolve every edge case)<br>• `to-spec` & `to-tickets` (converts the chat into a spec and tracer-bullet tasks) |

### 2. Recommended Workflow (Zero-to-MVP Order)

Don't jump straight to specs or code—run your idea through these three stages in separate chats, passing a concise summary from one to the next:

1. **Problem & Market Critique (Idea -> Problem -> User):** Force the LLM to challenge whether the problem is painful enough, who the exact initial user is, and why existing workarounds fail.
2. **Ruthless MVP Scoping (Shape Up + `grill-me`):** Strip your feature list down to the single core loop ("tracer bullet") and resolve edge cases, data flows, and failure modes through rounds of questioning.
3. **Spec & Build Plan (`to-spec` -> `to-tickets`):** Once every branch of the interview is resolved, ask the model to synthesize all decisions into a clean PRD / technical spec and ordered implementation milestones.

### 3. Ready-to-Paste "Senior PM Critique + Grill" Prompt

If you want to start right now in a free web chat without digging through GitHub repos first, paste this along with your idea:

```text
Act as a Principal / Senior Product Manager with 15+ years of experience shipping 0-to-1 consumer and B2B apps. Your job is NOT to validate my ego or jump into building features—your job is to rigorously critique my idea, uncover fatal product risks early, and guide me to a razor-sharp MVP.

Follow this workflow in focused rounds:
1. Initial Critique: Give me a candid assessment of my idea across (a) Problem Severity, (b) Target User Clarity, (c) Differentiation vs. existing alternatives/workarounds, and (d) Biggest Assumption that could kill the product.
2. Structured Interview (grill-me style): Ask me 3–5 targeted questions at a time to resolve product ambiguity and scope. For each question, briefly explain why it matters, note the trade-offs, and state your recommended answer as a Senior PM so I can push back or agree.
3. Ruthless Scoping: Help me cut everything that isn't essential for a first testable version (MVP), defining clear non-goals and success criteria before we write any spec.

Do not generate a full PRD or code yet. Start with your candid initial critique and Round 1 of questions.

Here is my app idea: [PASTE YOUR IDEA HERE]
```

If you'd like, you can paste your rough app idea right here and I can put on the Senior PM hat to run Round 1 with you.
