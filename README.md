# Aptamer-Project
A repository for code written during my internship at Frederick National Labs, working on potential RNA Aptamers for the protein PrPc (bovine prion protein).

Summary: The project aims to propose RNA sequences (aptamers) which bind to a target protein, ‘PrPc’ (bovine prion) with high affinity, starting from an experimental sequence ‘2RU7’ (https://www.rcsb.org/structure/2ru7). This involves modelling the structure of 2RU7, using both secondary and tertiary structure prediction programs such as ViennaRNA, Unafold, RNAComposer and iCn3D; and modelling the protein-RNA complex, to be done via rigid body docking simulations using the existing PDB structures, and also molecular dynamic simulations. The aim is then to propose aptamers which produce similar secondary and tertiary structure, and assess their binding. For candidate aptamers, compare substrate-binding affinities with ‘2RU7’, aiming to " beat the current standard”.

Apta-MCTS (https://github.com/leekh7411/Apta-MCTS) generates a large number of potential RNA aptamer sequences, which may bind with good affinity to a target peptide. It's proposed as an 'in-silico' alternative to SELEX, the process of generating a large number of physical aptamer sequences, which is highly expensive and time-consuming. It instead uses a Random Forest model trained on preexisting Aptamer-Protein Interaction(API) data, and generates candidates via a Monte Carlo Tree Search algorithm. The program is not deterministic, which presents a problem in determining the ideal aptamer sequences to move forward with into docking simulations.

1. Apta-MCTS_and_TN93_Exploration: My initial exploration of the behaviour of the program. My mentor was interested to know whether the tree search algorithm might produce the same set of aptamers if fed the same input conditions, and to what degree. Is it completely deterministic, does it produce some recurring sequences in each batch, or is it entirely new each time? To what extent does this depend on the aptamer length, n(size of search space is 4^n)? Finding was that the algorithm is highly unlikely to **exactly** duplicate a sequence. From this, we get into methods of trying to quantify how similar related sequences are, and to gain information from these relationships. To do so, I imported the TN93 model (https://github.com/CDCgov/tn93), which is a fairly widely used measure of distance by nucleotide substitution. Finding was that even though Apta-MCTS rarely duplicates the same candidate exactly, it does frequently create candidates which differ only by a few substitutes.
   
2. Clustering by Pairwise Tamura-Nei Score:
   
3. Kill-Neighbors:
   
4. Real Data (12b):
   
5. Real Data (15b):
