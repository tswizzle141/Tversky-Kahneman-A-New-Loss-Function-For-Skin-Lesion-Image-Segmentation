# Tversky-Kahneman-A-New-Loss-Function-For-Skin-Lesion-Image-Segmentation
#### (Specially thanks to @minhnhattrinh312 for the code)
## Our tasks
Skin lesion segmentation on the ISIC 2017 and ISIC 2018.
## Our contributions
![Proposed Model](https://github.com/tswizzle141/Tversky-Kahneman-A-New-Loss-Function-For-Skin-Lesion-Image-Segmentation/blob/main/1.jpg)
* We customize an U-Net model; that we utilize the Attention-Up-and-Concate modules and the Residual skip connections instead of traditional skip connections of U-Net. We also adopt the Mean-Variance Normalization instead of using Batch Normalization. While BatchNorm could calculate windowed statistics and switch between accumulating or using fixed statistics, MVN basically centers and standardizes a batch at a time. However, MVN is utilized since it is a primary but advantageous procedure that substantially strengthen the network learning ability.
* We create a novel loss function for skin segmentation, called the Tversky-Kahneman loss function. 
