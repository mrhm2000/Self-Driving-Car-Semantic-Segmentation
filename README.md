# Semantic Segmentation
### Goal
Project goal is to label road images using a Fully Convolutional Network based on pre-trained VGG-16 image classifier. The model will train and test using KITTI data set.

### Environment

#### GPU
The python code 'main.py' will check the GPU availability.

#### Dependency
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)


#### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.


### Implementation
Pretrained VGG-16 is converted to match data set in this case model is set to identify two classes : road and non road. The model loss is calculated using cross-entropy, and use Adam as an optimizer.


##### Run
Run the following command to run the project:
```
python main.py
```
### Result
Result of the train model images are save on images folder. Parameter adjustment and loss are recorded.

#### Parameter

Model was train on various setting. I settled with 20 epoch, batch_size = 5, dropout 0.5, learning rate = 0.0001, kernel initializer weight = 0.01 and kernel regularizer weight 1e-3.

#### Loss
I experimented with number of setting and loss average are tend to getting lower on each Epoch iterations.

No|Epoch | Loss average | Dropout | Learning Rate
---|---|---|---|---
1|20|0.033|0.5|0.00009
2|20|0.027|0.5|0.0001
3|20|0.038|0.6|0.0001
4|20|0.044|0.5|0.0002


Training loss record on row 2 setting above:

Epoch | Loss average
---|---
1|0.52895992968616812
2|0.15678886208554793
3|0.12183833970078106
4|0.094745325695337917
5|0.090101418181740001
6|0.075108099279218701
7|0.06586082992625647
8|0.06244756740614258
9|0.052465703370499203
10|0.048280684887592136
11|0.04552585021432104
12|0.042489964804001926
13|0.040817561944753958
14|0.040140913767290523
15|0.03672626222772845
16|0.033920377685592092
17|0.032669993567055668
18|0.03021795659101215
19|0.029408452486426664
20|0.027688115144726532



#### Images

![image1](/images/um_000002.png)
![image2](/images/um_000045.png)
![image3](/images/um_000066.png)
![image4](/images/uu_000038.png)
![image5](/images/uu_000055.png)
