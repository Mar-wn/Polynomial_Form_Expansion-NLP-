* In this challenge, we want to predict an expanded sequence from a factorized one.
* The task can be modeled as a **sequence to sequence translation model**. In fact, we can consider that the two forms belong to two different languages.

* To solve this problem, I built an **encoder decoder with an attention mechanism**.

* The idea behind the attention mechanism is that, for each output item generation, one would need to look back at different parts of the input rather than reading the input then generating translation at once. Thus, using attention, the model learns to determine the input items **it is useful to pay attention** to at each output item prediction.

* The encoder is a **bidirectional LSTM** that encodes the factorized input and passes its states to the attention step.

* Then, at each output timestep:

* The attention step defines the **attention weights** and therefore a **context vector**.
* The decoder is an LSTM that takes the context as input from the attention step and outputs new states.
* Finally, a softmax dense layer predicts the item at position t.


