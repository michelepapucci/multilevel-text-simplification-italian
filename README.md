# Generating and Evaluating Multi-Level Text Simplification: A Case Study on Italian

The repository contains the dataset created for an in-depth linguistic analysis of automatically generated text simplification for Italian using Llama-2. 

The dataset has been created in the context of a research paper, that is currently under review, by [Michele Papucci](https://michelepapucci.github.io), [Giulia Venturi](http://www.italianlp.it/people/giulia-venturi/) and [Felice dell'Orletta](http://www.italianlp.it/people/felice-dellorletta/). 

## Dataset Format

Inside the `data/` folder of the repository (linked [here](https://github.com/michelepapucci/multilevel-text-simplification-italian/tree/master/data/)), there are two files, one for each tested domains: [PaWaC - Public Administration Web as Corpus](https://live.european-language-grid.eu/catalogue/corpus/18863) and Wikipedia. They are csv files, containing each 2000 original sentences, taken from the correspective original corpus. For each of these original sentences, multiple simplification are provided. 
Each row represent a tuple `(original, simplification)`. Relevant fields are: 
- `original_sentence_idx` which is used to identify all the simplification that are derived from the same original sentence; 
- `original_text` and `simplification` which contains the texts of the original sentence, and the generated simplification; 
- `readit_og` and `readit_simp` which represent the Read-IT Global Score (paper [here](https://aclanthology.org/W11-2308.pdf), demo [here](https://www.ilc.cnr.it/dylanlab/apps/texttools/)) of the original sentence and the generated simplification; 
- The remainder of the `*_og` and `*_simp` columns represent a linguistic feature obtained trough the use of ProfilingUD (paper [here](http://www.lrec-conf.org/proceedings/lrec2020/pdf/2020.lrec-1.883.pdf), web-based tool [here](http://linguistic-profiling.italianlp.it/)) of the original sentence and of the simplification (e.g. `char_per_tok_og` and `char_per_tok_simp` represent respectively the average number of characters per token for the original sentence and for the generated simplification). Filters that remove sparse features are applied as a part of the ProfilingUD pipeline, so the number of the feature may not be the same between the two domains; 