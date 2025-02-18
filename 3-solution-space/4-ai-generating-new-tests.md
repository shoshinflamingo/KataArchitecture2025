# AI Generating new tests

[Data augmentation](https://en.wikipedia.org/wiki/Data_augmentation) is an AI technique used to generate new data from
existing one.
We can do the same with our questions to provide variability
and prevent the candidates from ~~overfitting~~ learning the answers by heart

We probably do not want to rely on the AI regarding architecture, but it certainly can create variations.
Traditional data augmentation typically means flipping, rotating, or cropping images.
For questions, we can:

* Change from affirmative to negative. `Select what of those are XXX` -> `Select what of those are NOT XXX`
* Add or remove options like: `All of the above` or `None of the above`
* Combine or change the order of questions.
* Add some distracting information to the question.








