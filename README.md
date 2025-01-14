# Reduce-Foodwaste-Dataset

In a world where systematic overproduction drives both economic inefficiency and environmental degradation, the challenge of accurate demand forecasting has never been more pressing. The Green AI Hub project on foodwaste reduction, ["KI-basierte Prognosen für Lebensmittelproduktion"](https://www.green-ai-hub.de/pilotprojekte/pilotprojekt-brammibals-donuts-foodtracks) tackled one such real-world scenario: predicting pastry sales. Framed as a time-series forecasting problem, the task calls for innovative yet efficient machine learning solutions to help reduce waste while meeting customer demands.

## The Repo: Training and Test data 
In this repository, we collect anonymized excerpts of the project data for future applications and own experiments. Have a look at the notebook for a first overview of what is included. As it is accompanied by a [kaggle competition](https://www.kaggle.com/competitions/pastry-prediction), the solution file will be uploaded later. 

The data is aggregated from a German confectionery chain with several stores. It spans from August 2021 to May 2024 and contains, among the scaled total sales per store and day, information on public holidays as well as weather. For some days and stores, there is also scaled information available on unsold/ordered donuts, as opposed to actual sales. 

![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F20663420%2F010547ad79879451e0d7c61a53f9b50f%2FBildschirmfoto%202024-12-23%20um%2011.38.46.png?generation=1734950378044347&alt=media)

Pastry sales show a strong weekly seasonality with occasional outliers. 

### Files

*   **train.csv** - the training set
*   **test.csv** - the test set

### Columns

*   `date` - day of the infromation, dates can be duplicates, as there are several stores in the data
*   `store` - id of the store, String
*   `is_state_holiday` - contains information on type of day, regarding public holidays
*   `is_school_holiday` - contains information on type of day, regarding school holidays
*   `is_special_day` - contains information on type of day, regarding non-holidays (e.g., religious days that are not public holidays)
*   `temperature_max` - maximum temperature this day during opening hours
*   `temperature_min` - minimum temperature this day during opening hours
*   `temperature_mean` - mean temperature this day during opening hours
*   `sunshine_sum` - total minutes of sunshine this day during opening hours
*   `precipitation_sum` -  total mm of precipitation this day during opening hours
*   `sales` - total number of units sold, scaled for better comparison between stores - this is the **prediction target**
*   `unsold` - total number of units not sold, scaled for better comparison between stores (not available for all stores/days)
*   `ordered` - total number of units originally ordered, scaled for better comparison between stores (not available for all stores/days)

## The Problem: Pastry Planning and Overproduction
Pastry sales present a particularly intriguing forecasting challenge. Freshness is critical, and unsold items often end up as waste at the end of the day. Overproduction leads to increased costs and environmental harm, while underproduction risks lost revenue and dissatisfied customers. The stakes are high: businesses that master this balance can not only improve their profitability but also contribute to global efforts to reduce food waste.

## The Goal: Intelligent Solutions for a Complex Trade-Off
The mission is to develop models that enable better pastry production planning. By accurately predicting daily and seasonal variations in sales, bakeries can produce just the right amount. However, the solution comes with its own trade-offs. Many state-of-the-art machine learning methods require significant computational resources, raising questions about their sustainability. This competition encourages you to weigh these trade-offs and explore innovative, computationally efficient approaches to forecasting.

