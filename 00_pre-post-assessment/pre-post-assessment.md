---
title: Pre/Post-Assessment
author: Thomas Graf
geometry: margin=1in, letterpaper
fontsize: 12pt
numbersections: true
fontfamily: mathdesign
fontfamilyoptions: charter
---

For all of the exercises below, your code should contain doctrings following the [`numpy` conventions](https://numpydoc.readthedocs.io/en/latest/format.html).

# Syllable counting

Write a program that automatically counts the number of syllables in an English word.
Your count should be based on the actual pronunciation, not the spelling!

*Hint*:
You'll need the right corpus for this, then the rest will be easy.

# Style comparison

Provide a quantitative estimate of the frequency of English *yeah* in written texts vs oral speech.

*Hint*:
Again, this is mostly about picking adequate corpora.

# Edit distance

Write a function that takes two strings and returns their *Hamming distance*, if it is defined.
The function should raise an error otherwise.

*Hint*:
Pretty trivial as long as you know the definition of Hamming distance.

# n-gram models

Get the list of all words that occur in the Brown corpus, and add an out-of-distribution item to it.
From this, construct the set of all possible trigrams and determine their frequencies based on the Brown corpus.
Then smooth the frequencies using Add-`alpha` smoothing with `alpha = 2`.
Using these trigram frequencies, what is the probability of the sentence *This class has taught me a lot*?

# Smoother smoothing

This continues the previous exercise.
Instead of using Add-`alpha` smoothing, use linear interpolation of trigrams, bigrams, and unigrams.
Assume a respective weighting of `.5`, `.35`, and `.15` for trigrams, bigrams, and unigrams.

# Meaning

Write a function that takes as its input a list of words and an integer `n`.
The function should find the `n` most common words in the text that aren't stopwords, together with their Wordnet definitions, and write them to a file in reverse alphabetical order of the words.
Run your function on the Reuters corpus.

# Data cleaning

Write a script that retrieves a book of your choice from Project Gutenberg.
Use a regular expression to tokenize the text, then remove all stopwords and lowercase all remaining tokens.

*Hint*:
Pick a book that you can download as a `txt` file.
Other formats like `html` and `epub` have lots of markup in them that requires quite a bit of extra work to get rid off.

# Efficient search

Write a function that takes a sorted list and another argument `a`, and then uses binary search to determine if `a` is in the list.
Measure how long your function takes relative to Python's built-in list search when called on the (alphabetically sorted) text of NLTK's sample of the Penn treebank.

*Hint*:
The corpus is called `treebank` in NLTK.

# POS tagging

Write a function that reads in a file that only contains sentences of English and creates a file where each word has been tagged with its part of speech.
The name of the output file should be based on the name of the input file and include the current date and time.

*Hint:*
`Spacy` has a built-in tagger.

# Lexicon

Write a class that represents a mental lexicon as a prefix tree.
It should come with methods to add new entries and to read in new words from a file (with one word per line).
It should also have a method that takes a word as its only input and returns `True` if the word is in the lexicon; otherwise it returns `False`.

*Hint:*
It's not very space efficient, but you can implement your prefix tree as nested dictionaries.
Building your own implementation is way beyond the scope of this course.

# Finite-state automata

Implement a class for (deterministic) finite-state automata (FSA) that provides the following functionality:

- initialize an FSA based on a json file
- test whether the FSA is deterministic and raise an error if it isn't
- generate a random string that is recognized by the automaton
- say whether a given string is recognized by the automaton
