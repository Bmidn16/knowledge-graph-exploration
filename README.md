# knowledge-graph-exploration

# Utilizing ```het.io```

My introduction into accessing and utilizing cypher queries to read data from knowledge graphs

My first step was getting familiar with Neo4J Cypher queries that I learned of Neo4J's Graph Academy courses

From here, I was able to utilize these cypher queries when acessing the het.io Neo4J platform at https://neo4j.het.io/browser/

1. Intital request to collect the symptoms for each disease:
```
MATCH (d:Disease)--(s:Symptom) RETURN d.name,collect(s.name)
```

2. Visualiztion using a network graph
```
CALL db.schema()
```

From ehre, we can do a wide range of queries.

For one example, we can look at collecting genes assosicated with each disease:

3. The collection of genes associated with each disease
```
MATCH (d:Disease)--(g:Gene) RETURN d.name,collect(g.name)
```

4. Counting the number of genes and pathways for each of the diseases
```
MATCH (d:Disease)--(g:Gene)--(p:Pathway) RETURN d.name,count(g.name),count(p.name)
```

5. Counting and colelcting associated compounds with disease
```
MATCH (d:Disease)--(c:Compound)--(s:SideEffect) 
RETURN d.name,count(DISTINCT c.name),collect(DISTINCT c.name)
```

6. And for the last part, we can visualize the associated compound with disease and side effects at a scale of a 100 nodes

```
MATCH p=(d:Disease)--(c:Compound)--(s:SideEffect) RETURN p LIMIT 100
```

7. In addition, if you want the visualize with the subgraphs of Disease, Gene, AND Pathways at the same scale of a 100 nodes
```
MATCH path=(d:Disease)--(g:Gene)--(p:Pathway) RETURN path LIMIT 100
```






