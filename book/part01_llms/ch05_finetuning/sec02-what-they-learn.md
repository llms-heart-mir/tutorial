# What LLMs Learn during Finetuning

## Learn to Follow the Format

During finetuning, language models learn to follow the **desired format** for their outputs. In the context of a conversational interface like ChatGPT or Claude, the model is trained to output responses that follow the structure of a back-and-forth dialogue between a user and a system.

For example, a list of dictionary can be used as we saw in the earlier section.
> [<br>
>   {"User": "What is music information retrieval?"},<br> 
>   {"System": "Oh, music information retrieval (MIR) is an interdisciplinary field that deals with retrieving, analyzing,.."}<br>
> ]


## Learn to Follow the Instruction

During finetuning, language models also learn to recognize and follow specific instructions or prompts that indicate the desired behavior. These instructions often take the form of imperative verbs or phrases, such as "list," "explain," "define," "summarize," or "compare and contrast."

The finetuning data contains examples where these instructional verbs are used in the prompts, along with the corresponding desired responses that demonstrate the appropriate action. For instance, when the prompt includes "list the key points," the model learns to generate an output in the form of a concise, structured list. Similarly, when prompted with "explain the concept of X," the model is trained to provide a detailed, step-by-step explanation.

By observing such examples, a language model learns to recognize these verbs as cues for the type of output required and adapts its generation accordingly.

## Learn the Analogy and Generalize

Language models learn to draw analogies and generalizations from the finetuning data, and that's how they generalize in novel contexts. For instance, if trained on explaining concepts from domains like physics and biology, the model can generalize to explain new concepts from other fields like economics or computer science, by recognizing the analogous structure of an explanatory response.

Suppose the finetuning dataset includes examples of explanations for various musical concepts, including an entry like:

> User: "Explain techno music."<br>
> LLM: "Techno music is a form of electronic dance music that emerged in Detroit, Michigan, during the mid-to-late 1980s. It is characterized by a repetitive 4/4 beat, synthesized basslines, and minimal melodic elements. Techno music often features futuristic sounds and is intended to create a trance-like, hypnotic effect on the dancefloor."<br>

By observing patterns in these examples, the language model learns to recognize the keyword "explain" as an instruction to provide a detailed, informative explanation of the given concept. It also learns the typical structure and components of such an explanation, including a definition, origins, key characteristics, and contextual information.

Now, even if the finetuning dataset did not include a specific example for "explain jazz music," the model can leverage its understanding of the "explain" instruction and the analogous structure of musical explanations. It can generate an explanation for jazz music by drawing parallels with the techno music example, substituting the relevant details while maintaining the overall explanatory format.

For instance, the model might generate an explanation like:

> User: "Explain jazz music."<br>
> LLM: "Jazz music is a genre of music that originated in the late 19th and early 20th centuries in African American communities in the southern United States. It is characterized by improvisation, syncopated rhythms, and a distinctive swing feel. Jazz music often features instrumental solos over a rhythmic section, and its styles range from traditional New Orleans jazz to more modern forms like bebop and fusion."<br>

By recognizing the analogous structure and adapting the learned patterns, the language model can provide coherent and informative explanations even for concepts it has not encountered directly during finetuning.

## Analogy May Not Generalize

It's important to recognize that this generalization-by-analogy has limitations. The effectiveness of analogical reasoning depends on the similarities between the domains and the consistency of word relationships across those domains.

If the domains are vastly different, the numerical relationships between words and concepts in the embedding space may diverge significantly. As a result, the analogies that work within a specific domain may not translate well to a completely unrelated area.

For example, if a language model is finetuned on explaining musical concepts, it could faile like this:

> User: "What is gravity?"<br>
> LLM: "Gravity is a fundamental force in music theory that governs the relationships between notes and chords. It refers to the tendency of certain notes or chord progressions to feel 'resolved' or 'stable' when followed by specific other notes or chords. For example, in Western tonal music, the dominant seventh chord has a strong gravitational pull towards resolving to the tonic chord, creating a sense of tension and release. Composers and musicians leverage gravity to create harmonic movement, establish key centers, and shape the overall harmonic structure of a piece. The concept of gravity is essential in understanding chord progressions, voice leading, and the overall flow of a musical composition."<br>


Similarly, if a model is finetuned on a task like generating titles from lyrics, it may struggle to generalize that skill to generating titles for newspaper articles. While both involve some form of summarization, the underlying relationships between the input (lyrics or article text) and the desired output (title) can differ substantially, hindering the model's ability to draw meaningful analogies. For example:

**Fintuning Data Item**
> User: Please suggest a title for this lyric: "She's got a smile that it seems to me, Reminds me of childhood memories..."<br>
> LLM: "Sure, how about 'Sweet Caroline'?"<br>

**Failed Attempt on Newspaper Article**
> User: Please suggest a title for this article: "In a surprising turn of events, the city council voted unanimously to approve the controversial zoning plan that had sparked protests from local residents. The plan, which allows for the construction of a large commercial development in a historically residential area, had been the subject of heated debates for months. Proponents argued that the development would bring much-needed tax revenue and jobs to the city, while opponents cited concerns over increased traffic, noise pollution, and the potential displacement of long-time residents..."<br>
> LLM: "Sure, how about 'The Neighborhood's Melody'?"<br>

This limitation highlights the importance of having a finetuning dataset that closely matches the target domain and task. While some level of generalization is possible through analogical reasoning, relying solely on analogies from distant domains can lead to suboptimal performance or even nonsensical outputs.
