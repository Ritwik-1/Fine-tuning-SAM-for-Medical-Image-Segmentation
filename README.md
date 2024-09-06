# Fine-Tuning SAM for Medical Image Segmentation

## Topic
This project focuses on fine-tuning the Segment Anything Model (SAM) for medical image segmentation, specifically targeting adrenal glands in axial abdominal computed tomography (CT) images.

## Dataset
The dataset used is the [MICCAI Flare 2022](https://flare22.grand-challenge.org/). For this project, only the Left and Right Adrenal gland annotations were utilized, and around 800 images of adrenal slices were selected.

## Preprocessing
- **Windowing:** Applied windowing to the mediastinal window to enhance the contrast of the adrenal glands.
- **Normalization:** Images were normalized to standardize pixel intensity values.
- **Resampling:** Resampled images to a (512,512) resolution to ensure uniformity across the dataset.

## About SAM
The Segment Anything Model (SAM) is a vision transformer model developed by META for natural image segmentation. It features an encoder-decoder architecture and leverages various prompts to perform segmentation tasks effectively. SAM is designed to handle a wide range of segmentation challenges by utilizing its advanced vision transformer capabilities.

It consists of three modules:-
- Image encoder
- Prompt encoder (point or box prompt)
- Mask decoder

## Approach
Given the large number of parameters in SAM, I adopted the following approach:
- **Frozen Layers:** Unfreezed only the mask decoder while keeping other layers frozen to efficiently fine-tune the model.
- **Loss Function:** Used the Dice Cross Entropy (DiceCE) loss function to train the model.
- **Box Prompt Mode:** Employed the Box prompt mode of SAM to provide a bounding box around the left and right adrenal glands, guiding the segmentation process.

## Results
- **Vanilla SAM Performance:** The initial performance of SAM on adrenal gland segmentation was 0.06.
- **Fine-Tuned SAM Performance:** After fine-tuning, the performance improved to approximately 0.20.

## Resources
- **Google Colab:** Used the free version of Google Colab for GPU acceleration.
- **Dataset:** Utilized the open-source MICCAI FLARE dataset.

## Contact
For any questions or further information, please contact me at [ritwik21485@iiitd.ac.in].

