
# ***Cassava-Leaf-Disease-Detection***

&nbsp;<img src="https://user-images.githubusercontent.com/75840165/110804699-6b38d200-82a6-11eb-85fc-dc4e48dfa249.jpg" height=250 width=350 />  &nbsp;&nbsp;<img src="https://user-images.githubusercontent.com/75840165/110804685-68d67800-82a6-11eb-854b-a6c6711a853b.jpg" height=250 width=350 /> 

## Overview:-
* As the second-largest provider of carbohydrates in Africa, cassava is a key food security crop grown by smallholder farmers because it can withstand harsh conditions.
At least 80% of household farms in Sub-Saharan Africa grow this starchy root, but viral diseases are major sources of poor yields.With the help of data science, it 
may be possible to identify common diseases so they can be treated.
* Existing methods of disease detection require farmers to solicit the help of government-funded agricultural experts to visually inspect and diagnose the plants. This 
suffers from being labor-intensive, low-supply and costly. As an added challenge, effective solutions for farmers must perform well under significant constraints, since
African farmers may only have access to mobile-quality cameras with low-bandwidth.




## Goal:- 
To classify each cassava image into five disease categories  With our help, farmers may be able to quickly 
identify diseased plants, potentially saving their crops before they inflict irreparable damage.

## Data:- 
>* This is dataset from Kaggle competition 
>* We have train set containing  more than 20k images, With train.csv file which contains id for image and labels.
>* To know more about dataset i have added [dataset_info.md](https://github.com/AdiShirsath/Cassava-Leaf-Disease-Detection/blob/main/Dataset_info.md) file.

## ***Preprocessing***:-
* Converting image pixel's from 0-255 to 0-1 using tensorflow kept size of tensor (224,224,3) 
* Created tuples of images and respective labels with batch size of 32
* Preprocessed all data and saved it

## ***Training***:-
* On Sample Dataset 10K images

| Model   |training score|Validation Score|  
|---------|--------------|----------------|   
| Own CNN |  65%         |    67%         |   
|ResNet50V2| 100%        |    70%         |   
|InceptionResNetV2| 90%  |    70%         |  

* On Full data 21k images

| Model   |training score|Validation Score|   
|---------|--------------|----------------|  
|InceptionResNetV2|  94% |    73.69%      |
|***CropNet-MobileNetV3***|88% |88% |   

* ***Best Model***:-
>* CropNet-Cassava disease classifier whose architecture is same as MobileNetV3 
>* This was already trained of Cassava leaf's for 6 classes, Link to this model is here [Tensorflow](https://www.tensorflow.org/hub/tutorials/cropnet_cassava#:~:text=This%20notebook%20shows%20how%20to,disease%2C%20healthy%2C%20or%20unknown.)
>* We had five classes so trained this model by adding own fully connected layer.  

## Building Web-App :-
* To create web app we used Flask and to create Web pages used HTML.
* To style html pages used scss file.
* Now we can input images from html using GET method.
* Preprocess image in flask app as model required. 
* And after clicking predict button which uses POST method We can predict leaf disease of Cassava leaf. 

## Results:-
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="https://user-images.githubusercontent.com/75840165/111299311-cafff600-8675-11eb-8ae4-83aa2b658dbb.png" height=210, weight=310 />  &nbsp;<img src="https://user-images.githubusercontent.com/75840165/111299323-ce937d00-8675-11eb-9d45-11926101c0e7.png" height=210, weight=310 />
<img src="https://user-images.githubusercontent.com/75840165/111299331-d05d4080-8675-11eb-9b2a-f1f090b34a2d.png" height=210, weight=310 />  <img src="https://user-images.githubusercontent.com/75840165/111299333-d18e6d80-8675-11eb-8d91-af4cb545e5c3.png" height=210, weight=310 />

