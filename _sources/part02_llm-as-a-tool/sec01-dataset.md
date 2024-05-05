# Dataset Cleaning and Creation

LP-MusicCaps {cite}`doh2023lpmusiccaps` is a great example of using a LLM as a tool to solve MIR problems.

Music captioning is a task of generating natural language description of given music. Captions are for example:

> A high-energy rock anthem with driving guitar riffs and powerful vocals, this track exudes a sense of rebellion and youthful defiance. The pounding drums and soaring melodies create an anthemic feel, perfect for getting crowds pumped up and singing along.
> This mellow acoustic ballad features delicate finger-picking guitar patterns and a soulful vocal performance. The introspective lyrics explore themes of love and loss, with the singer's emotive delivery evoking a sense of longing and heartache. The sparse instrumentation allows the raw emotions to shine through, creating an intimate and vulnerable listening experience.

Music captions are becoming more and more useful in the ear of LLM-based AI services. For example, an AI DJ service can utilize music captions when introducing a music track.

However, music captions are expensive to generate. It takes time for humans to listen to music and write a description about it. It also requires musical knowledge.

Fortunately, there exists a similar type of information already -- music tags. In terms of size, it's x100 easier to find music datasets that has tags like:

> rock, high-energy, guitar, vocals, drums, sing along, crowds, party

The authors of MusicCaps took this advantage. They designed several prompts that includes a list of music tags of a track so that a LLM would respond with captions. The linguistic ability of a LLM was suitable for this task for a few reasons.
- Music tags are not complete; they have a lot of false negatives. For example, a tag lists of `heavy metal, drums, vocal` is likely missing `guitar, electric guitar, bass guitar, rock, metal`, also perhaps `loud, high energy`. LLMs are good at filling information like this. 
- Synonyms can be addressed. For example, it's common to have tags like `vocalists, vocals, vocal, vocalist` in one song. LLMs can absolutely handle this and write a clean music caption. 
- Noises can be cleaned. Since music tags are often collaboratively created, there are many tags with little musical meaning such as user id or typo. LLMs can be prompted to remove this kind of noise. 
 

(disclaimer: The author (Keunwoo Choi) is one of the authors of LP-MusicCaps.)
