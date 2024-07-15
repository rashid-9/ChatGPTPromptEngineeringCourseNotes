# Lesson 1

## Two Types of Large language models (LLM'S)

 ### - Base LLM

 Predicts next word, based on text training data

 **Example 1:**
 
```
//Users input

 Once upon a time, there was a unicorn
```

```
///Bots output

that lived in a magical forest with all her unicorn friends
```

**Example 2:**
 
```
//Users input

 What is the capital of France?
```

```
///Bots output

What is France's largest City?
What is France's population?
What is the currency of France?
```

  ### - Instruction Tuned LLM

Tries to follow instructiona

It works by first starting with a Base LLM that has been trained with a huge set of text data and then further fine tune it on instruction and good attempts at following these instructions

Then further refine using a technique called Reinforcement learning with human feedback (RLHF).

**Example 1:**
 
```
//Users input

 What is the capital of France?
```

```
///Bots output

The capital of France is Paris
```
  
