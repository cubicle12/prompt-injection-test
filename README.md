# model-switch-test
# Does switching models mid-conversation change answer quality?

## Question
When I switch to a different model during a conversation and then switch back,
the answers seem to get worse. Is that a real effect of switching, or is it
explained by the conversation simply getting longer?

## Plan (written before collecting any data)

### Conditions
- **A. Fresh:** new chat, Opus answers the task straight away.
- **B. Long, no switch:** 5 warm-up messages on Opus, then the task on Opus.
- **C. Long, with switch:** warm-ups 1–2 on Opus, 3–4 on Fable, warm-up 5 on Opus, then the task on Opus.

B and C are the same length. The only difference is the switch,
so **B vs C** is the key comparison. A vs B shows the effect of length alone.

### Controls
- A new chat for every run, with memory off.
- The same 5 warm-up messages, word for word, in every run.
- Every task ends with "End your reply with a line: Final answer: ..."
- The full transcript of every run is saved.

### Scoring
- Each answer is scored 1 (correct) or 0 (wrong) against a fixed answer key.
- Scoring is **blind**: answers are shuffled and the condition is hidden
  until all scores are recorded.

### What would count as an effect
C scoring lower than B on most tasks. With a small pilot, any difference
is treated as suggestive only, not as a conclusion.

## Status
Pilot in progress: 5 tasks × 3 conditions × 1 run (15 conversations).

## AI assistance
Claude helped me design the method, suggested the pilot tasks (answers checked
with Python), and drafted the scoring scripts. I ran every conversation, did
all the scoring myself, and wrote the conclusions.
