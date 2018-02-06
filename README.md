# MobileNet-v2-caffe
MobileNet-v2 experimental network description for caffe.

### Note
There are some unclear details about the network architechture.
1. bottleneck sequence 5's input size doesn't match its prior sequence's stride.
2. how to deal with shortcuts or residual when the input channel and ouptut chanel are not the same. (Currently, we add shortcuts for all bottlenecks in the bottleneck sequence except the first one.)
3. The paper says there are 19 bottlenecks, while there only 17 bottlene in Table 2. 

### Suggestion
1. Strongly recommend that reimplement the paper use mxnet, pytorch, tensorflow, other than caffe, since there are optimized depthwise conv layer. 
2. Don't forget set the weight decay 4e-5. 
3. inception data augmentation helps.
