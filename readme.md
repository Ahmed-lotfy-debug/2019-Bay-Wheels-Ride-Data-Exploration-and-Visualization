# (2019 Bay Wheels Ride Data Exploration and Visualization)
## by (Ahmed lotfy)


## Dataset

> [Bay Wheels]( https://en.wikipedia.org/wiki/Bay_Wheels) (previously known as Ford GoBike) s a regional public bicycle sharing system in California's San Francisco Bay Area. It is operated by Motivate in a partnership with the Metropolitan Transportation Commission and the Bay Area Air Quality Management District.[3] Bay Wheels is 'the first regional and large-scale bicycle sharing system deployed in California and on the West Coast of the United States. It was established as Bay Area Bike Share in August 2013. As of January 2018, the Bay Wheels system had over 2,600 bicycles in 262 stations across San Francisco, East Bay and San Jose.

In June 2017 the system was officially re-launched as Ford GoBike in a partnership with Ford Motor Company.[4] After Motivate's acquisition by Lyft, the system was renamed to Bay Wheels in June 2019.[5] The system is expected to expand to 7,000 bicycles around 540 stations in San Francisco, Oakland, Berkeley, Emeryville, and San Jose. 
The dataset used for this exploratory analysis consists of [monthly individual trip data]( https://video.udacity-data.com/topher/2020/October/5f91cf38_201902-fordgobike-tripdata/201902-fordgobike-tripdata.csv) for Feb 2019 in CSV format covering the greater San Francisco Bay area.

#### Data wrangling process:

> 1- Coordinates of both start stations and end stations is irrelevant to our targeted analysis, so the should be elemenated:
•	Elemenate: ["start_station_latitude", "start_station_longitude", "end_station_latitude", "end_station_longitude"]
2- Duration data is per seconds , it should be converted to duration per minutes to facilitate interpretation of the analysis:
•	Add column contains duration per minutes.
3- Date data should be distributed into: start hour of day, day of week, month of year
•	Add columns contains: "hour", "day".
4-Current users ages should be extracted from "member_birth_year" column:
•	Calculate current users ages based on birth year data.
5- Dealing with data types issues: the following data types should be converted to:
•	start_time to (datetime)
•	end_time to (datetime)
•	user_type to (Catagory)
•	member_gender to (Catagory)
•	bike_share_for_all_trip to (Catagory)
6- Nan values should be removed since its porportion less than 0.05:
•Drop Nan values.



## Summary of Findings

> •	The Majority of the trips durations were quite short (within 200 mints).
•	Since trip duration distribution has right skewed shape which means that lots of points refer to low values, with a very long tail of points refer to large values: Most trips duration approximately in range (3-12) minutes. And very few trips duration lasted more than one hour (60 minutes)
•	The distribution seems roughly bimodal (has two peaks) at (8 AM) and (5 PM). Further specified analysis could examine if that correlated to factor of being most of work days start and end around those times.
•	The distribution of end trips hours also seems roughly bimodal (has two peaks) at (8 AM) and (5 PM). Which supports the Further specified analysis hypothesis that suggests: there is a positive correlation between times of trips and being most of work days start and end around those times.
•	The distribution of "start day of week" trips date also seems related to "work days" [Monday-Friday] which supports giving priority to "going to Work" as a main purpose of using "ford gobike" service.
•	"Users ages" approximately seems in range (20 - 60) with few higher values outliers, about 75% of users is less than 40 years old, and 90% less than 60 years old which support the suggestion of going to work is a main purpose of using "ford gobike" service.
•	Subscriber user type:
Duration of trips for Subscribers mostly in range (5-12) minutes. while:
•	Customer user type: Mostly rode in range (8-20) minutes which surprisingly is longer range . Also customers seems likely to last more than one hour compared to subscribers.
•	It seems like subscribers have a more specific usage or targeted purposed riding the bikes compared to customers who vary more.
•	Customers: seem to have a roughly uniform pattern of using the "ford gobike" service through all weekdays. while
•	Subscribers: seem to have a dual pattern of using the "ford gobike" service through all weekdays, large amount of subscribers uses the service through [Mondays - Fridays] but on [Saturdays- Sundays] number of subscribers who uses the service falls down, which supports the hypothesis of "going to work" as a main motive for subscribers.
•	Subscribers: seem not only slightly older than customers, but also they have a wider range of ages as well
•	Subscribers: seem more diversitive, they are males ,females and other, also customers have the same diversity: males and females with slightly higher proportion for females than the subscribers.
•	Subscribers: generally seem to have higher rates of ages among all types of genders, also females generally seem to be among younger subscribers and customers
•	Generally the range of ages of males ages is ( 20-60) for subscribers and customers, while most of "other" gender type subscribers in range ( 22- 58), also females in range (20 - 60) for both subscribers and customers same as males.
•	Customers with genders types: Male and Other. seem slightly younger than subscribers with the same types, while both subscribers and customers females have the same younger ages ranges.
•	Female customers in range (20-30) seems to be the peak of female customers while female subscribers peak seems to be in range (30-40) same as males customers and subscribers also same as "other" gender type peak.
•	Generally both Males and females in range (20-60) have the same pattern of trips durations (right skewed curve shape) which means that length of trip duration has inversely proportional relationship with Age while the "other" type gender has a unique bimodal pattern (has two peaks in range (30-40) and range (55-60).
•	Males trips durations last for more than (35 minutes) length in range (20-53) years old, while femals' lasts for the same length in range (20-45) years old. also both males and females trips durations last for (20 minutes) length in the same age range (20-60) years old.
•	"Other" gender type has a unique dual pattern, durations of trips mostly last for (20 minutes) in range (24- 41) years old, but in range (55-60) years old surprisingly trips durations lasts for more than (50 minutes) , which seems an outlier for the "Other" gender type but it seem normal pattern as it is for both males and females.
•	Generally "Other" gender type has the longest trip durations which can last for (400) minutes
•	Users older than (100 years old) almost females and "Other"s gender type.
•	It is obvious that the "Other" gender type has the longest trip durations which can last for (400) minutes and has the majority of longer than (40 minutes) trips durations.
•	All of member gender types trips durations lasts for (30 minutes) in range (60-80) years old.
•	Males has the longest trips durations in range (77 - 83) years old with more than (40 minutes) durations length.
•	Female users are the majority of users older than (90) years old with the longest trips durations (almost 25 minutes).


## Key Insights for Presentation

> * "Duration" distributions:
•	Most trips duration approximately in range (3-12) minutes. And very few trips duration lasted more than one hour (60 minutes).
"Time" per hour of the day distributions:
•	The distribution seems roughly bimodal (has two peaks) at (8 - 9 AM) and (5 - 9 PM). Further specified analysis could examine if that correlated to factor of being most of work days start and end around thoes times.
•	The distribution of end trips hours also has two peaks at (8 AM) and (5 PM). Which supports the Further specified analysis hypothesis that suggests: there is a positive correlation between times of trips and being most of work days start and end around those times.
"Date" per day of the week distributions:
•	The distribution of "start day of week" trips date also seems related to "work days" [Monday-Friday] which supports giving priority to "going to Work" as a main purpose of using "ford gobike" service.
"Users Ages" distributions:
•	"Users ages" approximately seems in range (20 - 60) with few higher values outliers, about 75% of users is less than 40 years old, and 90% less than 60 years old which support the suggestion of going to work is a main purpose of using "ford gobike" service
No transformation was needed luckily due to the straightforwardness of the data.

•	Subscribers' Durations of trips mostly in range (5-12) minutes. while Customers Mostly rode in range (8-20) minutes which surprisingly is longer range . Also customers seem likely to last more than one hour compared to subscribers. It seems like subscribers have a more specific usage or targeted purposed riding the bikes compared to customers who vary more.
•	While Customers seem to have a roughly uniform pattern of using the "ford gobike" service through all weekdays: Subscribers seem to have a dual pattern of usage.
•	Large amount of subscribers uses the service through [Mondays - Fridays] but on [Saturdays- Sundays] number of subscribers falls down, which supports the hypothesis of "going to work" as a main motive for subscribers.
•	Subscribers seem not only slightly older than customers, but also they have a wider range of ages as well.
•	Both Subscribers and customers seem diversitive, they are males, females and other, yet customers slightly have higher proportion of females than the subscribers have.
