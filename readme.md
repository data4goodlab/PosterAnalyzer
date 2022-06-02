# How to use posters analyser
## Code Explenation

The code is separated into 5 notebooks, each has its own responsibility but is not necessarily independent. The notebooks are:
*   posters_fetcher
*   duplicate_remover
*   actor_fetcher
*   face_recognition_ethnicity
*   analysis


### Below you can see a quick explanation of each notebook, they need to be run in that order.

Posters_fetcher - Posters fetching
*   Download metadata from imdb
*   Download posters images
*   Build movie_posters dataframe
*   Save tmdb_data 

Duplicate_remover - Duplicates removal
*   Load movie_posters
*   Calculate each image hash value
*   Assign a “dup” value of True or False to each poster
*   Save to posters_with_dup dataframe

Actor_fetcher - Actors fetching
*   Load movies ids from posters_with_dup
*   Save movies and actors metadata
*   Save actors images
*   Create actors dataframe and save as actors_df

Face_recognition_ethnicity - Face & Ethnicity recognition
*   Load posters_with_dup dataframe
*   Perform posters detection and save as posters_face_encodings
*   Perform posters encoding and save as posters_face_encodings
*   Load actors_df dataframe
*   Perform actors detection & encoding and save as actors_face_encodings
*   Recognize the actors who appear in the posters and save as match_poster_actor_cast_all
*   Use fairface 4 races model to predict each actors ethnicity
*   Add ethnicity information to the posters dataframe and save as posters_new_races4_cast_all
*   Create ranking dataframe to save the information about the actors positions in the cast list, saved as ranking_posters_new_races4_cast_all

Analysis 
*   Data preperation
*   Graphs creation seperated by titles


## Demo
There is a demo you can run to test the code, we uploaded the data and the dataframes you should expect to get.

Stages of the demo:
*   In poster_fetcher notebook, use sample_aids. The demo is the default so comment those lines for a full run.
*   In duplicate_remover notebook, load posters sample zip and previous obtained dataframes.
*   In actor_fetcher notebook use previous obtained dataframes
*   In Face_recognition_ethnicity notebook, load actos zip, movies zip, posters zip, w600k_r50.onnx model and use previous obtained dataframes
*   In analysis use previous obtained dataframes
