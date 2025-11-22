# Review Notes: *From Words to Worlds: Spatial Intelligence is AI’s Next Frontier*

[Fei-Fei Li Substack — “From Words to Worlds: Spatial Intelligence”](https://drfeifei.substack.com/p/from-words-to-worlds-spatial-intelligence)

## TL;DR

Fei-Fei Li frames spatial intelligence as the next step toward “Turing vision”: moving from fluent *talkers* to machines that can *see, imagine, and act in the world*. Three big themes stood out:

1. **LLMs are word-smart but world-naïve.** They know a lot, but lack grounding in geometry, physics, and time. ([HowAIWorks.ai][1])
2. **Spatial intelligence is the frontier beyond language.** Real progress in robotics, autonomy, and scientific discovery needs models that link perception ↔ memory ↔ action. ([HowAIWorks.ai][1])
3. **World models are the path forward.** They must be **generative**, **multimodal**, and **interactive**—able to build and update coherent 3D/4D environments. ([Medium][2])

You can almost read this as: we’ve spent a decade teaching machines to *talk about* the world; the next decade is teaching them to *live in* it.

> “Creativity is intelligence having fun.” — often attributed to Einstein.
> Fei-Fei’s essay feels like a call to let AI “have fun” in full worlds, not just token streams.

---

## FAQ

### **What does Fei-Fei mean by “spatial intelligence”?**

The capability to perceive and reason over space and time—understanding *where things are*, *how they relate*, and *what happens when actions occur*. Language is 1-D; the world is 3-D plus dynamics. ([HowAIWorks.ai][1])

### **Why aren’t today’s LLMs enough?**

They’re knowledgeable but ungrounded: excellent at symbolic manipulation, weak at forming persistent, physically consistent world states. That’s why retrieval grounding (KG/RAG) and tool use keep showing up in practice. ([HowAIWorks.ai][1])

### **What exactly is a “world model”?**

A model that represents and predicts complex worlds (virtual or real). Fei-Fei’s three required capabilities:

* **Generative:** can synthesize coherent worlds that obey geometry/physics.
* **Multimodal:** consumes more than text (vision, depth, action, touch, etc.).
* **Interactive:** updates world state under actions, predicting “what happens next.” ([Medium][2])

### **Why is training spatial models hard?**

Spatial data isn’t as “scrapable” as text—robotics and 3D interaction logs are scarce. Closing the sim-to-real gap likely needs high-fidelity synthetic data + new sensing modalities (depth, tactile). ([VAST Data][3])

### **How does this relate to Text-to-SQL / BIRD (your example)?**

Text-to-SQL shows the same pattern: general LLMs are strong but still need grounding/curated supervision to hit SOTA, and test-time scaling helps. Google’s recent BIRD single-model result is a good signal of that trajectory. ([Google Cloud][4])

---

# Key Takeaways

## 1. “Turing Vision” needs embodiment, not just eloquence

Fei-Fei starts from the gap between *describing* the world and *understanding/acting within* it. Many cognitive and ML traditions argue intelligence is a perception–action loop; language-only systems miss that core substrate. Spatial intelligence is her proposed bridge. ([HowAIWorks.ai][1])

Your framing lands well here: LLMs may be broad and capable, but without grounding they’re still “closed-loop-less.”

---

## 2. World models = imagination with persistence

A subtle but important requirement in the essay is **coherence over time**: the world model’s “now” must connect to its “past,” producing an explicit, inspectable state when needed. That’s what makes the model usable for robotics, games, XR, or science—not just pretty generations. ([The Neuron Daily][5])

This also matches your thought about *evolving worlds*: you want benchmarks that test whether models keep identities, rules, and histories straight.

---

## 3. Your research riff: memory vs physics priors

Fei-Fei notes the open question of **explicit vs implicit** world representations and innate geometric structure. ([The Neuron Daily][5])

**Revised mini-direction title:**
**“Cold-Start Memory, Warm-Start Physics: How Much World Can a Model Remember vs Re-Infer?”**

**Hypothesis (1–2 sentences):**
If a world model has strong long-horizon memory of latent world state, it can rely on *less* explicit physical cueing at each step; conversely, in cue-rich environments, smaller memory may suffice. The key trade-off is whether persistence (memory) or priors (physics/geometry) dominates generalization to new but rule-consistent worlds.

---

## 4. Benchmarks should be *world-distinct*, not just world-large

I like your “two worlds clash” idea a lot. Fei-Fei argues we need a universal training objective and better data/eval stacks for spatial learning. ([The Neuron Daily][5])

A controlled “rules-first” benchmark could:

* preload simple physics/action rules,
* let worlds evolve,
* and evaluate whether the model *separates* incompatible rule sets (hallucination = mixing worlds).

That feels like a clean way to operationalize “groundedness” in space.

---

## 5. The long game: simulation → reality

Because real robotic data is limited, world models may become the engine that rapidly generates high-fidelity simulations—tightening the sim-to-real loop. As perceptual accuracy and efficiency improve, this could unlock autonomy and scientific discovery far beyond today’s reach. ([VAST Data][3])

---

# References

1. **Fei-Fei Li (2025).** *From Words to Worlds: Spatial Intelligence is AI’s Next Frontier.* Substack. ([HowAIWorks.ai][1])
2. **HowAIWorks Team (2025).** *Spatial Intelligence: AI’s Next Frontier* (summary). ([HowAIWorks.ai][1])
3. **The Neuron Daily (2025).** *Why AI needs spatial intelligence* (summary of world-model pillars). ([The Neuron Daily][5])
4. **VAST Data / Shared Everything (2025).** *Spatial Intelligence Is AI’s Next True Frontier* (chat + context). ([VAST Data][3])
5. **Google Cloud (2025).** *How to get Gemini to deeply understand your database* (BIRD SOTA example). ([Google Cloud][4])
6. **BIRD Benchmark Team (2023–2025).** *BIRD: Text-to-SQL with efficiency & knowledge evidence.* ([bird-bench.github.io][6])