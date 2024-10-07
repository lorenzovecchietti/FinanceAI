# DNN for Financial Markets
Implementation of the paper ["Financial Markets Prediction with Deep Learning"](https://arxiv.org/pdf/2104.05413)

## Introduction
CNNs have proven effective for automatic feature extraction in fields like computer vision and natural language processing. However, applying CNNs to financial data presents unique challenges due to the structure of such data.

Financial trading records can be organized into 2-D frames, where:
*   The x-axis represents time, containing multiple trading records.
*   The y-axis denotes different data types, such as prices, volumes, and technical indicators.

### Limitations of Convolutions


*   **2-D Convolutions**: While they can process 2-D data, convolving different types of financial data may yield nonsensical results due to the inherent differences in the data types.
*   **1-D Convolutions**: Although they can be applied across time series, they struggle with parameter sharing across different data types. This can lead to unclear boundaries and similar nonsensical outcomes as seen in 2-D convolutions.

### Architecture

Proposed Solution: Cross-Data-Type 1-D CNN (CDT 1-D CNN)
To address these challenges, a novel architecture called Cross-Data-Type 1-D CNN (CDT 1-D CNN) is proposed. This architecture organizes input data into 2-D frames but employs only 1-D convolutional kernels that scan along the x-axis (time).

## Architecture Overview
**Input Organization**: Data is structured in a way that preserves temporal relationships while allowing for distinct data types to be processed effectively.

**Convolutional Layers**: The model utilizes one-dimensional kernels that focus on temporal patterns without mixing different types of financial data.

**Max-Pooling Layers**: After each convolutional layer, a max-pooling layer reduces the x-axis dimension of the feature maps, helping to distill important features and mitigate overfitting.

This approach aims to leverage the strengths of CNNs while addressing the specific needs of financial data analysis, potentially improving prediction accuracy in financial markets.

![image](https://github.com/user-attachments/assets/0e33e56d-62e5-4756-a915-5c66046a75c4)

The CDT 1-D CNN model presents several advantages for extracting profitable patterns in financial trading compared to traditional technical analysis. Here are the key arguments supporting its superiority:
   
* **Nonlinear Representation**: The CDT 1-D CNN model operates as a nonlinear variant of technical analysis. Traditional technical indicators rely on predefined mathematical formulas based on historical price and volume data. In contrast, the convolutional and fully connected layers of the CDT model can approximate these indicators without being limited by fixed coefficients.
* **Autonomous Training**: Unlike traditional methods where coefficients (like $\alpha$, $n$, $a$, and $b$) are set by users and remain static, the CDT model employs deep learning techniques that allow for the training of parameters through algorithms such as backpropagation. This flexibility enables the model to learn from the joint distribution of training data rather than relying solely on user experience.
* **Dynamic Coefficient Adjustment**: The inability of traditional indicators to adjust their coefficients during training can lead to biases and overfitting. The CDT 1-D CNN’s ability to train its parameters dynamically allows it to adapt to changing market conditions, thereby potentially enhancing prediction accuracy and profitability.

In summary, the CDT 1-D CNN model's capacity for nonlinear representation, autonomous training, and dynamic coefficient adjustment positions it as a more effective tool for pattern extraction in financial trading compared to conventional technical analysis methods.
