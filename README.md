# 🤖 Building a Cognitive Agent: Implementing Multi-Turn Memory Systems with RAG  

This repository demonstrates how to design and implement a cognitive agent using Retrieval-Augmented Generation (RAG) to simulate human-like memory systems. The agent is equipped with four types of memory systems to enhance multi-turn conversations and contextual understanding.  

## 🌟 Features  

- 🧠 **Working Memory**: Maintains current conversation and immediate context.  
- 🗂️ **Episodic Memory**: Stores historical interactions and their key takeaways.  
- 📚 **Semantic Memory**: Provides factual grounding and general knowledge context.  
- ⚙️ **Procedural Memory**: Encodes rules and skills for specific interactions.  

## 📖 Overview  

Language models (LLMs) are stateless by nature, but this project bridges that gap by incorporating memory systems into agent design. The approach draws inspiration from human cognition to improve the agent's understanding and adaptability in multi-turn interactions.  

## 🚀 Key Components  

1. **Working Memory**:  
   - Tracks the current conversation flow and context.  
   - Temporary, focused on the immediate task at hand.  

2. **Episodic Memory**:  
   - Stores historical events, user interactions, and their outcomes.  
   - Allows the agent to "remember" prior conversations and learn from them.  

3. **Semantic Memory**:  
   - Provides knowledge and factual grounding using external knowledge bases.  
   - Ensures accurate and informed responses.  

4. **Procedural Memory**:  
   - Implements rules and learned skills for interaction.  
   - Encodes "how-to" guides for performing tasks effectively.  

## 🛠️ Technologies Used  

- **Python** 🐍  
- **LangChain** 🔗  
- **Vector Databases** 📊  
- **LLMs** 💡 (e.g., OpenAI GPT, Zypher 7B LLM)  
- **Hugging Face Embeddings** 🤗  

# Memory Types in Agents and Humans

## **Procedural Memory**
- **Definition:** Long-term memory for how to perform tasks; akin to a brain’s core instruction set.
- **In Humans:** Remembering how to ride a bike.
- **In Agents:** 
  - Defined in the CoALA paper as a combination of **LLM weights** and **agent code** that determine how the agent operates.
  - **Current Practice:**
    - Few, if any, agentic systems update their LLM weights or rewrite their code automatically.
    - Some agents update their **system prompt** dynamically, though this is rare.

---

## **Semantic Memory**
- **Definition:** Long-term store of knowledge.
- **In Humans:** Facts learned in school, meanings of concepts, and their relationships.
- **In Agents:**
  - Defined in the CoALA paper as a **repository of facts about the world**.
  - **Usage:**
    - Personalizes applications by extracting information from interactions.
    - Application-specific storage, retrieved in future conversations to influence responses.

---

## **Episodic Memory**
- **Definition:** Recalling specific past events.
- **In Humans:** Remembering particular events or episodes experienced in the past.
- **In Agents:**
  - Defined in the CoALA paper as **storing sequences of past actions**.
  - **Usage:**
    - Implemented as **few-shot example prompting** or **dynamic few-shot prompting** with collected sequences.
    - Useful for tasks with a "correct" way of performing actions.
    - Differs from semantic memory, which is used when there’s no specific "correct" way to act or when new tasks arise frequently.

# Updating Agent Memory

## **1. How to Update Memory**
Developers consider two main ways to update agent memory:

### **In the Hot Path**
- **Definition:** The agent explicitly updates memory before responding, usually through tool-calling.
- **Example:** ChatGPT uses this approach.
- **Pros:**
  - Immediate memory updates.
- **Cons:**
  - Adds latency before delivering responses.
  - Combines memory logic with agent logic.

### **In the Background**
- **Definition:** A separate process updates memory during or after the conversation.
- **Pros:**
  - No added latency.
  - Keeps memory logic separate from agent logic.
- **Cons:**
  - Memory updates are not immediate.
  - Requires extra logic to determine when to trigger background updates.

### **User Feedback for Memory Updates**
- **Relevance:** Particularly useful for episodic memory.
- **Example:** If a user marks an interaction as positive, save the feedback for future use.

---

## **2. Why Memory Matters for Agents**
Memory significantly enhances the usefulness of agentic systems by enabling:
- Personalization
- Improved task performance through episodic and semantic recall

### **LangChain’s Contributions to Agent Memory**
LangChain simplifies leveraging memory in applications by providing:
1. **Low-level abstractions** for a memory store in **LangGraph**.
2. **Templates** for running memory updates both:
   - In the hot path
   - In the background
3. **Dynamic Few-Shot Example Selection** in **LangSmith** for rapid iteration.

---

## **3. Visual Comparison**

The image below demonstrates the two approaches:
- **In the Hot Path** (left side): Immediate memory updates before responding.
- **In the Background** (right side): Delayed memory updates via background processes.

![Alt text](images\hot_path_vs_background--2-.png)
