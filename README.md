# Music Recommendations

The purpose of this project is to create a machine-learning algorithm that provides music recommendations. 

In this project we used a Spotify API to pull data, we also aquired CSVs to compile and train an algorithm to provide a song recommendations. In the file Song_Reccomendation.ipynb is the code for the recommendations. 
The folder named Cleaning-Exploration is where we explored and cleaned our data. The folder named Data houses our primary CSVs and lastly the file titled music_reccomendations_arf.ipynb provided a foundation for our algorithm to function provide recommendations. 
The Tableau dashboard is available at: https://public.tableau.com/app/profile/sarah.stegall.rodriguez/viz/shared/S43DXD5C3.

Project Components
1. Data Retrieval and Processing
The project uses the Spotify API to retrieve song information such as name, year, popularity, and audio features like valence, danceability, etc.
The data is cleaned, normalized, and standardized before being used for modeling.
2. Data Model Implementation
The core functionality of the recommendation system is implemented in Python.
The script initializes, trains, and evaluates the model for song recommendation.
The model uses data retrieved from Spotify's API through the Spotipy library.
3. Recommendation Algorithm
The recommendation algorithm calculates song similarity using cosine distance based on scaled audio features.
It identifies songs with similar characteristics to the input song and suggests them.
4. Data Model Optimization
The project documents the iterative process of model optimization and evaluation.
Changes made to the model and the resulting performance improvements are tracked and documented.
5. GitHub Documentation
The GitHub repository is organized and free of unnecessary files and folders.
An appropriate .gitignore file is in use to exclude unwanted files from version control.
6. Group Presentation
The project includes a presentation where all group members participate.
The presentation content flows smoothly, includes relevant information, and maintains audience interest.

How to Use:
Set up Spotify API credentials:

Obtain a Spotify Client ID and Client Secret.
Set them as environment variables SPOTIFY_CLIENT_ID and SPOTIFY_CLIENT_SECRET.

Run the Recommendation System:

Use the provided Python script to interact with the recommendation system.
Example usage:
python
Copy code
recommend_songs([{'name': 'Meltdown', 'year': 2023}], data_pd)

Additional Code Explanation
In addition to the initial code provided, the project incorporates further functionality for data clustering and visualization. Below is an explanation of the added code segments:

1. Clustering for genres_pd
The code begins by creating a dataframe, genres_pd_X, containing only numerical values from the genres_pd dataframe.
It then initiates a loop to evaluate different values of k (number of clusters) using the K-means algorithm. Inertia values (within-cluster sum of squares) are calculated and stored for each k.
The results are saved in a DataFrame called genres_df_elbow containing k and corresponding inertia values.
2. Clustering Pipeline for genres_pd
A pipeline is created for clustering genres_pd data using the K-means algorithm.
It involves a standard scaling step followed by K-means clustering with 7 clusters.
The clustering model is then fitted to the genres_pd_X data.
3. t-SNE Visualization for genres_pd
t-SNE (t-distributed stochastic neighbor embedding) is used for dimensionality reduction to visualize the clusters in 2D.
The tsne_pipeline is constructed with a standard scaling step followed by t-SNE with 2 components.
genre_embedding is computed by fitting and transforming the genres_pd_X data.
A DataFrame projection is created with the resulting 2D coordinates, genre labels, and cluster assignments.
The scatter plot is generated using Plotly Express, coloring points by cluster.
4. Clustering for data_pd
Similar to the clustering process for genres_pd, numerical columns from data_pd are extracted into data_pd_X.
A pipeline (data_cluster_pipeline) for clustering is established with 20 clusters using K-means.
5. Saving the Clustering Pipeline
The data_cluster_pipeline is saved using the Joblib library. This allows the model to be loaded and reused without retraining.
6. PCA Visualization for data_pd
Principal Component Analysis (PCA) is applied to reduce dimensionality for visualization of clusters in 2D.
The pca_pipeline involves standard scaling followed by PCA with 2 components.
Data is transformed and stored in data_embedding.
The resulting 2D coordinates, song titles, and cluster labels are organized in the projection DataFrame.
A scatter plot is generated using Plotly Express, with points colored by cluster.
These additional code segments enhance the project by incorporating clustering and visualization techniques to provide insights into the data's underlying structure.

Future Enhancements:
Incorporate user preferences and behavior to provide personalized recommendations.
Explore different distance metrics for improved song similarity calculation.

### Data Source

Data was aquired from Kaggle.com: [https://www.kaggle.com/code/vatsalmavani/music-recommendation-system-using-spotify-dataset](https://www.kaggle.com/code/vatsalmavani/music-recommendation-system-using-spotify-dataset).
