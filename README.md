# DA_Proj_G7
DataAnalysis Project G7

## Python version: Python3.7
    https://www.python.org/downloads/release/python-370/


## Todo list
### To check for later when we need to change data types
``` python
list_types = rating_df.dtypes.tolist()
print(list_types)

# country names are objects
# hotel id object
# reviewer,review,countries ids are int
# ratings are float, other than value rating thats an object
# date of review and trip type are objects
# starting with hotel stars until noofroofs are float
# 1/0 values are int
# gdp values are float
# destination hostedes are int, visitors are float
```

### To do later: maybe focus on some most important variables in the selected columns. 
``` python
# Print summary statistics for meanigful columns
selected_columns =["Overall_rating",
                   "Location_rating",
                   "Cleanliness_rating",
                   "Rooms_rating",
                   "Service_rating",
                   "Sleepquality_rating",
                   "Value_rating",
                   "Hotel.stars",
                   "Hotel.price",
                   "Hotel.distance",
                   "Hotel.noofrooms",
                   "Destination_country_GDP",
                   "Destination_country_pdi",
                   "Destination_country_idv",
                   "Destination_country_mas",
                   "Destination_country_uai",
                   "Destination_country_lto",
                   "Destination_country_ivr"
                   ] # [1048575 rows x 19 columns]
rating_df_stat = rating_df[selected_columns]

# Add variance and IQR to summary statistics
summary_stats = rating_df_stat.describe().transpose()
summary_stats["variance"] = np.var(rating_df_stat)
summary_stats["IQR"] = rating_df_stat.quantile(0.75) - rating_df_stat.quantile(0.25)

print(summary_stats)

```