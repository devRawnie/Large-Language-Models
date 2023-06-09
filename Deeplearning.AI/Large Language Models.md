# Tutorial

## Types of LLM


## Instruction Tuned LLM

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/5b00707b-15c0-4c0f-bbc6-cf042d466236)

- A Base LLM is trained using Re-Inforcement Learning to become an Instruction Tuned LLM

## Principles of Prompting

### Write clear and specific instructions
1. Use delimiters like Triple Quotes, Triple Backticks, Triple Dashes, Angle Brackets etc. It prevents the risk of **Prompt Injection** where the user can modify the prompt and ask the Model to do something else

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/4224e0b5-aad2-4a54-a047-a9fc78370267)

2. Ask for a structured output. For example ask for output in JSON format and specify the keys that you want in the JSON
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/bb62154c-003f-4d81-a7ad-ea06e8e1417b)


3. Ask the model to perform an operation if a particular condition is satisfied, otherwise it can perform an alternative operation
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/0fae570c-db51-40eb-8781-8b95900d4321)


4. *Few Shot* Prompting : Provide the model some successful examples of a response, before asking the model to generate a prompt
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/b4e7fb7d-ba08-499f-b84c-cdea62754efe)


### Give the model time to generate a response

1. Specify the steps required to complete a task. This will prevent the model from making errors and generate a better expected response

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/2588d4b8-e8cb-4fd0-9ad9-3b9f55cff154)
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/520aa5d9-f580-4505-8910-c48612f7cba7)

2. Instruct the model to work out its own solution before rushing to a conclusion

```py
prompt = f"""
Your task is to determine if the student's solution \
is correct or not.
To solve the problem do the following:
- First, work out your own solution to the problem. 
- Then compare your solution to the student's solution \ 
and evaluate if the student's solution is correct or not. 
Don't decide if the student's solution is correct until 
you have done the problem yourself.

Use the following format:
Question:
'''
question here
'''
Student's solution:
'''
student's solution here
'''
Actual solution:
'''
steps to work out the solution and your solution here
'''
Is the student's solution the same as actual solution \
just calculated:
'''
yes or no
'''
Student grade:
'''
correct or incorrect
'''

Question:
'''
I'm building a solar power installation and I need help \
working out the financials. 
- Land costs $100 / square foot
- I can buy solar panels for $250 / square foot
- I negotiated a contract for maintenance that will cost \
me a flat $100k per year, and an additional $10 / square \
foot
What is the total cost for the first year of operations \
as a function of the number of square feet.
''' 
Student's solution:
'''
Let x be the size of the installation in square feet.
Costs:
1. Land cost: 100x
2. Solar panel cost: 250x
3. Maintenance cost: 100,000 + 100x
Total cost: 100x + 250x + 100,000 + 100x = 450x + 100,000
'''
Actual solution:
"""
response = get_completion(prompt)
print(response)
```

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/4ade8b53-cf72-4368-9d54-7c46ae93b97b)


### Model Limitations

- Hallucinations : The model can make up statements about things that do not exist
- To avoid hallucination : Ask the model to find relevant information first, then based on that information the model should answer questions

## Summarizing

- Control character count by using following in the prompt
  - `at most 30 words`
  - `in 3 sentences`
  - `using 250 characters`
- Use `Extract` instead of `Summarize`
  - Ex: `Extract relevant information`

## Inferring

- Sentiment Analysis
  - Determine the sentiment (positive, negative) for a piece of text
  - Identify different types of emotions from the piece of text
  - Identify topics being discussed in a piece of text

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/77b0f72a-b3f3-4772-893e-3a2ab01e2e93)

## Transforming

- Language transformation
- Grammar Checking
- Tone Adjustment (Professional <-> Casual)
- Format Conversion (HTML <-> JSON)

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/f7c5470b-70de-4acd-b710-43d7583e44ae)
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/4afe95cd-6830-4539-8596-26a3f5f61f14)

## Expanding
- Generate longer text based on a shorter prompt
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/ded038e2-2afa-4df4-9c1e-f4d3141d61a0)

## Temperature
- It is a real number between 0 and 1
- 0 : Model will choose the most predictable word for completion
- Higher the value of temperature, more the response will diverge from the most predictable response

## ChatBot

In ChatGPT, we can send a series of messages with an extra parameter "role" to train the ChatGPT model as a Chat Bot to get Chat Completions

![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/98538075-600a-455c-974b-c1b05b9899a2)
![image](https://github.com/devRawnie/Large-Language-Models/assets/43227329/05359816-0cc2-488d-9b77-4dc845c609ea)
