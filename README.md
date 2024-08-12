# Movie Recommendation System

## Overview
This project implements a content-based movie recommendation system. It suggests movies similar to the one selected by the user based on various features like genre, keywords, cast, and crew.


## Dataset
The project uses the TMDB 5000 movies and credits datasets. These datasets include information about movies such as their genres, keywords, cast, crew, and more.

- **movies.csv**: Contains movie information such as movie ID, title, genres, keywords, overview, and more.
- **credits.csv**: Contains information about the cast and crew for each movie.

## Preprocessing
### Steps Involved:
1. **Merging Datasets**: The movies and credits datasets are merged based on the movie title.
2. **Column Selection**: Only relevant columns such as `movie_id`, `title`, `genres`, `keywords`, `overview`, `cast`, and `crew` are kept.
3. **Handling Null Values**: Rows with missing data in the `overview` column are dropped.
4. **Data Transformation**:
   - Genres, keywords, cast, and crew columns are converted into lists of strings.
   - Space is removed from names to create unified tags.
   - An additional `tags` column is created by combining all these features into a single text.
5. **Text Preprocessing**:
   - The tags are lowercased.
   - Stemming is applied to normalize words to their root forms.

## Model
A **CountVectorizer** is used to convert the tags into a matrix of token counts. The cosine similarity between these vectors is then calculated to measure the similarity between movies.

### Recommendation Function
The `recommend()` function takes a movie title as input and returns a list of recommended movies based on cosine similarity.

## How to Use
### Running the Code:
1. **Load the Data**: The data is loaded and preprocessed as described above.
2. **Train the Model**: The model is trained using the preprocessed data.
3. **Generate Recommendations**:
   - Call the `recommend()` function with a movie title as input.
   - The function will print out a list of 5 recommended movies.

### Example:
```python
recommend('Spectre')
