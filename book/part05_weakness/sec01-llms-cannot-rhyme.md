# LLMs can't rhyme

## Because LLMs don't know how to pronounce

One specific weakness of LLMs in the context of MIR is their lack of understanding of sound and phonetics. This limitation becomes particularly evident when dealing with tasks related to lyrics and vocals, where the pronunciation, rhyming patterns, and acoustic properties of words play a crucial role.

At the core of this issue is the way LLMs process and represent text during training. The tokenization process, which involves breaking down text into smaller units called tokens, completely discards important phonetic information. Tokens are simply integers, and they lack the information about how those words are pronounced or how they sound when spoken or sung.

For example, consider the words "might" and "night." While an LLM can easily understand their meanings and linguistic relationships, it does not inherently grasp that these words rhyme due to their similar vowel sounds and ending consonants. This is because the tokenization process strips away the phonetic information that would allow the model to recognize and understand rhyming patterns. If any existing LLM seemed to rhyme when you asked for rap lyrics, you were fooled. The LLM simply happened to sound rhyme, while all it did was simply generating sequence based on the rap lyrics from the training data.

This limitation has significant implications for tasks such as lyric generation, where the ability to generate rhyming lines or maintain consistent rhyme schemes is essential. LLMs, without explicit training on phonetic data or specialized acoustic models, may struggle to produce lyrics that adhere to the intricate rhyming conventions found in various musical genres.

Related: A Computational Evaluation Framework for Singable Lyric Translation, {cite}`kim2023computational`

## Because LLMs don't know how to spell

The lack of phonetic understanding can also hinder LLMs' ability to accurately analyze or interpret lyrics that rely heavily on wordplay, puns, or deliberate mispronunciations – creative techniques commonly employed by songwriters and artists.

While there have been efforts to incorporate phonetic information into language models, either through specialized tokenization strategies or by integrating acoustic models, these approaches are still premature and often require significant additional training or architectural modifications.

## Future Direction

To truly leverage the power of LLMs for lyric-related tasks in MIR, it may be necessary to explore hybrid approaches that combine the language understanding capabilities of LLMs with dedicated acoustic or phonetic models. Alternatively, new training techniques that better preserve and incorporate phonetic information during the tokenization process could be explored.

Ultimately, the inability of current LLMs to fully grasp the nuances of sound and pronunciation in language is a significant limitation when it comes to music and lyrics, where these aspects are intrinsically tied to the artistic expression and creative process.

