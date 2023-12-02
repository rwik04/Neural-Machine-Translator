# Neural Machine Translator

### _A pre trained neural machine translator, fine tuned to a specific dataset, to convert English Text into German Text_

We have used the Hugging Face Model called Opus MT model developed by the Language Technology Research Group at the University of Helsinki. The dataset is used from the World Machine Translation Conference held in 2016.

Link to dataset : https://huggingface.co/datasets/wmt16/viewer/de-en


## Installing Libraries

For fine tuning the model to our own dataset, we need to install a few libraries.

```sh
pip install install datasets transformers sacrebleu torch sentencepiece transformers[sentencepiece]
```
- datasets: NLP dataset access
- transformers: Pre-trained NLP models
- sacrebleu: BLEU score computation
- torch: PyTorch framework
- sentencepiece: Text tokenization

## Loading Model

Load model using the following command

```sh
model_checkpoint = "Helsinki-NLP/opus-mt-en-de"
```
