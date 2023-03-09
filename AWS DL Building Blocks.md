
## AWS Inferentia

When some inference workloads require  an entire GPU or have low latency requirements, use a specialized and dedicated inference chip. AWS Inferentia chip is a ML inference chip designed to deliver high performance at low cost. Each AWS Inferentia chip provides hundreds of TOPS (tera operations per second).

## Amazon Elastic Inference

Allow you to attach low-cost GPU powered acceleration to Amazon EC2 and Amazon SageMaker instances to reduce the cost of running deep learning inference by up to 75 %.

Amazon Elastic Inferece accelerators are network-attached devices that work along with EC2 instances in your endpoint to accelerated your inference calls. 

![[Screenshot from 2023-03-06 13-52-53.png]]

![[Screenshot from 2023-03-06 14-08-26.png]]

![[Screenshot from 2023-03-06 14-13-53.png]]


![[Screenshot from 2023-03-06 18-02-21.png]]

> Specificity and precision are two different measures of how well a test can classify positive and negative cases1. Specificity is how well a test can avoid false positives (people who do not have the condition but test positive), while precision is how many of the positively classified cases are relevant (true positives)1. A high specificity test means that it rarely misclassifies a negative case, while a high precision test means that it rarely includes irrelevant cases in its positive classification2. For example, if we have a test that can detect cancer in 100 people, where 20 people actually have cancer and 80 do not, then:

-   If the test correctly identifies all 20 people with cancer and no one else, then it has **100% specificity** and **100% precision**.
-   If the test correctly identifies all 20 people with cancer and 10 people without cancer, then it has **87.5% specificity** and **66.7% precision**.
-   If the test correctly identifies all 20 people with cancer and 40 people without cancer, then it has **50% specificity** and **33.3% precision**.