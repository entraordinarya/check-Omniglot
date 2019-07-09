# -
手写字符识别
离线手写体字符识别是非常困难的。目前，手写体的字符识别主要分为在线文字识别和离线字符识别两种。但在线文字识别含有笔顺特征和笔顺之间时间间隔特征。而离线文字识别却不含有时间关系，因此给识别带来难度。本文针对Omniglot离线手写体小样本数据集，分别提出了进化投影描述子与极坐标统计特征，对该小样本数据集进行了分类识别。进化的投影描述子具有强的旋转不变性，而投影特征描述了文字的笔画细节，所以该模型具有非常好的鲁棒性。
首先解决了手写体样本大小、外边框不均的问题。因为样本是手写体，形态大小不均，位置也具有不确定性。但手写体对应的标准字体总可以被正方形边框所包裹，因此我们首先对样本集中的每一张图片进行白边的切割并进行了双三次线性插值对图像的大小进行了归一化，这使得缩放后的图像具有更平滑的图像边缘，最大限度上的减少了图像的失真。在提取特征方面我们进行了大量的创新，不仅提出了进化投影特征的字符描述算法，而且提出了一种具有旋转不变形的极坐标统计特征。
在训练方面，我们采用了二级分类的方法。即字符类别和字符分别训练的方式，得到了语言分类器和20类独立的字符分类器，其中语言分类器可以识别字符所在的语言种类，而字符分类器可以进行字符识别。
最后我们将程序封装为app.exe(在字符识别文件夹)，请在数据集目录下测试(因本程序为python封装，初始化时需等待10秒左右)。
