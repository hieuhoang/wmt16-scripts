This directory contains some sample files and configuration scripts for training a neural MT model with multiple input featues.
It documents the method described in:

Rico Sennrich, Barry Haddow, (2016):
    Linguistic Input Features Improve Neural Machine Translation. Proceedings of WMT16.


INSTRUCTIONS
------------

all scripts contain variables that you will need to set to run the scripts.
For processing the sample data, only paths to different toolkits need to be set.
For processing new data, more changes will be necessary.

As a first step, preprocess the training data:

  ./preprocess.sh

Then, start training: on normal-size data sets, this will take about 1-2 weeks to converge.
Models are saved regularly, and you may want to interrupt this process without waiting for it to finish.

  ./train.sh

Given a model, preprocessed text can be translated thusly:

  ./translate.sh

Finally, you may want to post-process the translation output, namely merge BPE segments,
detruecase and detokenize:

  ./postprocess-test.sh < data/newstest2013.output > data/newstest2013.postprocessed