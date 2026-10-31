# Basics

1. How to design the prompt for better output
2. prompt workflow
3. prompt template, constraint, role, example
4.  

syllabus

1. unit 1 basics
2. unit 2 how to improve

gradding scheme : Total : (CA) 40 + (practical) 40 + (viva) 20 = 80

LLM output depends on

1. output length 
  1. longer : model keep emitting useless tokens after desired response, high energy consumption, longer response time
  2. shorter : insufficient answers,  less precision,models sopts predicting tokens after limit
2. How are token selection (sampling control) (not set to extreem, it will have too much randomness)
  1. temperature
    1. 0 : no randomness (greedy decoding) : deterministis
    2. 1 : more creative  
  2. Top-k
    1. 1 : greedy decoding
    2. 30(some random more no.) : exterese high value render the filter irrelevant
  3. Top-p
    1. select top token which have sum of token to 1, then select ransom from them
    2. 0 : most probable
    3. 1 : all tokens concidered
  4.  

 

 