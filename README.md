# Text2Image
* Goal : In terms of specific text description to generate corresponding images.
* TensorFlow implement for [Kaggles Contest - Reverse Image Caption](https://www.kaggle.com/c/datalabcup-reverse-image-caption-ver2/leaderboard)
* Technique: Using `GAN-CLS` algorithm from the paper [Generative Adversarial Text-to-Image Synthesis](http://arxiv.org/abs/1605.05396) and `stackGAN++` model from [StackGAN++: Realistic Image Synthesis with Stacked Generative Adversarial Networks](https://arxiv.org/abs/1710.10916)

## Download Data and Pre-trained Model  
* Download image files, captions, and pre-trained model from [Google Drive](https://drive.google.com/open?id=18MUiMDk4Udp4D8euOVVFS2ZCXlqPFsQ8). Image and captions file put into `./text-to-image` directory. Moreover, the pre-trained model put into `./checkpoint` directory.


## Inference Result 
* the flower shown has yellow anther red pistil and bright red petals.
* this flower has petals that are yellow, white and purple and has dark lines
* the petals on this flower are white with a yellow center
* this flower has a lot of small round pink petals.
* this flower is orange in color, and has petals that are ruffled and rounded.
* the flower has yellow petals and the center of it is brown
* this flower has petals that are blue and white.
* these white flowers have petals that start off white in color and end in a white towards the tips.  

### Result after 200 epochs
<img src="train_samples/train_200.png"/>

### Result after 800 epochs
<img src="train_samples/train_800.png"/>

## Some thoughts
* Use stackGAN can get better result, despite the improved-wgan with skip-thought also can produce satisfying one. 
* Get more captions per images, that is, randomly choose 3~5 captions for each picture (if we choose all captions, the training set is so   large that it takes long time to train).
* Add ***wrong image with false label*** to train with Discriminator:
  That is, give a caption and a random image from dataset, and give it false label.
  (To let D learn whether the image has relation with the caption.)
* The result of random distortion(e.g. brightness and different angles) to images is not good as I think. 

## Reference
 * StackGAN++ PyTorch [paper](https://arxiv.org/abs/1710.10916) [code](https://github.com/hanzhanggit/StackGAN-v2)
 * [Generative Adversarial Text to Image Synthesis](https://github.com/zsdonghao/text-to-image)
