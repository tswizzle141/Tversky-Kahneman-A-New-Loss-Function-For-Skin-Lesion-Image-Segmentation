# Tversky-Kahneman-A-New-Loss-Function-For-Skin-Lesion-Image-Segmentation
#### (Specially thanks to @minhnhattrinh312 for our lovely cooperation)
## Our tasks
Skin lesion segmentation on the ISIC 2017 and ISIC 2018.
## Our contributions
![Proposed Model](https://github.com/tswizzle141/Tversky-Kahneman-A-New-Loss-Function-For-Skin-Lesion-Image-Segmentation/blob/main/1.jpg)
* We customize an U-Net model; that we utilize the Attention-Up-and-Concate modules and the Residual skip connections instead of traditional skip connections of U-Net. We also adopt the Mean-Variance Normalization instead of using Batch Normalization. While BatchNorm could calculate windowed statistics and switch between accumulating or using fixed statistics, MVN basically centers and standardizes a batch at a time. However, MVN is utilized since it is a primary but advantageous procedure that substantially strengthen the network learning ability.
* We create a novel loss function for skin segmentation, called the Tversky-Kahneman loss function. 
Number of classes $c=2$. $N$ pixels for prediction and $N$ pixels for ground truth labels, $P$ and $L$ be the predicted set and the ground truth set. $p_{ic}$ and $l_{ic}$ be the element of $P$ and $L$ that $i \in \{1,2,...,N\}$ and $c \in \{0,1\}; \ p_{ic} \in [0,1]; \ l_{ic} \in \{0,1\}$.

The Tversky-Kahneman probability weighting function:
$$\omega(z)=\frac{z^{\gamma}}{[z^{\gamma}+(1-z)^{\gamma}]^{\frac{1}{\gamma}}}$$
where $z$ $\in [0,1]$; $\gamma$ $\in (0,1)$ is a parameter. 

Inspired by this kind of function, a new loss for medical image segmentation is proposed, which is also named as Tversky-Kahneman:
$$\Omega(x)=\frac{x^{\gamma}}{[x^{\gamma}+(1-x)^{\gamma}]^{\frac{1}{\gamma}}}$$
subject to 
$$x=\frac{\alpha \sum p_{i1}l_{i0} + \beta \sum p_{i0}l_{i1}}{0.5 \sum (p_{i0}l_{i0}+p_{i1}l_{i1}) + \alpha \sum p_{i1}l_{i0} + \beta \sum p_{i0}l_{i1}} \ \ \ \ \ \ \ i \in \{1,2,...,N\}$$
$\alpha + \beta$=1; $\gamma$=$\frac{4}{3}$.
## Results
![table1](https://github.com/tswizzle141/Tversky-Kahneman-A-New-Loss-Function-For-Skin-Lesion-Image-Segmentation/blob/main/2.jpg)
![table2](https://github.com/tswizzle141/Tversky-Kahneman-A-New-Loss-Function-For-Skin-Lesion-Image-Segmentation/blob/main/3.jpg)
