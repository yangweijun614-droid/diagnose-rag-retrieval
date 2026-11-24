---
name: diagnose-rag-retrieval
description: Use when a RAG system fails to retrieve a known relevant passage, ranks it too low, or drops it before generation. 适用于 RAG 检索问题排查。
---

# RAG 检索排查

选一条失败问题和一段已知能回答它的原文。记录原文的文档 ID 或位置，沿处理链查找它第一次消失的环节。

1. 检查原文是否进入索引，切块后是否仍包含关键句和必要上下文。
2. 比较初次检索、过滤及重排后的文档 ID 和名次。只检查实际存在的环节。
3. 检查保留下来的段落是否进入最终上下文。如果证据已传入模型，就结合提示词和答案看模型如何使用它。

输出第一处有证据支持的异常、一个最小改动，以及如何用同一问题验证它。缺少中间结果时，写清需要补看的记录。

示例：目标段落在重排前位列第 3，重排后掉到第 12，而生成只接收前 5 段。先隔离验证重排对该段落的影响。
