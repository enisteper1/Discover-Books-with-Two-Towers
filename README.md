<td>
<a target="_blank" href="https://colab.research.google.com/github/enisteper1/Personalized-Recommendation-with-Transformers/blob/main/Personalized_Recommendation_with_Transformers.ipynb">
<img src="https://www.tensorflow.org/images/colab_logo_32px.png" />Run in Google Colab</a>
</td>

# Book Recommendation System

This project aims to build a book recommendation system using with following steps; data preprocessing, creating a book-to-book model, and evaluating recommendations. Below is a basic guide to understanding and implementing the system.

## 1. Data Preprocessing
At first,libraries are initalized, dataset is loaded and data is preprocessed. In order to train two tower architecture book pairs which are read from same user are selected. 

## 2. Book to Book Model
After data preprocessing sub-models are defined for id based features like ISBN, Author, Publisher. With addition of the text embedding of book titles and publication years Book to Book recommendation model is defined. 

<h3 align=left> Two Tower Architecture </h3>
<img src="https://github.com/enisteper1/Discover-Books-with-Two-Towers/assets/45767042/4b781add-f9e7-41f2-b703-9b039b43fa27" width="60%" height="60%">

## 3. Recommendations & Evaluation
In this section  recommendations are generated and performance of the model is evaluated using NDCG metric. From the results, it can be seen that our approach is approximately 10 times better tham recommending popular items.
<img src="https://github.com/enisteper1/Discover-Books-with-Two-Towers/assets/45767042/e6feac6d-8140-41ae-82d9-e45df4b004ff" width="60%" height="60%">


<h3 align=left> An Example of Book to Book Recommendation </h3>
<h4 align=left> Main Book </h3>
<img src="https://github.com/enisteper1/Discover-Books-with-Two-Towers/assets/45767042/fefccf74-3c00-46fc-b303-04b40998a533" width="20%" height="20%">

<h4 align=left> Two Tower Model Recommendations </h3>
<img src="https://github.com/enisteper1/Discover-Books-with-Two-Towers/assets/45767042/3f977863-1487-41eb-97a8-218e7beedfa1">


<h4 align=left> Popular Book Recommendations </h3>
<img src="https://github.com/enisteper1/Discover-Books-with-Two-Towers/assets/45767042/284bbf6a-41cb-496b-979a-74e510b66d0b">

## References
- https://www.tensorflow.org/recommenders/examples/basic_retrieval
- https://www.tensorflow.org/recommenders/examples/featurization
