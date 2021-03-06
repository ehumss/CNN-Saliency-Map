# CNNSaliencyMap
Given a pre-trained CNN, saliency map for an input image is generated corresponding to the output label of interest. The procedure followed is from the paper ["Deep Inside Convolutional Networks"](https://arxiv.org/pdf/1312.6034.pdf). 

The saliency map generation is inspired by the basics of back propagation algorithm, which states that the deltas obtained at a layer L equal the gradient of the loss incurred by the subgraph (subnet) below L with respect to the outputs at L. Thus, backpropagating till the input data layer will yield us the gradient of the loss incurred by the whole CNN with respect to the input itself, thereby providing us the importance / saliency over the input image. 

find_saliency_map.py is the main file to run, inside which all the configurable parameters can be specified. The code is pretty much self-explanatory. The Caffe Reference ImageNet pre-trained model used for the example in this repository can be downloaded at http://dl.caffe.berkeleyvision.org/bvlc_reference_caffenet.caffemodel. 

We have also found saliency maps using googleNet model. Please find the corresponding deploy file in the models folder, download the ImageNet trained GoogleNet from http://dl.caffe.berkeleyvision.org/bvlc_googlenet.caffemodel, and see the example output image in the root directory. It is interesting to see how different net architectures disentangle the information of interest. 
