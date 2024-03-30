# LLM-Scratch

1) Bigram Model from Scratch
2) Transfomer Architecture
3) GPT Architecture


## Transformer Architecture - 

Traditional sequence-to-sequence models like RNNs and LSTMs have certain limitations:

--They are sequential and cannot parallelize the computation effectively.
--Capturing long-range dependencies is challenging due to the vanishing and exploding gradient problems.
The Transformer was designed to address these issues using a self-attention mechanism that allows for capturing contextual information from different parts of the input sequence.

2. Basic Components
   
2.1 Self-Attention Mechanism - The self-attention mechanism computes a weighted sum of all input tokens for each token. This allows the model to focus on different parts of the input sequence differently.

2.2 Multi-Head Attention - Instead of using a single set of Query, Key, and Value matrices, the Transformer uses multiple sets (heads) to compute self-attention in parallel. The outputs of these heads are concatenated and linearly transformed.

2.3 Positional Encoding - Since the Transformer does not have any inherent notion of the order of tokens, positional encodings are added to the input embeddings to give the model information about the position of each token in the sequence.

4. Transformer Architecture
The Transformer architecture consists of an Encoder and a Decoder, both of which are composed of multiple identical layers.

3.1 Encoder
Input Embedding: Converts input tokens into continuous vectors.
Positional Encoding: Adds positional information to the input embeddings.
Multi-Head Self-Attention: Allows the model to focus on different parts of the input.
Feed-Forward Neural Networks: Applies a position-wise feed-forward network to each position separately and identically.
Normalization and Residual Connections: These are added around each sub-layer (attention and feed-forward) to help with training deep networks.
3.2 Decoder
Masked Multi-Head Self-Attention: Ensures that the predictions for a particular position can only depend on the known outputs at positions before it.
Multi-Head Encoder-Decoder Attention: Allows the decoder to focus on different parts of the input sequence.
Feed-Forward Neural Networks
Normalization and Residual Connections
4. Position-wise Feed-Forward Networks
Each layer in the Transformer has a position-wise feed-forward network consisting of two fully connected layers with a ReLU activation in between.

5. Normalization and Residual Connections
Normalization (Layer Normalization) is applied before each sub-layer, and residual connections are used around each sub-layer.

6. Final Output and Softmax
The final output of the decoder is passed through a linear layer followed by a softmax function to produce the final probability distribution over the output vocabulary.

Training and Inference
Training: The model is trained using the teacher forcing technique. The input to the decoder at each step is the actual output sequence up to that step.
Inference: During inference, the output at each step is fed back into the decoder to produce the next token until an end-of-sequence token is generated or a maximum length is reached.
