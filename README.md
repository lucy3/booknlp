# BookNLP

## This version ("Lucy's version") has improved character name clustering 

Original booknlp: https://github.com/booknlp/booknlp/tree/main

Our changes and motivation, from [our paper](https://culturalanalytics.org/article/131682-racial-and-ethnic-representation-in-literature-taught-in-us-high-schools): 

> We obtained character names using BookNLP, which combines coreference resolution and character name clustering to count all mentions and references to a character under a unique identifier. Initially, we observed that the default implementation of BookNLP yielded character lists that conflate key characters with each other or splits key characters among multiple character IDs. These errors originated from BookNLP’s character name clustering module, which groups aliases into characters based on overlapping substrings, e.g. Khalil Khalil Harris in The Hate U Give. These one-off named entity recognition errors can lead to main characters being incorrectly merged (e.g. Jo and Meg in Little Women), or split one character (e.g. Oliver in Oliver Twist) across multiple character IDs. We implemented two modifications to this name clustering process to improve our character lists: first, we avoided grouping characters based on overlap with an alias that only appears once, and second, we forced popular proper names of people to only be attached to one character. The latter modification assumes that authors rarely give multiple main characters the same frequently mentioned name.

Evaluation results can be found in section 4.3 of the paper linked above, showing improved precision and purity for "main" characters of books. 
