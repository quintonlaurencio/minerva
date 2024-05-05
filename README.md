# minerva
verification engine

# objective
predict
1. status : bin - 1 for correct 0 for incorrect
2. trustworthySources : List[Source] - populated source list to deciding status

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
