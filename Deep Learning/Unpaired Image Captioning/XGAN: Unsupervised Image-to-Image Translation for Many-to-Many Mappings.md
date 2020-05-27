# What
Unsupervised image translation. Sematic style transfer from real faces to cartoons with no known image pairing across domains. 

# Why
Unsupervised. 

# Related Work
* Style transfer.
* Domain adaption.
* Unsupervised Image-to-Image translation. UNIT DTN 

# Challenge
* study a semantic embedding across domains
* not in pixel level but semantic level. There might mbe significant structural change of the input.

# How
1. reconstruction loss -> encourages the model to encode enough information on each domain for to perfectly reconstruct the input.
2. Domain-adversarial loss -> encourage the embeddings learned by e1 and e2 to lie in the same subspace.
3. Semantic consistency loss -> encourages the network to preserve the learned embedding during domain translation
4. GAN objective -> generate more realistic image can fraud the discriminator.
5. Teacher loss -> encourages the learned embeddings to lie in a region of the subspace defined by the output representation of a pretrained teacher network.


# Experiment
CartoonSet and VGG-Face
Compared to DTN and CycleGAN.
Ablation study: 
XGAN with only the reconstruction and domain-adversarial losses active. Already able to capture basic semantic knowledge across domains.
teacher loss inactive experiment shows that the teach, FaceNet, is meaningful for real faces.
semantic consistency loss inactive experiment shows that semantic consistency loss will force the network preserve more semantic features across domains.

# Confused and Knowledge blind spot
* ADAM optimizer
* how teacher loss work? regularizer?
