# What
Use image-caption paired instances another source-target parallel corpus in one language to generate image-caption in target language which we do not have such image-caption paired dataset.

# Why
One performance bottleneck of automatic image caption generation is the availability of large paired dataset. 

# Related Work
* MT: translate between a resource rich language and a resource-scarce language; But caption-image dataset and the parallel corpus are quite different in distribution.
* Image Caption Generation
* Unpaired Image Captioning (straight forward pipeline)

# Challenge
* image-to-pivot and pivot-to-target models are quite different in terms of vocabulary and parameter space. (Image-captions in given scene; MT is more generic)
* The errors made by the image-to-pivot captioning model gets propagated to pivot-to-target translation model

# How
image -> zh -> en(target)
first separately train; then jointly train;
By minimizing the image captioning model and NMT model's input embedding l2 distance; 
By minimizing the NMT model's output and autoencoder input embedding l2 distance;

# Experiment

# Confused and Knowledge blind spot
* Exposure bias and loss-evaluation mismatch
* as the paper mentioned "there is no parallel corpus available for the pair", how we get "ground truth"? (Fig.1.)
* Beam search
* Adam algorithm
* target-target parallel corpus? what is that?
* what is the autoencoder loss? cross-entropy for what?
