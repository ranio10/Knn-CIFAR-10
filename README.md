# Knn-CIFAR-10

1. Accuracy Analysis
The experimental results show that the L1 distance metric consistently outperforms the L2 distance metric across all tested values of K.
The best performance was achieved with K = 5 using L1 distance, yielding an accuracy of 31.0%.
When analyzing the effect of K, smaller values such as K = 1 and K = 3 tend to be more sensitive to noise, resulting in lower accuracy. On the other hand, larger values such as K = 9 lead to a smoother decision boundary, which may cause a loss of important local structure and slightly reduced performance.
Therefore, the results indicate that selecting an appropriate K value is crucial, with K = 5 providing the best balance between noise sensitivity and generalization in this experiment.

2. Confusion Matrix Analysis
The confusion matrix reveals clear patterns of misclassification between visually similar classes.
Classes with more distinctive shapes and backgrounds, such as airplane and ship, achieve relatively high classification accuracy. For example, the model correctly classified a large number of ship images.
In contrast, significant confusion occurs among classes with similar visual characteristics. For instance, frequent misclassifications are observed between cat, dog, and deer, as well as between frog and bird, and automobile and truck.
These results suggest that the model struggles to distinguish between categories that share similar low-level visual features.

3. Reasons for Low Accuracy
Although an accuracy of approximately 31% may seem low, this result is expected given the nature of the task.
CIFAR-10 images contain complex visual patterns, and representing them solely with raw pixel values is insufficient to capture meaningful semantic information. Since KNN relies purely on distance comparisons in the raw pixel space, it does not consider spatial relationships or higher-level features within the image.
As a result, its performance is inherently limited for complex image classification tasks.

4. Limitations of KNN for Image Classification
There are several fundamental limitations of KNN when applied to image data:
High computational cost:
KNN requires computing distances between each test sample and all training samples during prediction. This leads to significant computational overhead, especially as the dataset size increases.
Curse of dimensionality:
Each CIFAR-10 image is represented as a 3072-dimensional vector. In such high-dimensional spaces, distance metrics become less meaningful, which negatively impacts classification performance.
Lack of spatial awareness:
KNN treats images as flat vectors and ignores spatial structure. It cannot capture important patterns such as edges, shapes, or object arrangements within the image.

5. Conclusion
In conclusion, while KNN is a simple and intuitive algorithm, it is not well-suited for complex image classification tasks. Compared to more advanced models such as Convolutional Neural Networks (CNNs), KNN shows clear limitations in both performance and computational efficiency.
