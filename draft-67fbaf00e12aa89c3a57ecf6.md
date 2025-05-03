---
title: "Query Translation Patterns (Advanced RAG)"
slug: query-translation-patterns-advanced-rag

---

\`Before jumping to the query translation patterns, I like to give a little introduction to RAG

RAG, or Retrieval-Augmented Generation, is when we want to create question answering and chatbots to improve response quality. It's a technique in natural language processing (NLP) that combines **retrieval-based** and **generation-based** methods to improve the performance of language models.

Now the question is how many ways to improve AI model performance for specific tasks or applications. So basically best way is two.

1. Fine Tuning
    
2. RAG
    

Fine-tuning has its problems, like modifying the model’s weights in LLM for as it is quite expensive and time-consuming, and it is not real-time.

What is Fine-tuning, and what are a model’s weights in LLM? How is it executed? I will discuss this in another article. Also, I will create on the basics of RAG.

There are 6 main points we have to follow up with the Advanced Rag.

1. Query Transformation
    
2. Routing
    
3. Query Construction
    
4. Indexing
    
5. Retrieval
    
6. Generation
    

So, in advance, RAG's priority is how to optimise the use of the query, which is uncontrollable.

For that, we use the first step is Query Transformation Patterns. We need to update and improve the user prompt.

Let me give you an overview of some portion of the NLP world, which will help you to understand it better. There is most popular word is Abstraction, and Less-abstraction. When we focus and generalise any prompt, which is Abstraction. When we detail any prompt is called Less-abstraction. We need both to get the best improved prompts.

So, for take both Abstraction and Less-abstraction, we need to take rewrite query, were we can see the RAG function and the Multi-query approach.

There is a technique we followed called Parallel Query(Fan out) Retrieval.

### Parallel Query(Fan out) Retrieval:

1. Represented by a stick figure on the left, indicating the starting point of the process (the user submits a query).
    
2. **Query Generation (Brain Icon)**:
    
    * A brain icon (likely representing an LLM) takes the user’s query and generates multiple sub-queries.
        
    * The brain splits the query into three parallel paths labelled "Query."
        
3. **Retrieval (Pinecone Cube)**:
    
    * Each sub-query is sent to a "Pinecone Cube," symbolising Pinecone’s vector database for retrieval.
        
    * Multiple Pinecone cubes are shown, indicating parallel retrieval across different indices or data sources.
        
    * Retrieved items are represented as small document icons (blue, yellow, red) next to each Pinecone cube, suggesting document chunks or results.
        
4. **Documents**:
    
    * A separate "Documents" box above the Pinecone cubes indicates the knowledge base from which documents are retrieved.
        
5. **Filtering (Filter Unique)**:
    
    * Retrieved document chunks are passed through a "\[filter\_unique\]" step, which deduplicates the results.
        
    * The output is a smaller set of unique document chunks (blue, yellow, red).
        
6. **Generation (Brain Icon)**:
    
    * The unique document chunks are fed into another brain icon (representing an LLM) for generation.
        
    * The LLM combines the chunks to produce the final result.
        
7. **Final Result**:
    
    * The final output is delivered back to the user, represented by a stick figure on the right with a speech bubble containing document icons.
        

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745420442747/01c2cc78-d20f-4236-920f-5e13396b428f.png align="center")