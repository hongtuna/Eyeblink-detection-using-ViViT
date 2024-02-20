# Robust Eye Blink Detection Using Dual Embedding Video Vision Transformer

This repository contains the official implementation of the WACV 2024 paper "Robust Eye Blink Detection Using Dual Embedding Video Vision Transformer".

### [Paper📝](https://openaccess.thecvf.com/content/WACV2024/html/Hong_Robust_Eye_Blink_Detection_Using_Dual_Embedding_Video_Vision_Transformer_WACV_2024_paper.html) • [Video 🎥](https://youtu.be/i2CWdyRcgWQ?feature=shared) • [Poster📂]() ###

## About
Capturing eye blinks from different camera angles poses significant challenges, primarily because the eye region is relatively small and eye blinks occur rapidly, necessitating a robust detection algorithm. To address these challenges, we introduce Dual Embedding Video Vision Transformer (DE- ViViT), a novel approach for eye blink detection. We modified the existing tubelet embedding for our task and added a new residual embedding. Both were designed to capture the key movements and slight changes in the frame over time. In addition, we created a new dataset and used it with existing public datasets to evaluate the robustness of the proposed method from different aspects. We rigorously evaluate our proposed method using HUST-LEBW, a publicly available dataset, as well as our newly collected multi-angle eye blink dataset (MAEB).

## DE-ViViT
### Model Architecture
This code is inspired by [ViViT](https://keras.io/examples/vision/vivit/). 

![model_architecture](https://github.com/hongtuna/Eyeblink-detection-using-ViViT/assets/33884976/03777632-6036-4881-97ef-bf0d69f8f324)


### Data Preparation
[HUST-LEWB](https://thorhu.github.io/Eyeblink-in-the-wild/) dataset serves as the primary resource for both training and evaluation of our proposed model.


### Training 
Models including baselines were trained using the HUST-LEBW training dataset with random horizontal flip as data augmentation. The hyperparameters for each model were kept identical across all experimental conditions as follows: Image shape is 24×24×1, frame number per sequence is 10, batch size is 32, learning rate is 0.0001, epoch is 100. The final model was chosen based on the validation accuracy during the training process.


### Evaluation
To observe the performance of the proposed and baseline eye blink detection method, three evaluation metrics were used: Precision, Recall, and F1 score. These evaluation metrics are commonly used in existing eye blink detection studies, as corroborated by several prior works. 


## MAEB
Our custom-collected dataset, MAEB, was specifically designed to investigate the blink detection performance of our model under varying camera angles; this was achieved through controlled experiments con- ducted in-house.

![setting](https://github.com/hongtuna/Eyeblink-detection-using-ViViT/assets/33884976/3e8a7268-de6d-4084-9fd6-9e7ac1b68cbe)

To compile the MAEB dataset, we recruited 20 participants (6 females and 14 males), maintaining an even spectacle-wearing distribution. Nine cameras simultaneously captured the facial expressions of the participants from different angles during the video viewing task. We ensured an equal number of blink and non-blink sequences, using a total of 1,440 sequences to evaluate the model’s performance.

## Contact 
Please let me know if you have any questions: jeongminhong@hanyang.ac.kr

## Citation
```
@inproceedings{hong2024robust,
  title={Robust Eye Blink Detection Using Dual Embedding Video Vision Transformer},
  author={Hong, Jeongmin and Shin, Joseph and Choi, Juhee and Ko, Minsam},
  booktitle={Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision},
  pages={6374--6384},
  year={2024}
}
```

