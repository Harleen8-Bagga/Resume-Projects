# HANGMAN-VERSION using n-gram logic

##  Purpose
This code can play a game of hangman, given a word with blank spaces and 6 guesses (head, body, arms and legs) will return the best letter to guess.

## Method Used
- I used n-gram interpolation algorithm to enable the game to guess a letter. N-grams are typically used to determine the likelihood of a word following another, but in this case we will use it for letters.

Approach:

- The algorithm utilized a cascade of five, four, three, two, and one-gram models with a weighted average approach. The choice of five as the cut-off of the n-gram is based on the observation that as the order of n-grams goes beyond five, the number of unique n-grams encountered in the corpus tends to decrease significantly. Choice of the 5-gram model as the cut-off model was to balance the accuracy of capturing longer-range dependencies and the practical limitations imposed by data sparsity.

- After constructing the n-grams, for each n-gram, the algorithm estimates the probability of the next letter given the context of the partially revealed word. The algorithm then assigns weights to each of the n-gram models based on their importance in guessing the letter. This is followed by the multiplication of the probabilities of the n-gram with their respective weights.

- Based on the calculated weighted average probabilities, the algorithm chooses the letter with the highest probability as the next likely occurring letter.

- If no letter is chosen from the above procedure, the algorithm chooses the words from the most common occurring in the corpus with extra weight given to the vowels.

## Gameplay

- We can start a game by either selecting a random word from the dictionary, or by passing our own word as a string. The word is then converted into blanks (underscores separated by spaces) and is fed to the model to guess the first letter. For example, "hangman" is converted to "_ _ _ _ _ _ _". Any correctly guessed letter will replace the underscore, and this new string is passed for the next guess.

- This string is then passed over to find any potential n-grams. For example, a unigram can be where there is any single blank space (in the above example, that would be every single space). A bigram can be anywhere with a blank and a letter, no matter the order, meaning "letter-blank" is a bigram as is "blank-letter". Therefore a single blank space can be multiple n-grams. If the current status of the word is "g i _ h u b", the blank space is a unigram, bigram (for both "i " and " h"), trigram ("g i ", "i _ h", " h u"), four-gram and five-gram.

- For each blank, a vector of probabilities for each letter not yet guessed is tabulated by calculating the frequencies of each n-gram, with more weight given to larger n. The letter with the highest probability is taken.

## Test

- The model is trained on a dictionary of 250,000 word. On this training set the winning rate of designed hangman game is 65%

- To see how the model performed on completely new words, another dictionary of words was used for test. In this new set of words, the model has a success rate of around 54%





