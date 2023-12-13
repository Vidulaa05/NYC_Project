# NYC_Project
# NYC Taxi Fare Prediction Group Project

## 1. Dataset information

The datset contains the following fields:

* key - a unique identifier for each trip
* fare_amount - the cost of each trip in usd
* pickup_datetime - date and time when the meter was engaged
* passenger_count - the number of passengers in the vehicle (driver entered value)
* pickup_longitude - the longitude where the meter was engaged
* pickup_latitude - the latitude where the meter was engaged
* dropoff_longitude - the longitude where the meter was disengaged
* dropoff_latitude - the latitude where the meter was disengaged

## 2. Feature Engineering

There are a variety of features within the dataset and it is important to convert them into the right format such that we can analyse them easily. This would include converting datetime features and string features. As we can only feed numeric features as input to our models, our next task is to convert the features in numeric form. Feature engineering is the process of extracting information from the existing data in order to improve the performance of the model. Feature engineering is subdivided into two parts: Feature prepocessing & Feature generation

### 2.1 Feature Preprocessing

Feature preprocessing implies updating or transforming existing data.

Feature Transformation of pickup_datetime data type to datetime
By Default all datetime based columns are considered as strings in pandas. Convert string date to datetime features.

### 2.2 Feature Generation

Feature generation involves creating new features from the existing data. 
New variables can be created as follows:
* Datetime features
* Pickup hour - from pickup_datetime
* Pickup week day name
* Pickup date
* Pickup month
* Pickup day of week in numbers.

## 3. Finding the distance between pickup an dropoff point

### Haversine Distance
Haversine distance: To calculate the distance (km) between pickup and dropoff points. Difference between pickup and dropoff points will give an idea about the distances covered which should be the most predictive feature for taxi fare. The haversine formula determines the great-circle distance between two points on a sphere given their longitudes and latitudes.

The haversine formula approximates the great-circle distance between two points on a sphere given their longitudes, latitudes and the sphere’s radius. The sphere we are interested in here is the Earth – which is not a perfect sphere, but close enough for the approximations that we are interested in. Important in navigation, it is a special case of a more general formula in spherical trigonometry, the law of haversines, that relates the sides and angles of spherical triangles. Source: Haversine formula

Haversine distance can be found using geopy library, scikitleran library, or by implementing Haversine formula by defining a custom made function. All three methods are described below.


Lattitude & Longitude
Lets look at the geospatial or location features to check consistency. They should not vary much as we are only considering trips within New York city.


## 4. Model Development

The following algorithms are going to be used to build regression models:

- Linear Regressor
- Polynomial Regressor
- Ridge Regressor
- Lasso Regressor

## Conclusion
After testing with various regression models, the RMSE error on validation data is lowest for Lasso Model.

We can say that lasso model is best fit for the used dataset and number of data points.

Model can further be improvised by adding more features or using various kinds of regression model available.

As for this model we have tried best our knowledge
