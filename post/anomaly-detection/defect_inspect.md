## An Unsupervised-Learning-Based Approach for Automated Defect Inspection on Textured Surfaces
阅读笔记 by **luo13**  
2020-4-5  

这篇文章关于实验细节方面并不是写得很详细，也没有公开代码，但是他的思想非常适合做工业生产中的缺陷检测问题。  
工业生产的权限检测问题主要问题是，缺陷样本很稀少，并且缺陷的种类非常多，不能很明确对每一种缺陷都进行分类。且标注成本也是一个需要考虑的因素。  
这篇文章提供了一种无监督的方式进行缺陷检测，且只使用了无缺陷的样本。看文章给出的结果还算可以。  

![结构图](../../img/defect_inspect/结构图.png)   
这篇文章采用autoencoder的方法，对原图进行重构，训练时只使用无缺陷的样本，让网络学习到无缺陷样本的特征，当输入图片存在缺陷时，网络对缺陷的响应应该与正常部分有所不同，根据这一特征实现了缺陷的定位。  
文章提到，如果在输入图片中加入一定的椒盐噪声，会对模型效果有所提升。采用特征金字塔结构是为了适应不同大小的缺陷。  

![效果图](../../img/defect_inspect/效果图.png)   

![loss](../../img/defect_inspect/loss.png)   
loss的原则是与输入图片要尽可能相似
