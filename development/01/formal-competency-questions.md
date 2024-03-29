# Formal Competency Questions

## CQ_1.1
Return a list of all the terms included in the `vocabulary_a`.

```
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX gtvo: <https://gotriple.eu/ontology/triple/gtvo#>

SELECT * WHERE {
  ?sub skos:inScheme gtvo:terms .
}
```

## CQ_1.2
Return the vocabulary name that contains the term `term_a`.

```
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX gtvo: <https://gotriple.eu/ontology/triple/gtvo#>

SELECT ?schema WHERE {
  gtvo:term_a skos:inScheme ?schema .
}
```

## CQ_1.3
Return all external entities to which the term `term_a` is connected.

```
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX gtvo: <https://gotriple.eu/ontology/triple/gtvo#>

SELECT ?entities WHERE {
  { gtvo:term_a skos:closeMatch ?entities . }
  UNION
  { gtvo:term_a skos:exactMatch ?entities . }
}
```

## CQ_1.4
Return external entities that are closely related to the term `term_a`.

```
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX gtvo: <https://gotriple.eu/ontology/triple/gtvo#>

SELECT ?entities WHERE {
  gtvo:term_a skos:closeMatch ?entities .
}
```

## CQ_1.5
Return external entities that are closely related to the term `term_a`.

```
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX gtvo: <https://gotriple.eu/ontology/triple/gtvo#>

SELECT ?entities WHERE {
  gtvo:term_a skos:exactMatch ?entities .
}
```