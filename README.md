# LLM Inference Simulators

How to build, accelerate, validate and integrate simulators for LLM inference and novel AI hardware. Eleven interactive decks run from *why* architecture teams simulate (and how software-level models relate to RTL simulation), through a hands-on simulator-development tutorial in SimPy, the physics of LLM serving and the existing simulator landscape, to a **live disaggregated-serving simulator in the browser**, then metrics and validation, **power and energy** (DVFS, power caps, joules per token), acceleration techniques, and integration with PyTorch, ONNX Runtime and HEIR. A reading list and a role primer close the series.

**Live index:** https://brendanjameslynskey.github.io/LLM_Hub_Inference_Simulators/

## Presentations in this series

| # | Title | Status | What it covers |
|---|-------|--------|----------------|
| 01 | [Why Simulate? From Spreadsheets to RTL](https://brendanjameslynskey.github.io/InfSim_01_Why_Simulate/) | live | The fidelity ladder of pre-silicon models — analytical, discrete-event, transaction-level, cycle-accurate, RTL, emulation — what each answers, what each costs, and how software-level simulators and RTL simulation feed each other. |
| 02 | [Simulator Development: A Hands-On Tutorial](https://brendanjameslynskey.github.io/InfSim_02_Simulator_Development_Tutorial/) | live | Build a discrete-event simulator from an empty file: the event queue, simulated time, processes, resources and probes; then SimPy idioms, how to structure a simulator so it survives contact with architects, modelling buses, memories and pipelines, and making the simulator itself fast. |
| 03 | [What You Are Simulating: LLM Inference Workloads](https://brendanjameslynskey.github.io/InfSim_03_LLM_Inference_Workloads/) | live | Prefill versus decode, the roofline, KV-cache arithmetic, batching and parallelism — the first-order physics every LLM inference simulator must get right, with the formulas to put in a cost model. |
| 04 | [The LLM Simulator Landscape](https://brendanjameslynskey.github.io/InfSim_04_Simulator_Landscape/) | live | A guided tour of the tools: serving-level simulators (Vidur, LLMServingSim, SplitwiseSim), hardware-level models (LLMCompass, Timeloop, SCALE-Sim), system and network simulators (ASTRA-sim, gem5, SST, SystemC), and analytical calculators — sorted by the question each one answers. |
| 05 | [Disaggregated Inference, Simulated](https://brendanjameslynskey.github.io/InfSim_05_Disaggregated_Inference/) | live | Why splitting prefill and decode onto separate hardware raises goodput (Splitwise, DistServe, Mooncake, NVIDIA Dynamo), what the KV-cache transfer costs, and a live discrete-event simulator you can drive in the browser — a JavaScript port of the SimPy model in Disaggregated_Inference_Sim. |
| 06 | [Metrics, Hot-Spots & Validation](https://brendanjameslynskey.github.io/InfSim_06_Metrics_Hotspots_Validation/) | live | Turning a simulation into evidence: latency distributions, utilisation, MFU/MBU, stage breakdowns and hot-spot attribution; traces in Perfetto; statistics that survive review; and the verification ladder — unit, invariant, analytic, behavioural, correlation — wired into CI. |
| 07 | [Power & Energy in Inference Simulators](https://brendanjameslynskey.github.io/InfSim_07_Power_and_Energy/) | live | Speed is half of performance. Static and dynamic power, why data movement dominates energy, the simulator's calibrated power model, prefill running hot and decode cool, DVFS and power caps as a third roof, energy proportionality, the link to RTL power and thermal analysis, and what photonic systems must pay for — all measured on the companion simulator. |
| 08 | [Accelerating Inference Simulators](https://brendanjameslynskey.github.io/InfSim_08_Accelerating_Simulators/) | live | Making this kind of simulator fast without changing its answers: event abstraction, incremental state, lazy bookkeeping, exact macro-stepping, probe discipline, compiled kernels, parallel and multi-fidelity sweeps, surrogates, sampling, and parallel discrete-event simulation — each measured on the companion simulator. |
| 09 | [From PyTorch, ONNX & HEIR to a Simulator](https://brendanjameslynskey.github.io/InfSim_09_Framework_Integration/) | live | How real applications reach a simulated accelerator: graph capture with torch.fx / torch.export and torch.compile backends, out-of-tree PyTorch devices, ONNX Runtime execution providers, MLIR, and Google's HEIR compiler for fully homomorphic encryption. |
| 10 | [Further Learning: Books, Courses, Papers, Tools](https://brendanjameslynskey.github.io/InfSim_10_Further_Learning/) | live | A curated reading list for simulator engineers: textbooks on discrete-event simulation and computer architecture, university courses, the key LLM-serving and simulator papers, and the open-source tools worth reading the source of. |
| 11 | [Role Primer: Simulation & Frameworks Engineer](https://brendanjameslynskey.github.io/InfSim_11_Role_Primer/) | live | The series applied to a real job: a photonic-computing architecture group's simulation and frameworks role, mapped requirement by requirement onto the decks, with the domain background (photonics, FHE) and a set of practice questions. |

## Companion code

| Repo | What's inside |
|------|---------------|
| [Disaggregated_Inference_Sim](https://github.com/BrendanJamesLynskey/Disaggregated_Inference_Sim) | A SimPy discrete-event simulator of prefill/decode-disaggregated LLM serving: roofline cost model, continuous batching, KV-capacity admission, a shared KV link, colocated baseline; latency percentiles, goodput, utilisation, MFU/MBU, stage breakdown, hot-spot attribution, Perfetto traces; a power model (static + pJ/FLOP + pJ/byte + pJ/bit, DVFS, per-pool power caps, joules per token); an exact accelerated path, search utilities, 32 tests, and the JavaScript port used live in deck 05. |

## How to read this series

Decks 01–02 are about simulators in general and stand alone. Decks 03–05 apply them to LLM serving and culminate in the live simulator. Decks 06–09 cover what turns a simulator into an engineering tool: trustworthy metrics, power and energy, simulator speed, and integration with real frameworks. Deck 10 is a reading list (books, courses, papers, tutorials, source code); deck 11 applies the whole series to a real, publicly advertised simulation-and-frameworks role.

## Where this fits

Part of the [LLMs hub](https://github.com/BrendanJamesLynskey/LLMs), under *Hardware & Inference*. Complements [Local LLM Hosting](https://github.com/BrendanJamesLynskey/LLM_Hub_Local_LLM_Hosting) (the real serving engines these simulators model), [NVIDIA GPU Architectures](https://github.com/BrendanJamesLynskey/LLM_Hub_NVIDIA_GPUs) and [Google TPUs](https://github.com/BrendanJamesLynskey/LLM_Hub_Google_TPUs) (the hardware in the cost models), and the [Key LLM Publications](https://github.com/BrendanJamesLynskey/LLM_Hub_Key_Publications) efficient-inference deck.
