<img src="https://raw.githubusercontent.com/Cheeriooo/Cheeriooo/main/assets/inference.svg" width="100%" alt="Inference readout: 'I build AI systems, tools, and workflows that actually ship.' Hallucination risk 4%, within tolerance." />

# Model card: `rakesh-sawant` 🦦

A general-purpose builder fine-tuned on shipping AI systems rather than demoing them. Weights are public, [documentation lives here](https://rakeshsawant.space).

| | |
|---|---|
| **Architecture** | one human, caffeine-attention |
| **Primary modality** | Python, JavaScript, embeddings |
| **Context window** | good until roughly 2am |
| **Fine-tuned on** | vector search, prompt compression, computer vision |
| **Deployment** | Earth, remote |

---

## Intended use

Building the unglamorous half of AI products — the retrieval layer, the prompt pipeline, the thing that has to still work on Tuesday. Direct use is encouraged. Downstream use is encouraged. Fork freely.

**Out of scope:** anything that requires me to say "we'll productionize it later."

---

## Checkpoints

Three releases worth reading, in the order I'd read them.

### `NexusDB` — a vector database, written from scratch
Not a wrapper around someone else's index. Storage, similarity search, the whole thing, in JavaScript, so I'd stop treating vector search as a magic box.

→ [**Read the source**](https://github.com/Cheeriooo/NexusDB)

### `PromptDistill` — throws away the prompt you didn't need
Most prompts are 60% ceremony. This compresses them down to the tokens actually carrying signal, and tells you what it dropped.

→ [**Read the source**](https://github.com/Cheeriooo/PromptDistill)

### `Alphabet_Recognition_Gestures` — draw a letter in the air, it reads it
Real-time hand tracking to character recognition. The project that convinced me computer vision is mostly a plumbing problem.

→ [**Read the source**](https://github.com/Cheeriooo/Alphabet_Recognition_Gestures)

<details>
<summary><b>All nine repositories →</b></summary>
<br>

Everything else lives at [github.com/Cheeriooo?tab=repositories](https://github.com/Cheeriooo?tab=repositories) — experiments, half-finished ideas, and the occasional thing I only wrote so I'd understand how it worked.

</details>

---

## Evaluation

Benchmarked against nothing in particular, self-reported, no held-out test set.

| Task | Score | Note |
|---|---|---|
| Ships the thing | 0.94 | jumped a full point the day I learned the word "MVP" |
| Reads the paper before the tutorial | 0.71 | still opens the tutorial in a second tab, just in case |
| Writes the README | 0.83 | you are currently the eval |
| Names variables well | 0.55 | `data2`, `data2_final`, and `data2_final_ACTUAL` are all in production |
| Resists rewriting a working script "properly" | 0.31 | it worked. now it's a framework |
| Correctly estimates a weekend project | 0.08 | no measurable improvement across checkpoints; considered a stable baseline |

---

## Limitations and biases

Standard disclosure, and all of it true:

- Confidently wrong about CSS, indefinitely, no amount of MDN fixes this.
- Strong prior toward building it myself instead of adding a dependency. Correct maybe half the time; the other half is just me, alone, at midnight, writing a parser.
- Inference quality drops sharply before the first coffee. Querying the base model pre-caffeine is unsupported and disclaimed.
- Treats "quick refactor" as a trigger phrase, not a task description.
- Occasionally hallucinates. This is the entire premise of the bio.

---

## Inference

```bash
curl -s https://rakeshsawant.space
```

Or open an issue on any repo above. Both return a response; only one of them is fast.

---

<sub><b>License</b> — MIT, mostly. Take the code, break the code, don't email me when it breaks. 🦦</sub>
