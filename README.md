# Security Infrastructure - Anomaly Detection using Machine Learning

**Network Traffic Anomaly Detection System**

## Overview

This project implements a robust anomaly detection system for network traffic using machine learning techniques. The system is designed to identify abnormal traffic behaviors while minimizing false positives by accurately distinguishing between legitimate variations in normal behavior and true security anomalies.

## Problem Statement

Traditional anomaly detection methods often struggle with:
- Multiple types of normal behavior patterns
- High false positive rates
- Inability to handle complex, non-linear relationships in network data
- Limited adaptability to varying network conditions

## Solution Approach

### Method Evolution

**Initial Exploration: Chi-square Method**
- **Limitation**: Assumes single standard ideal behavior
- **Issue**: Cannot handle multiple types of normal behavior patterns
- **Result**: Unrealistic for real-world network environments

**Intermediate Approach: Bayesian Event Classification**
- **Advantages**:
  - Better aggregation of different model outputs
  - Incorporates additional information for handling dependencies
  - Models varying confidence levels (high to low)
  - Effective uncertainty modeling
- **Enhancement**: Improved anomaly detection through feature dependency modeling

**Final Implementation: Random Forest Classifier**
- **Selected for**:
  - Superior accuracy and robustness
  - Excellent handling of high-dimensional data
  - Better performance with complex, non-linear relationships
  - Optimal results for network traffic analysis

## Technical Implementation

### Dataset
- **Source**: CICIDS 2017 dataset
- **Original Features**: 77 network traffic features
- **Selected Features**: 28 critical features (via Information Gain)

### Feature Selection Process
- **Method**: Information Gain analysis
- **Reduction**: 77 → 28 features (63% reduction)
- **Impact**: Improved classifier accuracy and stability
- **Outcome**: Enhanced attack identification capabilities

### Model Architecture
- **Algorithm**: Random Forest Classifier
- **Approach**: Ensemble of multiple decision trees
- **Benefits**: 
  - Improved prediction accuracy
  - Enhanced model stability
  - Reduced overfitting risk

### Validation Strategy
- **Cross-Validation**: 5-fold and 10-fold validation
- **Data Splits**: 30-70% and 40-60% train-test splits
- **Purpose**: Ensure model robustness and reliability

## Results

### Performance Metrics

| Testing Mode | Training Accuracy | Testing Accuracy |
|--------------|------------------|------------------|
| 5-fold CV    | 99.92%          | 99.81%          |
| 10-fold CV   | 99.86%          | 99.84%          |
| 30-70% Split | 99.80%          | 99.76%          |
| 40-60% Split | 99.79%          | 99.78%          |

### Key Achievements
- **Average Training Accuracy**: 99.842%
- **Average Testing Accuracy**: 99.797%
- **Consistency**: Reliable performance across multiple validation methods
- **Robustness**: Stable results with different data split ratios

## Technical Highlights

### Feature Engineering
- Strategic feature selection significantly improved model performance
- Selected features proved crucial for accurate attack identification
- Dimensionality reduction enhanced computational efficiency

### Model Robustness
- Random Forest's ensemble approach provided excellent stability
- Cross-validation confirmed reliability across multiple test scenarios
- Consistent performance across different data distributions

### Research Foundation
- Comprehensive literature review guided implementation decisions
- Ensemble learning principles informed algorithm selection
- Network intrusion detection research shaped project direction

## Applications

### Network Security
- Real-time anomaly detection in network traffic
- Intrusion detection system enhancement
- Security monitoring and alerting

### Infrastructure Protection
- Automated threat identification
- Reduced manual security analysis workload
- Improved incident response times

## Technologies Used

- **Machine Learning**: Random Forest Classifier, Bayesian Classification
- **Feature Selection**: Information Gain analysis
- **Validation**: Cross-validation techniques
- **Dataset**: CICIDS 2017 network traffic data
- **Evaluation**: Multiple train-test split strategies

## Future Enhancements

- Integration with real-time network monitoring systems
- Expansion to additional attack types and patterns
- Implementation of adaptive learning capabilities
- Development of automated response mechanisms

## References

1. C. Kruegel, D. Mutz, W. Robertson and F. Valeur, "Bayesian event classification for intrusion detection," 19th Annual Computer Security Applications Conference, 2003. Proceedings., Las Vegas, NV, USA, 2003, pp. 14-23, doi: 10.1109/CSAC.2003.1254306.

2. Archit Sanghi, Krishna P. Kadiyala, Praveen Tammana, and Saurabh Joshi. 2021. Anomaly Detection in Data Plane Systems using Packet Execution Paths. In Proceedings of the ACM SIGCOMM 2021 Workshop on Secure Programmable network INfrastructure (SPIN '21). Association for Computing Machinery, New York, NY, USA, 9–15. https://doi.org/10.1145/3472873.3472880

3. Ayyoob Hamza, Hassan Habibi Gharakheili, Theophilus A. Benson, and Vijay Sivaraman. 2019. Detecting Volumetric Attacks on loT Devices via SDN-Based Monitoring of MUD Activity. In Proceedings of the 2019 ACM Symposium on SDN Research (SOSR '19). Association for Computing Machinery, New York, NY, USA, 36–48. https://doi.org/10.1145/3314148.3314352

---

*This project demonstrates the effective application of machine learning techniques for network security, achieving exceptional accuracy in anomaly detection while maintaining practical applicability for real-world security infrastructure.*
