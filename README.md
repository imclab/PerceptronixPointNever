Perceptronix Point Never
========================

This is an implementation of an HMM part-of-speech tagger using the 
averaged perceptron algorithm, as described in Collins 2002. As in Collins'
paper, the features used are the same as those used by Ratnaparkhi (1996), except that the same features (including orthographic features) are used 
for both "rare" and "non-rare" words.

IOB NP-chunking support may be added at a later date.

Usage
-----

    PPN [-i tag] [-i|-p input] [-D|-E|-T output] [-t t] [-h] [-v]

    Input arguments (exactly one required):

        -i tag         train model on data in `tagged`
        -p source      read serialized model from `source`

    Output arguments (at least one required):

        -D sink        dump serialized training model to `sink`
        -E tagged      compute accuracy on data in `tagged`
        -T untagged    tag data in `untagged`
    
    Optional arguments:

        -t t           number of training iterations (default: 10)
        -h             print this message and quit
        -v             increase verbosity

Options `-i` and `-E` take whitespace-delimited "token/tag" pairs as input.
Option `-T` takes whitespace-delimited tokens (no tags) as input.

For anything else, UTSL...

A few Python-based scripts have been added to assist in tagging: 

* `confusion` creates a tagging confusion matrix in CSV format
* `universal` converts Penn Treebank tags to the Petrov et al. (2012) universal tagset
* `untag` removes tags from data for performing experiments

Requirements
------------

Three 3rd-party Python modules are required:

* `numpy`
* `simplejson`
* `jsonpickle`

License
-------

MIT License (BSD-like); see source.

What's with the name?
---------------------

It is an homage to experimental musician Daniel Lopatin, who performs under the name [Oneohtrix Point Never](pointnever.com).

Bugs, comments?
---------------

Contact [Kyle Gorman](mailto:gormanky@ohsu.edu).

References
----------

M. Collins. 2002. Discriminative training methods for hidden Markov models: Theory and experiments with perceptron algorithms. In _EMNLP_, 1-8.

A. Ratnaparkhi. 1996. A maximum entropy model for part-of-speech tagging. In _EMNLP_, 133-142.

S. Petrov, D. Das, and R. McDonald. 2012. A universal part-of-speech tagset. In _LREC_, 2089-2096.
