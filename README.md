# mts-ml-cup
Solution of team **baseline_business** at the MTS Machine Learning Cup 2023 competition.


![image](https://user-images.githubusercontent.com/61282340/229229125-b48b3929-dd40-434d-80ea-e5545b70d1b5.png)

Public & Private scores: **1.64** (~ top **25%** of leaderboard).

Google Colab **link**: https://colab.research.google.com/drive/1V8tjtyK4yzPqxLSiTGtarh0jHPGyu6bd?usp=sharing
Kaggle **link**: https://www.kaggle.com/code/valeryberezovsky/notebookcdc69f64b3

Brief report:

The notebook with a baseline from the authors of the competition was taken as a start point (https://www.kaggle.com/code/dmitriy89/mts-ml-cup-2023-baseline/notebook). To begin with, in addition to als embeddings regarding user_id and url_host for the request_cnt sum, the same embeddings were used for the price feature. Also, in addition to the operation of the sum, aggregations were added through the mean, minimum and maximum. This helped increase the score from **1.48** to **1.54**.

Further, the following feature was used: the sum of request_cnt for all url_hots from the top_k most popular. **256**, **512**, **1024** were used as the top_k parameter, and the quality steadily increased.

Also, all categorical features (date, region_name, city_name, cpe_manufacturer_name, cpe_model_name, cpe_type_cd, cpe_model_os_type, part_of_day) have been replaced with numbers using label encoding. Then their aggregations were used using the sum, average, minimum, maximum, median, mode, std.
As a result, we managed to get a score of **1.64**. The selection of hyperparameters for the CatBoost with the help of Optuna did not give an increase in quality.
