# Visual-Similarity

This Project recommends 10 most similar images to a query image from within a database of images.

For this project,
I have used ResNet18 and performed Transfer Learning to suggest similar images.

Steps Involved :

1. ImageData Class
- Takes Images as Input and transforms them to (224*224) sized images[ResNet18 Input dimensions]
- Normalizes tranformed images with mean=[0.485, 0.456, 0.406],std=[0.229, 0.224, 0.225] across three channels RGB.
- Transforms the normalized images into Tensors
- Repeat This for every image in the dataset.

2. Tensor2vec

- Has following Parameters
-- model :  Model used in this project ie ResNet18
-- number_of_features : Features produced by our model
-- layer : Extract "avgpool" layer output which is our required features
-- features : Extracted Features
-- Similar : Similarity Matrix(cosine_similarity used to calculate similarity b/w features)
-- recommend_files : Similar Files
-- recommend_values : Similar Values

- Has Following Functions
-- extract_features : Extracts Features from avgpool layer of ResNet18.
-- all_features : Extracts Features for every image in DataBase
-- get_similarity : Generate Similarity Matrix and stores it as DataFrame
-- execute : to run the above commands and get recommendations

3. Storing Similar files and values as pickle file. Now we can recommend images on any machine(provided we have input images) without running our model.

4. Plotting our Reccomendation
- Show 10 most similar images from our DataBase

Notes : Offline model- Results are produced and stored on the system. If new values are added, we have to retrain our model.

Follow Ups :
1- Designing Front-End to display images
2- Designing Back-End to store images in database.
3- Designing Online Model capable of adding images and recommending similar images.





