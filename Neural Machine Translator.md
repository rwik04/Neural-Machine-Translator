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
## Datasets

Dataset includes train, val and test data in the numbers of 4.55 Million, 2.17 Thousand and 3 Thousand respectively.

Format of the dataset

**'translation'**: {

**'de'**: 'Ich erkläre die am Freitag, dem 17. Dezember unterbrochene Sitzungsperiode des Europäischen Parlaments für wiederaufgenommen, wünsche Ihnen nochmals alles Gute zum Jahreswechsel und hoffe, daß Sie schöne Ferien hatten.',

**'en'**: 'I declare resumed the session of the European Parliament adjourned on Friday 17 December 1999, and I would like once again to wish you a happy new year in the hope that you enjoyed a pleasant festive period.'
    
}

## Running the model
Execute the following code to start training the model
```sh
trainer = Seq2SeqTrainer(
    model,
    args,
    train_dataset=tokenized_datasets["train"],
    eval_dataset=tokenized_datasets["validation"],
    data_collator=data_collator,
    tokenizer=tokenizer,
    compute_metrics=compute_metrics
)

trainer.train()
```