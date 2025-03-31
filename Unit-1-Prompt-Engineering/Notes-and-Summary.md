# Notes and Summary on Prompt Engineering (Unit 1)

## What is Prompt Engineering?

- Process of designing high-quality prompts to help the LLM to generate the desired output

## What is a Prompt?

- Input provided to the model

## LLM output configuration

### 1. Output length

- Setting a limit on the number of tokens
- More tokens &rarr; requires more computation &rarr; higher energy consumption, slower response time, higher costs
- Once limit of tokens is reached, the model stops generating text

### 2. Sampling controls

#### 2.1 Temperature

- Temperature controls the degree of randomness in the token selection
- Lower temperature &rarr; more deterministic output (more likely to select the most probable token)
- Higher temperature &rarr; more random output (more likely to select less probable tokens)
- Temperature range: 0 (greedy decoding) to 1

#### 2.2 Top-k sampling
- Select top k tokens with the highest probabilities
- higher top-K &rarr; more randomness (more creative output)
- lower top-K &rarr; more deterministic output (less creative output)

#### 2.3 Top-p (nucleus sampling)

- Select top tokens with cumulative probability p
- Values between 0 (greedy decoding) and 1 (all tokens)

## Prompting Techniques

### 1. General prompting/ Zero-shot prompting

- Only provide description of the task to the model
- No examples provided

- Example: "Translate the following English text to French: 'Hello, how are you?'"

### 2. One-shot prompting

- Provide one example of the task to the model
- Example: "Translate the following English text to French: 'Hello, how are you?' 'Bonjour, comment ça va?'"

### 3. Few-shot prompting

- Provide few examples of the task to the model
- Rule of thumb: 3-5 examples
- Use relevant examples to the task

### 4. System prompting

- Setting the big picture for the response

#### 5. Contextual prompting

- Providing specific details and background to the model

#### 6. Role prompting

-