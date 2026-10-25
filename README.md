
# Orange Classification Using Machine Learning and Deep Learning

## Objective
Classify orange images into four dataset labels:
blackspot, canker, fresh, and grenning.

## Models
1. SVM using CIELAB, HSV, and LBP image features.
2. MobileNetV2 using transfer learning.

## Test Results

| Model | Accuracy | Macro Precision | Macro Recall | Macro F1 |
|---|---:|---:|---:|---:|
| SVM | 98.99% | 98.91% | 98.86% | 98.86% |
| MobileNetV2 | 90.91% | 90.97% | 89.77% | 90.18% |

SVM performed best on the 99-image test set. These results need
validation on a larger independent dataset before deployment.

## Classical Machine Learning
Images are resized to 128x128. Normalized CIELAB and HSV histograms
are combined with Local Binary Patterns (LBP) texture features.
The resulting features are standardized and classified using an RBF SVM.

## Deep Learning
MobileNetV2 uses ImageNet-pretrained weights and a replacement
four-class classification layer. The best validation checkpoint is saved.

## Limitations
- The dataset and test set are relatively small.
- Results may vary with lighting, camera quality, and background.
- Production latency and robustness have not been measured.
- The supplied classes are retained as given; this is an orange
  classification project, not an avocado ripening project.

## Future Improvements
- Collect a larger independent dataset.
- Use cross-validation and hyperparameter tuning.
- Test fine-tuning and alternative lightweight CNN models.
- Measure CPU/GPU latency and memory usage.
- Test the system in production-like conditions.
