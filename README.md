WORD2VEC AND TSNE
====

Word2Vec is cool. So is tsne. But training a model and reducing the vector space can be intimidating – I found that to be the case, so here are some Python scripts meant to document how to do this and make it easier for you to use Word2Vec and tsne in your projects.

##CONTENTS  
This repo includes:

* lib/: where you need to put modules like `rasterfairy` that you can't install  
* ModelsAndData/: where the `50kCommonWords.txt` file is, and where model files will write to  
* SampleOutput/: the Wikipedia dump, including parts-of-speech, trained and reduced to 2D vector space  
* TagTextForTraining.py: splits a text into words, then gets their part-of-speech  
* TrainModel.py: first script to run, which trains a Word2Vec model on an input text file  
* TsneToGrid.py: a final optional step, uses the `rasterfairy` module to convert the tsne vector space into an even grid  
* TwoStageReduce.py: second step, takes a Word2Vec model and reduces its vector space  
* VisualizeVectorSpace/: a Processing sketch for visualizing your flattened vector space  

##REQUIRED LIBRARIES  
To use this code, you'll need to install some pretty hefty libraries:

* gensim  
* sklearn  
* rasterfairy  
* numpy  
* Optional: [Wikipedia Extractor](http://medialab.di.unipi.it/wiki/Wikipedia_Extractor) to strip Wiki tags (if you're using a Wikipedia dump as your data source)  

##TO USE  
More detailed tutorial coming soon-ish, but in the meantime:

1. Install the required libraries listed above and download a data set to train on  
2. Get an input text file to train on, such as a novel (a good place to start) or something larger like a Wikipedia data dump  
3. Run `TrainModel.py` on your text file, which outputs a `.model` file  
4. Run `TwoStageReduce.py` on your `.model` file, which outputs several csv files containing your reduced model (an initial reduction run, the final run, and the final run with vectors normalized -1 to 1)  
5. Optionally, run `TsneToGrid.py` to convert your csv file to an even grid  

