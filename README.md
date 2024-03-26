# Benchmarking Various ML Models for Deep Fake Detection

## Background
A "Deep Fake" refers to an image where an AI algorithm has changed someone's face to resemble a different real or fake person. As AI has become more readily accessible, determining the validity of images is critical for the protection of individuals and to safeguard against misinformation. This project aims to explore a variety of machine-learning models to identify these illegitimate images.

## Dataset
We use a Kaggle Dataset that contains 190,000 256x256 color images of human faces. Half are legitimate photos, the other half are AI-generated deep-fakes. These images are 256x256 and in color. The dataset can be found at this link: [Deepfake and Real Images Dataset](https://www.kaggle.com/datasets/manjilkarki/deepfake-and-real-images/data)

## Models Tested
- Convolutional Neural Network (CNN)
- SVM Polynomial Kernel
- SVM RBF Kernel
- Random Forest Classifier
- Basic Decision Tree
- Logistic Classifier

## Analysis
The Convolutional Neural Network (CNN) was by far the best model for this image classification task, reaching up to 90% accuracy. Even with aggressive data augmentation and regularization, our CNN model suffers from distinct overfitting. One of the biggest challenges with image augmentation for a task like this is that we are trying to detect AI manipulation. Too much image distortion may inadvertently cause false positives. With advanced enough optimizations, a CNN could likely reach over 95% accuracy.

SVMs were the next best-performing model at 71% accuracy. This is not terrible, but more advanced ensemble methods such as HOG extraction would likely be needed to score higher. Neither Kernel method showed a clear advantage.

Logistic classification is not far behind at 70% accuracy. While the accuracy is notably lower than our CNN model, it is significantly more computationally efficient. For full classification reports, please view the project file.

