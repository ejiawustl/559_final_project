# Style Cloaking: Protecting Human Artwork from Model Mimicry via Feature Space Obfuscation


Group Members: Eric Jia, Kyle Wolford, and Becky Shofner


For our final project, we explored a “style cloaking” approach that artists can apply to their images to combat AI models from learning or mimicking their artistic style when they make their artwork available online. This style cloak takes the form of a perturbation method that modifies images such as there are imperceptible changes in the visual space (i.e. it looks unchanged to the human eye), however, it substantially changes the location in the embedding space. We visualize this in 2 of the notebooks in our git repo (available here: https://github.com/ejiawustl/559_final_project/), and compare this to the SOTA approach, known as Glaze, which is linked here: https://arxiv.org/pdf/2302.04222 


To run everything in the right sequence, first navigate to the notebook titled: “CSE559A_Style_Cloaking - Eric.ipynb”. This notebook uses the data from “original images” in the github repo and produces the data housed in “perturbed images”. In this notebook, we cover the main processes of perturbing our images, visualizing the perturbations to see how they look visually, and then compare the differences in cosine similarity and L2-distance in the feature space using CLIP. We also examine how the number of identified key points changes before and after the perturbation. This aligns with our goals to 1) make the changes invisible to the human eye and 2) make the changes substantial in the feature space, in order to adversely affect the CLIP model’s ability to learn the style of the image. 


We then use the perturbed image results in addition to the results we obtained from perturbing some of the original images using Glaze in the subsequent notebook titled “feature_space_visualization.ipynb”. It uses both a resnet feature extractor (all layers of a pre-trained resnet except the last classification layer), and a clip feature extractor to mimic the stable diffusion feature extractor. The features are then visualized using both truncated SVD and T-SNE for dimensionality reduction. These were chosen so we could visually analyze the feature space and see how the images were being perturbed in that feature space. 

For the visualization we focus on one image, Roses by Van Gogh. This image was cloaked by GLAZE as well as Eric's notebook results, so we have 3 different versions of the image to analyze. All images were used to give more context to the feature space, but those 3 images were highlighted. The original Roses my file uses is stored in van_gogh_images, and both perturbed images are stored in perturbed_images (with an underscore).

The graphs definitely show that both GLAZE and Eric embeddings move the image's feature representation by a decent amount, and it is also interesting to see that Eric's implementation was quite similar in much less time (Glazing 1 image takes upwards of 40 minutes and 5+ GB of GPU memory). 

 There are 125 images in the dataset, many are Van Gogh, some are not. My file also has some code (commented out) relating to gathering the data, but that isn't too important.





