# Project 4: Billboard Hot 100 Trends and Top 20 Prediction Model
The source datasets, 'Hot 100 Audio Features' and 'Hot Stuff', come from Kaggle (https://www.kaggle.com/datasets/thedevastator/billboard-hot-100-audio-features/data). Both .csv files from this dataset can be found in the Resources folder:
* **'Hot 100 Audio Features.csv':** contains data from Spotify Web API on audio features for each song listed in the Billboard Hot 100 from the specified time frame. For more information on the audio features listed in the file, you can check https://developer.spotify.com/documentation/web-api/reference/get-audio-features
* **'Hot Stuff.csv':** contains data from the weekly Hot 100 singles chart data from the week of August 2, 1958 to the week of May 29, 2021.

**Project Dashboard**
The project's Tableau dashboard can be found at the following link: https://public.tableau.com/views/testing_17106176993650/Dashboard12?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link

**Project Description**
Using data from Billboard Hot 100 charts from the week of August 2, 1958 through the week of May 29, 2021, our goal was to analyze trends of songs that made it onto the charts and generate a model to predict whether a song would make it into the top 20 on Billboard's Hot 100. More specifically, we focused on trends among genres and of the top 20 songs vs bottom 80 songs based on the attributes with the highest correlation to whether a song ended up in the top 20.

When looking at those attributes, we then asked the following: Do genres have any correlation with song attributes? Do top 20 songs have any noticeable differences in these attributes when compared to songs in the bottom 80? Are there any obvious trends in the data overall?

*Key Insights*
* Most artists with top songs based on Danceability fall under the genres of hip hop or rap.
* Of top ten genres:
    * Pop is by far the most common genre on the chart (5552 songs), the next most popular being rock (4082 songs).
    * Rap and Hip Hop are the most explicit, most danceable, and most vocal genres on average. They also rank second and third for loudness, respectively.
    * Disco is the most positive sounding genre, and also the least explicit.
* Top 20 songs are more danceable, less intense, and sound more positive than songs that remain in the lower 80.

*The Dashboard*
The Tableau dashboard has a couple of interactive charts.
* The '# of Songs in Each Genre on the Chart Each Year' graph at the top displays trends of genres overtime on the charts. It has a slider filter for years and a dropdown to select one or more genres in case a user wants to compare specific genres or even look at one genre's trends more closely.
* In the 'Trends & Traits of Top Genres' section, there is the 'Top Ten Genres by:' chart section with a dropdown menu to select which song attribute you're looking at the trends of (Danceability, Explicitness, Loudness, Speechiness, and Valence).
* The final interactive chart is the first chart under the 'Trends of Top 20 Songs' section, accompanied by a dropdown menu that allows a user to select from another set of song attributes (Danceability, Energy, Speechiness, and Valence)

**Resources Folder**
There are five other files contained in the Resources folder:
* **'Billboard Data Table.sql':** the file exported from Postgres that holds the code used to create the SQL database used in building the model
* **cleaned_data.csv:** the file created in billboard_cleaning.ipynb that holds the completely cleaned data for trend analysis. The added 'Top 20' column contains a 1 to indicate the song made it into the top 20 at some point, or a 0 to indicate that it didn't.
* **parent_genres.csv:** the file used in billboard_cleaning.ipynb to reclassify song genres as their parent genre for the purpose of making genre analysis more concise
* **fully_cleaned_yearly.csv:** the file created in billboard_cleaning.ipynb explicitly for the purpose of creating a yearly trend chart on the tableau dashboard (used only in tableau)
* **top_20_songs.csv:** the file created in top_song_analysis.ipynb for the purpose of making visuals for the tableau dashboard (used only in tableau)

**Other Files**
* **billboard.db:** the sql database created to hold billboard data for the model
* **billboard_cleaning.ipynb:** contains all of the code for cleaning the original datasets and joining them together to create our useable .csv file for data analysis
* **genre_stats.ipynb:** contains all of the code used to analyze trends of attributes within each of the top genres
* **top_song_analysis.ipynb:** contains all of the code used to analyze trends of top 20 songs vs. bottom 80 songs
* **'Prediction Model.ipynb':** contains all of the code used to build our prediction model
