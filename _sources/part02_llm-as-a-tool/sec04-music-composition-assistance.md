# Music Composition Assistance

Presumably, LLM as an assistant for music composition would share many properties with LLMs as an assistant for writing. So, I shamelessly replace this section with this paper: {cite}`ippolito2022creative`.

..Since that feels overly shameless, here are some recent progress in using LLMs for composition. These are all about the symbolic domain and notations.  

- **ChatMusician** {cite}`yuan2024chatmusician`
  - MusicPile: 4B-token music-language corpora
  - MusicTheoryBench: Curated college-level music understanding benchmark
  - A LLaMA2-finetuned model "ChatMusician" that can understand and generate ABC notation
- **ComposerX** {cite}`deng2024composerx`
  - GPT-4 with various prompting methods to create melody and harmony / to review and revise / to finalize the composition.
- **SongComposer** {cite}`ding2024songcomposer`
  - Lyric-to-melody generation by finetuning an open-sourced LM.
-  **ByteComposer** {cite}`liang2024bytecomposer`
  - A workflow consists of conception analysis - drafting - self-evaluation - final selection
