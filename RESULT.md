# Evaluation Results & Findings

## Results Table

| Query | Keyword rank | Semantic rank |
|---|---|---|
| my redis cache keeps showing old data | 8 | 1 |
| how do I add semantic search to a table I already have | miss | 2 |
| redis or memcached for caching | 1 | 2 |
| why did my query get slower after I added an index | miss | 1 |
| what does ACID actually guarantee | 2 | 1 |
| how do I keep my postgres online while changing the schema | 6 | 3 |
| my background jobs stop after every deploy | miss | 2 |
| how do I let my database accept more writes per second | 4 | 1 |
| sql or nosql for a new product | 1 | 3 |
| why does my redis memory keep climbing | miss | 2 |
| **Summary** | **MRR 0.30 · Recall@10 0.60** | **MRR 0.67 · Recall@10 1.00** |

## Interpretation

Semantic search outperforms keyword search by a wide margin across both metrics, achieving an MRR of 0.67 compared to 0.30 and achieving a perfect Recall@10 of 1.00 compared to 0.60. Keyword search performed better on exact comparison queries—specifically "redis or memcached for caching" (rank 1 vs. 2) and "sql or nosql for a new product" (rank 1 vs. 3)—which both contain specific, well-defined technical keywords that directly match the post titles verbatim. In contrast, semantic search dominated conversational, descriptive, and symptom-focused queries such as "why does my redis memory keep climbing", "my background jobs stop after every deploy", and "why did my query get slower after I added an index", where users articulated problems in natural language rather than standard technical terminology. While keyword search suffered four total misses due to this vocabulary mismatch, semantic search successfully mapped the underlying user intent to relevant post concepts and returned a correct result in the top three for every single query. Engineering teams often maintain the keyword search system alongside semantic search in a hybrid retrieval architecture because exact keyword and token matching remains indispensable for acronyms, specific error messages, and precise product names where vector embeddings can sometimes lose specificity.
