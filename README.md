# JokeR: seqgan for Joke generation (Tensorflow)
SeqGAN implementation for generating jokes using an RNN and LSTM.

Generating jokes is a challenging and understudied task of Natural Language Processing. A computer that intends and succeeds to generate
jokes could be deemed artificially intelligent. We
present a couple of novel approaches to joke generation, such as using SeqGAN and a language model. We implement a variety of word-level
models to tackle parts of the joke-generation
problem, namely text generation and joke classification. Ideally, merging these steps will allow for a model to write joke candidates, that
are then pruned by a well-trained classifier. We
train these models from a corpus of 231,657 userwritten jokes scraped from reddit.com

## Samples
Some sample jokes that the model generated.

```
• I was in the bar, but I wasn’t the bartender.

• What do you call a bar, a bar because it was a bar

• What do you call a girlfriend? a child to the bar.

• I was in the bar and the bar says I am not a bar.
```

## Usage

To train the default model to generate lines from `sample_text.txt`, use:

```bash
>>> ./train
```

To sample from a trained model, use:

```bash
>>> ./sample <sample_len>
```

To specify your own text, use:

```bash
>>> ./train -t /path/to/your/file.txt
```

To see all the training options, use:

```bash
>>> ./train --help
```

This gives

```
usage: train.py [-h] [-t TEXT] [-l SEQ_LEN] [-b BATCH_SIZE] [-n NUM_STEPS]
                [-e NUM_EPOCHS] [-c] [-p LEARN_PHASE]

Train a SeqGAN model on some text.

optional arguments:
  -h, --help            show this help message and exit
  -t TEXT, --text TEXT  path to the text to use
  -l SEQ_LEN, --seq_len SEQ_LEN
                        the length of each training sequence
  -b BATCH_SIZE, --batch_size BATCH_SIZE
                        size of each training batch
  -n NUM_STEPS, --num_steps NUM_STEPS
                        number of steps per epoch
  -e NUM_EPOCHS, --num_epochs NUM_EPOCHS
                        number of training epochs
  -c, --only_cpu        if set, only build weights on cpu
  -p LEARN_PHASE, --learn_phase LEARN_PHASE
                        learning phase (None for synchronized)
```

## Links
 - [Course Paper](https://sanketgujar.github.io/ext/pap/pdfs/joke.pdf)
 - [Paper](https://arxiv.org/abs/1609.05473)
 - [Canonical Implementation](https://github.com/LantaoYu/SeqGAN)
 - [Another Implementation](https://github.com/ofirnachum/sequence_gan)
