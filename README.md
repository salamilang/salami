# salami

_Salami is under active development, and the first prototype version will be published soon in this repository. Subscribe to [the Salami blog](https://salamilang.substack.com/) to receive updates. [Read more](https://salamilang.substack.com/p/slalom-designing-a-runtime-for-ai) about the planned runtime features._

Salami is a workflow runtime for LLM-generated code. It is reactive, async, and resumable (e.g. you can pause the running thread, store it in a file or any database, and restore it later when it's time to continue). It allows the code to be completed or edited in case of an error or incomplete specification.

It uses an internal language that is specifically designed to make it easy for an LLM to translate complex user instructions, with arbitrary triggers, delays, and easy state management. It also supports partial instructions that can only be improved upon ad hoc: "but when this happens, ask me what to do".

Salami only uses an LLM to generate the code upon the user instruction. Running it doesn't need an LLM, which massively saves costs and simplifies infrastructure requirements (compared to such SOTA methods as AutoGPT or ...).

Salami is deliberately not based upon an existing fully-featured programming language, to enable the reactive features and storable continuations, to improve sandboxing and resource control, and to avoid the semantic traps that arise from asking LLMs to write reactive code that is supposed to be triggered by external events in common languages. It is greatly inspired by Durable Workflows, but it's not actually "Durable" itself in that sense. Salami should be thought of as a workflow runtime, rather than a general-purpose VM.
