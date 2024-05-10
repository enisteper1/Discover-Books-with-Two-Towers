<td>
<a target="_blank" href="https://colab.research.google.com/github/enisteper1/Personalized-Recommendation-with-Transformers/blob/main/Personalized_Recommendation_with_Transformers.ipynb">
<img src="https://www.tensorflow.org/images/colab_logo_32px.png" />Run in Google Colab</a>
</td>

# Book Recommendation System

This project aims to build a book recommendation system using various techniques, including data preprocessing, creating a book-to-book model, and evaluating recommendations. Below is a comprehensive guide to understanding and implementing the system.

## 1. Data Preprocessing
Data preprocessing is a critical step to ensure that the dataset is clean, consistent, and ready for modeling.

### 1.1 Load Libraries
Libraries such as pandas, numpy, TensorFlow, and others are loaded to facilitate data manipulation, model building, and evaluation.

### 1.2 Load Dataset
Datasets for books, ratings, and users are loaded. Key steps include:

- Loading books, ratings, and users datasets.
- Standardizing and cleaning data.
- Filtering out books with missing or corrupted information.
- Removing unnecessary columns and handling missing values.
- Standardizing user and book IDs.
### 1.3 Book to Book Matches
This step involves:

- Grouping books that are read by the same user.
- Generating pairs of books read by the same user to create a dataset for modeling.
### 1.4 Convert Dataset to TFDS
The preprocessed data is converted to TensorFlow datasets (TFDS) for easier handling and feeding into the model.

## 2. Book to Book Model
The model is designed to learn the relationships between books based on various features such as titles, authors, and publication years.

### 2.1 Book Title Model
A DistilBERT model is used to generate embeddings for book titles. These embeddings capture the semantic meaning of the titles.

### 2.2 Book ISBN, Author, Publisher Models
Separate models are created for:

- Book ISBNs
- Authors
- Publishers
- Publication years
These models convert categorical features into dense embeddings.

### 2.3 Book Model
A comprehensive book model is created by concatenating the embeddings from the ISBN, title, author, publisher, and publication year models.

### 2.4 Book to Book Model
This model utilizes the book embeddings to learn similarities between books. The model is trained using TensorFlow Recommenders (TFRS).

### 2.5 Training the Model
The model is compiled and trained using the book to book match data.

### 2.6 Embedding Extraction
After training, embeddings for all books are extracted. These embeddings are used for finding similar books.

### 2.7 ANN
An Approximate Nearest Neighbors (ANN) algorithm (hnswlib) is used to quickly find similar books based on their embeddings.

### 2.8 Similar Book Search
A function is provided to search for similar books using the trained embeddings and ANN.

## 3. Recommendations & Evaluation
This section covers the evaluation of the recommendation system.

### 3.1 Highly Rated Popular Books
The most popular books are identified based on the number of ratings and their average ratings.

### 3.2 Similar Books
The performance of the recommendation system is evaluated by comparing the recommended books to actual user behavior.

### 3.3 NDCG Scores
Normalized Discounted Cumulative Gain (NDCG) scores are calculated to measure the effectiveness of the recommendations at different cut-off levels.

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
