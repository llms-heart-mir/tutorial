# LLMs don't know every artist

While LLMs excel at generating human-like text and understanding natural language, they have a significant limitation when it comes to factual accuracy and comprehensive knowledge. This weakness is particularly relevant in the context of music information retrieval (MIR) tasks such as music metadata analysis and recommendation systems.

## A LLM alone does and will hallucinate

No matter how large, the training data of LLM is i) limited ii) and biased as well as potentially iii) conflicting and iv) outdated. Moreover, i) LLMs cannot remember everything and ii) they generate plausible-sounding but factually incorrect statements, a phenomenon known as "hallucination."

For example, an LLM might confidently provide information about a popular artist's discography or biographical details, but when prompted about a more obscure or niche artist, it may fabricate or hallucinate details to fill in the gaps in its knowledge. This can lead to inaccurate metadata or recommendations, undermining the trustworthiness and usefulness of the system.

Without access to authoritative and up-to-date sources of music information, LLMs alone cannot be relied upon as a competitive information retrieval model for music applications.

## Future Direction: Continual Training and Connection to Truthful Databases

To address this limitation, future developments in LLM-based music information retrieval systems should focus on two key areas:

1. **Continual Training**: LLMs should undergo continual training or fine-tuning on high-quality, curated datasets specific to the music domain. This process can help the model acquire and retain accurate knowledge about artists, albums, genres, and other music-related entities, reducing the likelihood of hallucination.

2. **Connection to Truthful Databases**: LLMs should be integrated with authoritative and up-to-date databases or knowledge bases containing verified information about music. This can be achieved through techniques like Retrieval-Augmented Generation (RAG), where the LLM generates text based on both its language model and information retrieved from a external database.

By combining continual training on domain-specific data and integration with truthful databases, LLMs can become more reliable and accurate sources of music information. This approach can improve the quality of music metadata analysis, recommendation systems, and other MIR applications that rely on factual knowledge about artists, albums, and genres.
