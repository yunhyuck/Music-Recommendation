# Music-Recommendation with XGBoost
> [WSDM](https://www.kaggle.com/c/kkbox-music-recommendation-challenge) - KKBox's Music Recommendation Challenge  
Primary Performance Verification Using Kaggle's Data  

## Introduction
Using Kaggle's data, complete the first implementation of the recommended system. Then, they want to recommend music through XGBoost to the users' situation.  

## Execution environment
- Window10 Home
- CPU : Intel i5-7200U
- Ram : 8GB
- GPU : None
- ANACONDA : 5.7.4

## WSDM's Data
### songs.csv
The songs. Note that data is in unicode.

* song_id
* song_length: in ms
* genre_ids: genre category. Some songs have multiple genres and they are separated by |
* artist_name
* composer
* lyricist
* language
* members.csv
* user information.

### msno
* city
* bd: age. Note: this column has outlier values, please use your judgement.
* gender
* registered_via: registration method
* registration_init_time: format %Y%m%d
* expiration_date: format %Y%m%d

### train.csv
* msno: user id
* song_id: song id
* source_system_tab: the name of the tab where the event was triggered. System tabs are used to categorize KKBOX mobile apps functions. For example, tab my library contains functions to manipulate the local storage, and tab search contains functions relating to search.
* source_screen_name: name of the layout a user sees.
* source_type: an entry point a user first plays music on mobile apps. An entry point could be album, online-playlist, song .. etc.
* target: this is the target variable. target=1 means there are recurring listening event(s) triggered within a month after the user’s very first observable listening event, target=0 otherwise .

## Flow Chart
* Flow Chart
<p align="center"> 
<img src="https://github.com/yunhyuck/Music-Recommendation/blob/master/Picture/flow%20chart.png">
</p>
  
* Update Flow Chart(2019-07-03)
<p align="center"> 
<img src="https://github.com/yunhyuck/Music-Recommendation/blob/master/Picture/flow%20chart%20update.png">
</p>

## The Order Data Schema
* __사용자 상황 정보(User_Situation)__  
USERID , DAY , EVENT , LOCATION , WEATHER , TIME (_MUSIC_)
  
* __음악정보 DB(Melon_Top100_DB)__  
FILENAME , ALBUM , ARTIST , GENRE , TITLE , YEAR , TAG
  
* __사용자 정보(User)__  
USERID , AGE , SEX , SINGERS , GENRES , TAGS

* __상황별 들었 던, 음악 리스트(User_Situation_Music)__  
USERID , TIME , MUSIC

