# minerva
verification engine

# objective
predict
1. status : bin - 1 for correct 0 for incorrect
2. trustworthySources : List[Source] - populated source list to deciding status

# method
We feed 'summary' of takes into an LLM and ask it to web search for verifying documents. We then feed data from those 5 documents into an LLM to get a status on whether the 'summary' was correct (1) or incorrect (0).

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
