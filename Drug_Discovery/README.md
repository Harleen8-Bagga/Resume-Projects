### Introducing the problem statement
- In chemoinformatics we have the SMILES representation of molecules. SMILES is an acronym for Simplified molecular-input line-entry system, details can be found on the Wikipedia page on the subject. In short its a way to specify a molecule as a single line of text.
- (Smiles = molecules as text) + Recurrent Neural Networks + Database of drug like molecules => Computational Molecular Generation

#### Approach to the problem
1- **Selection of the Network Architecture (VAE composed of LSTM Encoder & Decoder)**
- Data collection in **SMILES** format.
- SMILES represent the chemical compounds in string format.
- Since this is a **sequence task, LSTM** is the preferred choice of the neural network architecture for generating new SMILES string.

2- **Data Preprocessing Steps**
- Collect all the **unique characters** from the dataset.
- Create **two dictionaries**, one mapping all the unique characters to the index while the other mapping index back to character.
- Encode all the SMILES string into **one hot vectors** (character based) to feed into the network.
- Append **start token** at the beginning of each SMILE string and **end token** to mark the end of the string.
- Make all the SMILES string of **same length** for training in batch by padding smaller SMILE strings with end token.
- **Labels will be shifted** by one unit from the inputs for **teacher forcing method** to train the sequence model.
- Build the lstm encoder and decoder network.
- Train the network end to end using one hot encoded SMILES string.

3- **Inference from the decoder**
- After training the network, feed random samples to the decoder to generate new SMILES string.
