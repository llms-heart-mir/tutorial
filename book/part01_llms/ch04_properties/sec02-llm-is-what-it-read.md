# A LLM is What It Read

Yes, we still argue large data vs. clean data. Of course the answer is large and clean data. This applies to LLMs. But how exactly?

It's always related to the next-token prediction.

## Normal Data

Let's take the sentences above as an example of normal, typical data.
It's okay to use this to train a LLM, because it is fine and would be useful to learn predict next tokens from this sequence. 

> Yes, we still argue large data vs. clean data. Of course the answer is large and clean data. This applies to LLMs. But how exactly?


## Dirty Data for Next-token Prediction

This is a randomly shuffled word sequence. 

> to data large yes clean always data. data. to prediction. applies is we how argue answer the Of But next-token and exactly? This It's the LLMs. large related clean vs. still course 

It is not only difficult but also useless to learn to predict the next tokens from the sentence above. 

> cocococodsdse wefse3 ewwv3 eewdd d eew dwdll ojrvv ozvkd ewm211ofs @lf

> 가ffdj 나ㅏㅏㅏㅏqvbblf rdp d e r 3 3 r fd % 

These are not any language; Again, it'd be a waste to train LLMs with this sequence. 

## Banal Data for Next-token Prediction

> Good morning! How are you today?<br>
> Hi, how is everything going on? Hope you are doing well.<br>
> Hello, there! I was wondering if..<br>
> Hi! How was your weekend?<br>

These kinds of sentences are too common that after a bit of training, a LLM would be able to perform the next-token prediction pretty well, too well, well enough that seeing these sentences once more wouldn't make the LLM any stronger.

## High-quality Data

So what is high-quality data? It depends on what you want, but you'd want to make sure your LLM is trained to predict all the rare, domain-specific, and important tokens in the right context. 

For example, for music AI:


> Much of the time, the pianist isn’t improvising. Certainly Jamal must mix it up from night to night, but the general plan is always highly organized. On “No Greater Love” there’s a chorus and a half where Jamal seems to really “blow.” It’s not pure bebop, but a collection of tricks and tips, all done with astonishing rhythmic panache.
> His left hand pulses on the off beat, going straight into the engine room with the bass and drums. Jamal had been doing this for a while; it is one of the many details Miles Davis seems to have encouraged Red Garland to copy.

(quote from [Ethan Iverson's blog](https://iverson.substack.com/p/tt-240-ahmad-jamal-at-the-pershing))

For a legal AI:

> The challenge of identifying discrimination based upon loan acceptance and rejection data is great given the number of factors that might influence a bank's decision to extend credit. The most comprehensive study completed to date was conducted by the Federal Reserve Bank of Boston in 1990.

(quote from local enforcement of laws prohibiting discrimination in housing: the new york city human rights commission)

For a scientific AI:

> A single polymer chain is as soft as living tissue and as strong as carbon fiber. However, rubber bands are weak, and carbon fibers are strong, even though both consist of carbon-carbon bonds. Can soft materials be as strong as carbon fiber? The answer lies in the molecular structure. In a soft material, polymer chains crosslink and entangle, forming a polymer network. Therefore, it is the topology of the polymer network that determines whether the soft material is strong or weak. More importantly, the topology of the polymer network can be engineered. Designing the network topology has enormous potential to achieve extreme material properties, poses fundamental questions in mechanics and material science, and opens new possibilities for diverse applications.

(quote from [Soft Matter Mechanics Lab](https://www.junsoo.kim/research))

The key idea is to curate examples containing rare, technical, and context-specific language that challenges the LLM to learn nuanced, domain-specific representations.

