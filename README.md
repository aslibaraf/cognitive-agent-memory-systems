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

