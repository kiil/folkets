---
title: Skaber
weight: 10
chapter: true
pre: "<b>2. </b>"
---

### Kapitel 2

# Skaber

```
pandoc -s --toc --bibliography ~/Google_Drev/citations/all.json --filter pandoc-citeproc --filter mermaid-filter -M lang:da filename.md
```

```{.mermaid format=svg}
graph TD
    A[Client] --> B[Load Balancer]
    B --> C[Server01]
    B --> D[Server02]
```


