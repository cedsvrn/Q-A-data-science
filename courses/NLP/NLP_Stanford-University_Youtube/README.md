# NLP Stanford University course
https://www.youtube.com/watch?v=oWsMIW-5xUc&list=PLLssT5z_DsK8HbD2sPcUIDfQ7zmBarMYv


## Course 1 : Introduction
Mostly solved :
- Spam detection
- Part-of-speech (POS) : Saying "blue" is an adjective, "drink" is a verb ...
- Named entity recognition (NER) : Saying "Einstein" is a person, "Paris" is a localisation ...

Making good progress : 
- Sentiment analysis
- Coreference resolution
- Word sense disambiguation (WSD) : knowing if mouse is an item or an animal
- Parsing
- Machine translation (MT)
- Information extraction : "You're invited in Paris, Sunday 10th february at 10:45" -> "Paris", "Sunday 10th february", "10:45"

Still really hard :
- Question answering (QA)
- Paraphrase : saying the same thing with other words
- Summarization
- Dialog

## Collaborative filtering vs Content based
Goal : recommend a product P to a user A

- Collaborative filtering (CF) : Try to  find similar user to A and recommend what those users consumes.
Cons : Cold start (need user-item interactions), algorithms not standards.
- Content based (CB) :  Regroup products and recommend products close to P. 
Pros : Classification problem.
