# minerva
verification engine

# objective
predict
1. status : bin - 1 for correct 0 for incorrect
2. trustworthySources : List[Source] - populated source list to deciding status

# method
We feed 'summary' of takes into an LLM and ask it to web search for verifying documents. 
We then feed data from those 5 documents into an LLM to get a status on whether 
the 'summary' was correct (1) or incorrect (0).

## api 

```
/take
  /<takeId>
    /status
    /author
    /createdAtMillis
    /classification #always 1 for 'is a take'
    /summary
    /trustworthySources
```

# 'base truth' engine

## gpt-4o
We feed the below prompt into the gpt-4o api before feeding in data 
```
Tweet Analysis Framework

  1. Base Truth:

     Question: What is the fundamental statement or main message of the tweet?

     Purpose: This helps identify the core idea or assertion being made.

  2. Measurable Claim:

     Question: Does the tweet make a claim that can be supported or refuted
     by specific data points or a set of data points?

     Purpose: To distinguish between opinions and factual claims that can be
     tested or proven.

  3. Outcome and Timing:

     Question: What is the specific outcome or result mentioned in the tweet?
     Does this outcome relate to an event in the past, present, or future?

     Purpose: To determine the timeframe and nature of the outcome for tracking
     and validation purposes.
```
