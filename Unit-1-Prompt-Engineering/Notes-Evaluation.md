# Evaluation LLMs

- You can use LLMs to evaluate the output of other LLMs
- To reduce error, try different models as judges (like Gemini, Claude, ChatGPT, etc.)

## Pointwise evaluation

- Use a judge model to evaluate the output of a candidate model
- Evaluate a single input/output pair given some criteria
- Good for answering the questions, e.g., "Is this answer correct?" or "Is this answer relevant to the question?"
- Assigns a score to the output representing how well the output (e.g. score between 0 and 5)

## Pairwise evaluation

- Judge model evaluates two outputs (e.g. output A and output B) and assigns a score to each output
- Choose then the best output (e.g. output A is better than output B)