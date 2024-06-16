# Pre-Training, and the Induced Properties

The (pre- or post-)training of LLMs follows the typical training procedure of neural networks. 

Repeat this many, many times:
- Let the model make a prediction: $\hat{y} = f(x)$
- Measure how it did: loss function $f_{loss}(\hat{y}, y)$
- Backpropgation to update model weights $\theta$: $\theta \leftarrow \theta - \eta \frac{\partial f_{loss}}{\partial \theta}$

But the detail varies by domains and tasks; and LLMs have their own training recipe. It is highly scalable and efficient - I can say. But in terms of what? We'll cover this soon.

The training configuration i.e., what to predict and how to measure the loss, determines some important properties of LLMs. We'll cover this as well in this chapter.

Ready? Let's go 🛢
