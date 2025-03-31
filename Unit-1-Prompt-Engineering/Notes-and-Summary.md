# Notes and Summary on Prompt Engineering (Unit 1)

## Table of Contents

1. [What is Prompt Engineering?](#what-is-prompt-engineering)
2. [What is a Prompt?](#what-is-a-prompt)
3. [LLM output configuration](#llm-output-configuration)
4. [Prompting Techniques](#prompting-techniques)
5. [Best Practices for Prompting](#best-practices-for-prompting)

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
- Defines the model's capabilities
- It is like providing another task to the system. 

### 5. Contextual prompting

- Providing specific details and background to the model
- Highly task-specific

### 6. Role prompting

- Model should take specific character or role
- Frames the output style

### 7. Step-back prompting

- Prevent the model from jumping straight into the answer
- Provide a more general question first
- Provide the specific question later

### 8. Chain-of-thought prompting (CoT)

- Asking the model to think step-by-step
- Helps the model to break down the problem into smaller parts

### 9. Self-consistency prompting

- Asking the model to generate multiple outputs for the same prompt
- Select the most common output
- Helps to improve accuracy and coherence of the output

### 10. Tree-of-thought prompting (ToT)

- Generalizes CoT prompting
- Exploration of multiple different reasoning paths

## Best Practices for Prompting

- Provide examples
    - Allows the model to learn and tailor responses
- Keep it simple and clear
    - Prompt should be easy to understand by you and the model
- Be specific
    - Not generic
    - Provide details and context
- Define instructions and set constraints
    - Instructions: define desired format, style or content
    - Constraints: define limitations or restrictions (things the model should avoid)
- Control maximum token length
    - Set limit (max token limit)
    - Define length in prompt
- Use variables as placeholders
    ```
    VARIABLES
    {country} = "Germany"
    PROMPT
    "Tell me about the capital of {country}."
    ```
- Experiment with input formats, writing styles, and output formats
- Document prompt attempts