# GAN-s-GENAI
Introduction
Generative Adversarial Networks (GANs) are a class of neural networks capable of generating new, realistic data by learning from existing data. A GAN consists of two models: a generator that creates new data, and a discriminator that evaluates the data. Together, they form a feedback loop that results in highly realistic outputs such as images, text, or sound.

Experiment Summary
For this project, I used BigGAN, a large-scale pretrained GAN model, to generate realistic dog images. BigGAN takes a 128-dimensional noise vector and a class label as input and produces a synthetic image corresponding to that label. I used the pytorch-pretrained-biggan library to access the model and generate images for ImageNet class 207 (Golden Retriever).

In the code, I created 4 different noise vectors using truncated_noise_sample(), which produces normalized random inputs. Each vector was passed through the model along with the class label, and the resulting output was displayed using matplotlib.

Observations
Each image had a unique look even though the class (dog) remained constant.

Some dogs appeared sitting, while others were in action or had different facial expressions.

The background and fur color varied significantly by proving the model learned many internal features.

A few images had minor artifacts, like unusual edges or blurred textures, which is typical in GAN-generated content.

When the noise vector changed, the visual characteristics changed as well as confirming the impact of the latent space.

Reflection
This project deepened my understanding of how GANs create images from noise and how latent vectors influence image diversity. I learned how class conditioning and truncation affect output quality. A major takeaway is that GANs are not just random generators — they produce structured outputs from high-dimensional noise.

Challenges:
The original template was broken because it used from transformers import BigGAN, which does not work.

The model actually comes from a separate library (pytorch-pretrained-biggan), which needed to be installed and imported properly.

Also, class conditioning (class_vector) was completely missing in the template, which is mandatory in BigGAN.

Improvements:
Including more user control for choosing class labels and truncation levels.

Saving generated images to disk for easier sharing.

Optionally, interpolating between latent vectors to see smooth transitions in image space.

Included:
4 generated dog images using different noise vectors.

Full working code (see attached notebook/script).

Insights on latent space and model behavior.
