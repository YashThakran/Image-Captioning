##Code to be Updated

# Image-Captioning
Emphasized the critical role of attention mechanisms in the image captioning task, utilizing a ResNet-based encoder and a GRU-based decoder. Illustrated the paramount importance of attention in enhancing the quality and contextual relevance of generated captions by enabling the model to selectively focus on specific image regions.


The notebooks expect images to be in the data subfolder and the saved models and features to be in the same folder as the notebook.The models for encoder and decoder need to be separately saved and loaded, but the naming is consistent. 

For InceptionV3 we have models numbered 1, 3 and 7 (see number at end of model file). For these models, we need to change the batch-size, embedding dimensions and hidden units according to the tables specified at the bottom of the notebooks which describe the model parameters.

For ResNet50, we have two models, 1 and 7 which are loaded accordingly. The naming is consistent across these two to ensure we know the model parameters.

So, when running from pretrained weights, we need to ensure we uncomment the following lines and specify the models and parameters correctly:

encoder.load_weights("my_encoder1_res")
decoder.load_weights("my_decoder1_res")

Then we obviously skip the training part and get down to the evaluation part.



For Without Attention model :

1. Download the dataset :
	chmod +x download.sh
	./download.sh
	
2. Preprocessing
	python build_vocab.py   
	python resize.py

3. Train the model
	python train.py    

4. Test the model
	python sample.py --image='png/example.png'
