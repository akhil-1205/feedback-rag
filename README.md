# Feedback-RAG
RAG model that can accomodate user inputs after a generic query-retrieval-generation.

## Workflow
Imported data, chunked it, embedded it and stored it in a FAISS vector index.
A query is prompted (by the user) and a chunk is semantically searched.
The chunk and the query is passed to the LLM to generate an answer.

Feedback is taken from the user regarding the generated answer.
The feedback, chunk, query and even response is sent to an internal LLM call.
This LLM call creates a new chunk with new information.
The new chunk is now embedded and replaces the old chunk.

A new query asking the same question would retrieve the same chunk and represent the new information.

## Usecase?
Any sort of internal company procedures face issues where concepts are very qualitative and would require some additional information to be added.
Procedures often have tiny changes and this can also be done using this.

## Implementation
An old [HP tablet user manual](https://h10032.www1.hp.com/ctg/Manual/c04491263.pdf) is used for now. A company procedure would be more apt though.

