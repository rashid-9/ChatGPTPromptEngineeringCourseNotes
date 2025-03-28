# Guidelines For Prompting

## Principles

### 1. Write Clear and Specific Instruction

<ins>Tactic 1: Use Delimiters (Delimiters are characters or sequences used to define the boundaries of different elements within a code construct.)</ins>
 - Triple Quotes: """
 - Triple backticks: ```
 - Triple Dashes: ---
 - Angle brackets: <>
 - XML tag: <tag>, </tag>

 Example:
```
text = f"""
You should express what you want a model to do by \ 
providing instructions that are as clear and \ 
specific as you can possibly make them. \ 
This will guide the model towards the desired output, \ 
and reduce the chances of receiving irrelevant \ 
or incorrect responses. Don't confuse writing a \ 
clear prompt with writing a short prompt. \ 
In many cases, longer prompts provide more clarity \ 
and context for the model, which can lead to \ 
more detailed and relevant outputs.
"""
prompt = f"""
Summarize the text delimited by triple backticks \ 
into a single sentence.
```{text}```
"""
response = get_completion(prompt)
print(response)
```

<ins>Tactic 2: Ask For A Structured Output (Like HTML OR JSON)</ins>
```
prompt = f"""
Generate a list of three made-up book titles along \ 
with their authors and genres. 
Provide them in JSON format with the following keys: 
book_id, title, author, genre.
"""
response = get_completion(prompt)
print(response)
```

<ins>Tactic 3: Check whether conditions are satisfied. Check assumptions required to do the task. </ins>
```
text_1 = f"""
Making a cup of tea is easy! First, you need to get some \ 
water boiling. While that's happening, \ 
grab a cup and put a tea bag in it. Once the water is \ 
hot enough, just pour it over the tea bag. \ 
Let it sit for a bit so the tea can steep. After a \ 
few minutes, take out the tea bag. If you \ 
like, you can add some sugar or milk to taste. \ 
And that's it! You've got yourself a delicious \ 
cup of tea to enjoy.
"""
prompt = f"""
You will be provided with text delimited by triple quotes. 
If it contains a sequence of instructions, \ 
re-write those instructions in the following format:

Step 1 - ...
Step 2 - …
…
Step N - …

If the text does not contain a sequence of instructions, \ 
then simply write \"No steps provided.\"

\"\"\"{text_1}\"\"\"
"""
response = get_completion(prompt)
print("Completion for Text 1:")
print(response)
```

<ins> Tactic 4: Few-Shot pormpting. Give successfull examples of completing tasks and then ask model to perform the task.</ins>
```
prompt = f"""
Your task is to answer in a consistent style.

<child>: Teach me about patience.

<grandparent>: The river that carves the deepest \ 
valley flows from a modest spring; the \ 
grandest symphony originates from a single note; \ 
the most intricate tapestry begins with a solitary thread.

<child>: Teach me about resilience.
"""
response = get_completion(prompt)
print(response)
```

### 2. Give the model enough time to think

If you give a model a complex task or problem to solve in a short amount of time, it make incorrect assumptions when trying to complete in a short time space, so you must give it enough time for it to think.

<ins> Tactic 1:  </ins>



### Limitations

<ins> Hallucinations </ins>

Makes statments that sound plausible but are not true

<ins> Reducing Hallucinations </ins>

First find relevant information, then asnwer the question based on the relevant information.

