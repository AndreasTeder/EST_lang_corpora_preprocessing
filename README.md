# EST_lang_corpora_preprocessing
## Introduction
This is the repository for the Bachelor's degree project of preprocessing Estonian speech corpora. In specific, the work focuses on removing leading and trailing silences and trimming of long pauses in the middle. The effect of the silence removal was later graded on speech synthesis models.  
  
2 methods were created for this purpose, which can be found in the Jupyter Notebook [SilenceRemovalMethods.ipynb](SilenceRemovalMethods.ipynb). One of the created methods uses RMSE and ZCR based features to spot and remove silences. The other method uses an acoustic model based text alligner - [Autosegmenteerija 2.0](https://bark.phon.ioc.ee/autosegment2/) - the work of Tanel Alumäe, Ottokar Tilk and Asadullah. In order to use the Autosegmenteerija to create the needed TextGrids for silence removal, the Jupyter Notebook [AutosegmentedTextGridCreator.ipynb](AutosegmentedTextGridCreator.ipynb) was created. The notebook does not come with Autosegmenteerija itself, so having it be running somewhere is a prerequisite.  
  
Both the results for the preprocessing methods and for the models can be seen in [Grading.xlsx](Grading.xlsx)
## Requirements for running the Notebooks
### SilenceRemovalMethods
* Python >= 3.7.9
* Librosa >= 0.8.0
* Jupyter >= 1.0.0
* Pandas >= 1.1.4
* Numpy >= 1.19.2
* Scipy >= 1.6.0
* Matplotlib >= 3.3.2
* EstNLTK >= 1.6.7beta (for transcript preprocessing, along with the [preprocessor](https://github.com/TartuNLP/tts_preprocess_et) itself)
* [textgrid](https://github.com/kylebgorman/textgrid) 
### AutosegmentedTextGridCreator
* Python >= 3.6
* Pandas >= 1.1.3
* Jupyter >= 1.0.0
## Models
3 models were created for the purpose of this work using [the Deep Voice 3 adaptation for Estonian](https://github.com/TartuNLP/deepvoice3_pytorch). For instructions on how to use the models, please refer to the previous link.  
The models can be downloaded from here:
* [RMSE + ZCR model](https://drive.google.com/file/d/1w12Aof799pMBMuvNBFFIV02WkvJjVWxN/view?usp=sharing)
* [Autosegment with text preprocessing model](https://drive.google.com/file/d/1rEJRWDKqCtKIOosD5he4clmBjIfeeAuC/view?usp=sharing)
* [Autosegment without text preprocessing model](https://drive.google.com/file/d/13F77LM64kfe3gKazMerYBMOzTV_QnowX/view?usp=sharing)
## Example soundfiles
Sadly Github does not allow embedded audio in a readme, so to listen to the audio files, please download the [zip](ExampleAudioFiles.zip) of the audio files  
Alternatively, each audio file can be downloaded seperately from the audio example [folder](ExampleAudioFiles)  
The zip/folder contains both preprocessed and synthesized audio examples, along with the original (not preprocessed) audio files
