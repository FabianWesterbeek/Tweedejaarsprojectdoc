## Table of Contents <!-- omit from toc -->
- [```p_scopus.ipynb```](#p_scopusipynb)
- [```p_results.ipynb```](#p_resultsipynb)
- [```p_vis.ipynb```](#p_visipynb)
- [```p_eval.ipynb```](#p_evalipynb)
- [Dependencies](#dependencies)
# Documentation product notebooks <!-- omit from toc -->

The full repository contains the following notebooks:

- ```p_scopus.ipynb```: Extracts the data from Scopus API and stores it in the ```data``` folder.
- ```p_results.ipynb```: Generates the results of the classification.
- ```p_vis.ipynb```: Generates the visualizations of the embeddings.
- ```p_eval.ipynb```: Generates the evaluation of the classification.

## ```p_scopus.ipynb```
This notebook contains the code to extract the data from Scopus API. The data is stored in the ```data``` folder, using the ```scopus_*.parquet``` format. The timestamp of the data is stored in its filename.

This notebook can be used to extract all data from the API, or to update the data with only the new data:

- If the ```overwrite``` variable is set to ```False```, the notebook will only extract the data that is not already in the ```data``` folder. 
  
- If the ```overwrite``` variable is set to ```True```, the notebook will extract all data from the API and overwrite the existing data in the ```data``` folder.

After the data is extracted, ```p_results.ipynb``` can be used to generate and view the results of classification.

## ```p_results.ipynb```
```p_results.ipynb``` uses the data in the ```data``` folder to generate the results of the classification.

This notebook can be used to search with a specific query, and to view the results of the binary classification between ```novel medical technology``` or ```not novel medical technology```. 

To change the query, change the ```query``` variable in the notebook.

```search_new``` can be set to change which results are shown in the notebook:

- If ```search_new``` is set to ```True```, the notebook will show the results of the classification of the new data.

- If ```search_new``` is set to ```False```, the notebook will show the results of the classification of the entire dataset.

## ```p_vis.ipynb```
```p_vis.ipynb``` uses the data in the ```data``` folder to generate the visualizations of the embeddings. 

This notebook either generates the visualizations of the title embeddings or the abstract embeddings. The user is prompted to choose which one to generate.

After running the notebook, the visualizations can be viewed through TensorBoard:
```bash
tensorboard --logdir=logs/title-embedding/
```
or 
```bash
tensorboard --logdir=logs/abstract-embedding/
```

## ```p_eval.ipynb```
```p_eval.ipynb``` uses the data in the ```data``` folder to generate the evaluation of the classification. These results are shown through the confusion matrix and the classification report. The treshold of the classification can be changed in the notebook through the ```treshold``` variable.

## Dependencies
The dependencies required to run the notebooks are listed in ```requirements.txt```.
