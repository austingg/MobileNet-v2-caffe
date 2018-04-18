# MobileNet-v2-caffe
MobileNet-v2 experimental network description for caffe.

### Update
1. Google has released a series of mobilenet-v2 models. So reference pretrained model from tensorflow/model repository.
2. MobileNet-V2 has accepted by CVPR 2018. The latest ilsvrc12 top1 accuracy is **72.0%**. 
3. According to google official model, mobilenet-v2 downsampled feature map early.
4. shortcuts are placed except the first inverted residual bottleneck sequence.

### Note
There are some unclear details about the network architechture.
1. ~~bottleneck sequence 5's input size doesn't match its prior sequence's stride.~~
2. ~~how to deal with shortcuts or residual when the input channel and ouptut chanel are not the same. (Currently, we add shortcuts for all bottlenecks in the bottleneck sequence except the first one.)~~
3. The paper says there are 19 bottlenecks, while there only 17 bottlene in Table 2. 

### Suggestion
1. Strongly recommend that reimplement the paper use mxnet, pytorch, tensorflow, other than caffe, since there are optimized depthwise conv layer. 
2. Don't forget set the weight decay 4e-5. 
3. inception data augmentation helps.
