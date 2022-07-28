# knowledge-graph-exploration

# Utilizing ```het.io```

My introduction into accessing and utilizing cypher queries to read data from knowledge graphs

My first step was getting familiar with Neo4J Cypher queries that I learned of Neo4J's Graph Academy courses

From here, I was able to utilize these cypher queries when acessing the het.io Neo4J platform at https://neo4j.het.io/browser/

1. Intital request to collect the symptoms for each disease:
```
MATCH (d:Disease)--(s:Symptom) RETURN d.name,collect(s.name)
```




