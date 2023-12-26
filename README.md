![Bellabeat logo](https://miro.medium.com/v2/resize:fit:1400/1*U4x0VzHWrRYZom1zFKQGIQ.png)
# <span style="color:#8fce00"><u> Analytical report of Bellabeat fitness app data</u> </span>
​
# <span style="color:#8fce00"> Table of Contents </span>
​
* [1. Summary](#summary_1)
* [2. Ask Phase](#ask_phase_2)
     * [2.1 Business Task](#business_task_2_1)
* [3. Prepare Phase](#prepare_phase_3)
   * [3.1 Dataset used](#dataset_used_3_1)
   * [3.2 Accessibility and privacy of data](#accessibility_and_privacy_of_data_3_2)
   *  [3.3 Information about our dataset](#information_about_our_dataset_3_3)
   * [3.4 Data organization and verification](#data_organization_and_verification_3_4)
   *  [3.5 Data credibility and integrity](#data_credibility_and_integrity_3_5)
* [4. Process Phase](#process_phase_4)
    * [4.1 Installing packages and opening libraries](#installing_packages_and_opening_libraries_4_1)
    * [4.2 Importing datasets](#importing_datasets_4_2)
    * [4.3 Preview our datasets](#preview_our_datasets_4_3)
    * [4.4 Cleaning and formatting](#cleaning_and_formatting_4_4)
    * [4.5 Merging datasets](#merging_datasets_4_5)
* [5. Analyze and Share Phase](#analyze_phase_5)
    * [5.1 Type of users per activity level](#type_of_users_per_activity_level)
    * [5.2 Steps and minutes asleep per weekday](#steps_and_minutes_asleep_per_weekday)
    * [5.3 Hourly steps throughout the day](#hourly_steps_throughout_the_day)
    * [5.4 Correlations](#correlations)
    * [5.5 Use of smart device](#use_of_smart_device)
        * [5.5.1 Days used smart device](#days_used_smart_device)
        * [5.5.2 Time used smart device per day](#time_used_smart_device)
* [6. Conclusion (Act Phase)](#conclusion_act_phase)
​
# <span style="color:#8fce00"> 1. Summary </span> <a class="anchor" id="summary_1"></a>
​
Bellabeat is a tech company specializing in health-oriented smart products, encompassing devices that gather data on activity, sleep, stress, and reproductive health. This case primarily focuses on the examination of fitness data from Bellabeat's smart devices, with particular attention to the Bellabeat app. 
​
This app provides users with health-related information concerning activity, sleep, stress, menstrual cycles, and mindfulness, facilitating well-informed decisions while seamlessly integrating with their line of smart wellness products.
# <span style="color:#8fce00"> <span style="color:#8fce00"> 2. Ask Phase </span>  <a class="anchor" id="ask_phase_2"></a>
​
### 2.1 Business Task <a class="anchor" id="business_task_2_1"></a> 
​
Recognize patterns in the usage of non-Bellabeat smart devices by consumers to inform enhancements to Bellabeat's marketing approach.
​
Stakeholders 
​
* Urška Sršen - Bellabeat cofounder and Chief Creative Officer 
* Sando Mur - Bellabeat cofounder and key member of Bellabeat executive team 
* Bellabeat Marketing Analytics team

## <span style="color:#8fce00"> 3. Prepare Phase </span> <a class="anchor" id="prepare_phase_3"></a> 

#### 3.1 Dataset used: <a class="anchor" id="dataset_used_3_1"></a> 

The dataset i used in analytical case study originates from FitBit Fitness Tracker Data, which is hosted on Kaggle.
#### 3.2 Accessibility and privacy of data: <a class="anchor" id="accessibility_and_privacy_of_data_3_2"></a> 
Upon verifying the dataset's metadata, i could affirm its open-source nature. The owner has relinquished all rights to the work worldwide under copyright law, including related and extending rights, to the extent permitted by law. This means that any body that comes across this piece is free to copy, adapt, distribute, and utilize the work, including for commercial purposes, without the need for prior permission.
#### 3.3 Information about our dataset:<a class="anchor" id="information_about_our_dataset_3_3"></a> 

These datasets were created through a survey conducted on Amazon Mechanical Turk from March 12, 2016, to May 12, 2016. Thirty qualified Fitbit users gave their consent to share personal tracker data, which includes minute-level details about physical activity, heart rate, and sleep monitoring. Differences in the data stem from the use of various Fitbit trackers and individual tracking habits and preferences.

#### 3.4 Data Organization and verification: <a class="anchor" id="data_organization_and_verification_3_4"></a> 

The bellabeat dataset file i downloaded has 18 CSV files, with each file containing distinct quantitative data tracked by Fitbit App. The data is structured longitudinally, meaning each row corresponds to a specific time point for an individual. Consequently, each user possesses multiple rows of data, each identified by a unique ID and recorded based on date and time.

Given the relatively small sample size, I organized and refined the tables by creating Pivot Tables in Excel. This allowed me to assess the characteristics and observations within each table and to examine the relationships between these tables. I also determined the sample size (number of users) for each table and confirmed that the analysis covers a time span of 31 days.

| Table Name | Type | Description |
| --- | --- | --- |
| dailyActivity_merged | Microsoft Excel CSV | Daily Activity over 31 days of 33 users. Tracking daily: Steps, Distance, Intensities, Calories |
|dailyCalories_merged | Microsoft Excel CSV | Daily Calories over 31  days of 33 users |
| dailyIntensities_merged | Microsoft Excel CSV | Daily Intensity over 31 days of 33 users. Measured in Minutes and Distance, dividing groups in 4 categories: Sedentary, Lightly Active, Fairly Active,Very Active |
| dailySteps_merged | Microsoft Excel CSV | Daily Steps over 31 days of 33 users | 
| heartrate_seconds_merged | Microsoft Excel CSV | Exact day and time heartrate logs for just 7 users |
| hourlyCalories_merged | Microsoft Excel CSV | Hourly Calories burned over 31 days of 33 users |
| hourlyIntensities_merged | Microsoft Excel CSV | Hourly total and average intensity over 31 days of 33 users |
| hourlySteps_merged | Microsoft Excel CSV | Hourly Steps over 31 days of 33 users |
| minuteCaloriesNarrow_merged | Microsoft Excel CSV | Calories burned every minute over 31 days of 33 users (Every minute in single row)|
| minuteCaloriesWide_merged | Microsoft Excel CSV | Calories burned every minute over 31 days of 33 users (Every minute in single column)|
| minuteIntensitiesNarrow_merged | Microsoft Excel CSV | Intensity counted by minute over 31 days of 33 users (Every minute in single row) |
| minuteIntensitiesWide_merged | Microsoft Excel CSV | Intensity counted by minute over 31 days of 33 users (Every minute in single column)|
| minuteMETsNarrow_merged | Microsoft Excel CSV | Ratio of the energy you are using in a physical activity compared to the energy you would use at rest. Counted in minutes |
| minuteSleep_merged | Microsoft Excel CSV | Log Sleep by Minute for 24 users over 31 days. Value column not specified |
| minuteStepsNarrow_merged | Microsoft Excel CSV | Steps tracked every minute over 31 days of 33 users (Every minute in single row)|
| minuteStepsWide_merged | Microsoft Excel CSV | Steps tracked every minute over 31 days of 33 users (Every minute in single column) |
| sleepDay_merged | Microsoft Excel CSV| Daily sleep logs, tracked by: Total count of sleeps a day, Total minutes, Total Time in Bed |
| weightLogInfo_merged | Microsoft Excel CSV | Weight track by day in Kg and Pounds over 30 days. Calculation of BMI.5 users report weight manually 3 users not.In total there are 8 users |

#### 3.5 Data Credibility and Integrity:<a class="anchor" id="data_credibility_and_integrity_3_5"></a>

Due to the limitation of size (33 users) and not having any demographic information, I could encounter a sampling bias. I am not sure if the sample is representative of the population as a whole. Another problem I would encounter is that the dataset is not current, and there's also the time limitation of the survey (2 months long). That's why I will give my case study an operational approach.
    
# <span style="color:#8fce00">  4. Process Phase </span> <a class="anchor" id="process_phase_4"></a> 
 
I will center my analysis on R because of its accessibility, the volume of available data, and its capacity to generate data visualizations for communicating my findings to stakeholders.

### 4.1 Installing packages and opening libraries <a class="anchor" id="installing_packages_and_opening_libraries_4_1"></a> 

I will be installing the packages that will help my analysis only. 
I will use the following packages for the analysis: 

* tidyverse
* here
* skimr
* janitor
* lubridate
* ggpubr
* ggrepel

 ```R
library(tidyverse)
library(here)
library(skimr)
library(janitor)
library(lubridate)
library(ggrepel)
library(magrittr)
library(ggplot2)
library(patchwork)
```
  
### 4.2 Importing datasets <a class="anchor" id="importing_datasets_4_2"></a>

After understanding the datasets and the business questions at hand, I will just go ahead and import the necessary datasets that will help me answer the business questions. 
 
 * Daily_activity 
 * Daily_sleep 
 * Hourly_steps

```R
daily <- read.csv(file = "../input/bellabit/dailyActivity_merged.csv")
hourlysteps <- read.csv(file = "../input/bellabit/hourlySteps_merged.csv")
dailysleep <- read.csv(file = "../input/bellabit/sleepDay_merged.csv")
intensity <- read.csv(file = "../input/bellabit/hourlyIntensities_merged.csv")
```
### 4.3 Preview our datasets <a class="anchor" id="preview_our_datasets_4_3"></a>
 
 In this section, I will examine my chosen data frames and review the summary statistics for each column.

```R
head(daily)
str(daily)

head(hourlysteps)
str(hourlysteps)

head(dailysleep)
str(dailysleep)
```
### 4.4 Cleaning and formatting <a class="anchor" id="cleaning_and_formatting_4_4"></a>
Having gained a better understanding of my data structures, I will proceed to process them, searching for any errors or inconsistencies.
​
#### 4.4.1 Veryfying number of users
Before I continue with my cleaning process, I want to determine the number of unique users in each data frame.

```R
n_unique(daily$Id)
n_unique(hourlysteps$Id)
n_unique(dailysleep$Id)
```
#### Result: The result shows 33, 33 and 24 for number of users represening daily activities, hourlystep and daily sleeps repectively.


#### 4.4.2 Duplicates
A quick search for any duplicate:

```R
sum(duplicated(daily))
sum(duplicated(hourlysteps))
sum(duplicated(dailysleep))
```

#### Result: The result shows 0, 0 and 3 indicating no duplication in daily activities and hourly sleeps datasets. 3 duplicates in daily sleep which i will be handling next.


#### 4.4.3 Remove duplicates and N/A
Removing the 3 duplicates seen in dailysleep dataframe.

``` daily <- daily %>%
distinct() %>%
  drop_na()
hourlysteps <- hourlysteps %>%
  distinct() %>%
  drop_na()
dailysleep <- dailysleep %>%
  distinct() %>%
  drop_na()
```

#### 4.4.4 Clean and rename columns 
I want to ensure that column names have the correct syntax and consistent format across all datasets, as we will be merging them later on. I am changing the format of all columns to lowercase.

```R
clean_names(daily)
daily<- rename_with(daily, tolower)

clean_names(hourlysteps)
hourlysteps <- rename_with(hourlysteps, tolower)

clean_names(dailysleep)
dailysleep <- rename_with(dailysleep, tolower)
```

#### 4.4.5 Consistency of date and time columns
I will concentrate on cleaning the date-time format for daily_activity and daily_sleep since I will be merging both data frames. Since the time component in the daily_sleep data frame is not needed, I will use 'as_date' instead of 'as_datetime
```R
daily <- daily %>%
  rename(date = activitydate) %>%
  mutate(date = as_date(date, format = "%m/%d/%Y"))

dailysleep <- dailysleep %>%
  rename(date = sleepday) %>%
  mutate(date = as_date(date,format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))
```
I will transform the date string into a date-time format for our hourly_steps dataset.

```R
hourlysteps<- hourlysteps %>% 
  rename(date_time = activityhour) %>% 
  mutate(date_time = as.POSIXct(date_time,format ="%m/%d/%Y %I:%M:%S %p" , tz=Sys.timezone()))
```
### 4.5 Merging Datasets <a class="anchor" id="merging_datasets_4_5"></a>
I will merge the daily_activity and daily_sleep datasets to examine any correlation between variables, using id and date as their primary keys.
```R
daily_act_sleep <- merge(daily, dailysleep, by = c("id", "date"))
glimpse(daily-act-sleep)
```
# <span style="color:#8fce00"> 5. Analyze Phase and Share Phase </span> <a class="anchor" id="analyze_phase_5"></a>
I will analyze trends among Bellabeat's FitBit users to determine if that can assist me in refining BellaBeat's marketing strategy.
### 5.1 Type of users per activity level <a class="anchor" id="type_of_users_per_activity_level"></a>
Since I don't have any demographic variables from our sample, I want to determine the type of users with the data we have. I can classify the users by activity based on their daily step counts as suggested by the link below. The categorization of users is as follows:
* Sedentary - Less than 5000 steps a day.
* Lightly active - Between  5000 and 7499 steps a day. 
* Fairly active - Between 7500 and 9999 steps a day.
* Very active - More than 10000 steps a day. 
​
Classification has been performed as per the following article <https://www.10000steps.org.au/articles/counting-steps/>
​
First, I will compute the daily average of steps per user. Let's get coding!
```R
daily_average <- daily_act_sleep %>%
  group_by(id) %>%
  summarise (mean_daily_steps = mean(totalsteps), mean_daily_calories = mean(calories), mean_daily_sleep = mean(totalminutesasleep))
```
Now, I will categorize our users based on their daily average step counts.
```R
user_type <- daily_average %>%
  mutate(user_type = case_when(
    mean_daily_steps < 5000 ~ "sedentary",
    mean_daily_steps >= 5000 & mean_daily_steps < 7499 ~ "lightly active", 
    mean_daily_steps >= 7500 & mean_daily_steps < 9999 ~ "fairly active", 
    mean_daily_steps >= 10000 ~ "very active"
  ))
```
Now that there's a new column representing user types, I will generate a data frame that shows the percentage of each user type, making it easier to visualize them on a graph.
```R
user_type_percent <- user_type %>%
  group_by(user_type) %>%
  summarise(total = n()) %>%
  mutate(totals = sum(total)) %>%
  group_by(user_type) %>%
  summarise(total_percent = total / totals) %>%
  mutate(labels = scales::percent(total_percent))

user_type_percent$user_type <- factor(user_type_percent$user_type , levels = c("very active", "fairly active", "lightly active", "sedentary"))
```
Below, it is evident that users are evenly distributed based on their activity, considering their daily step counts. This suggests that users across all activity levels use smart devices.
```R
user_type_percent %>%
  ggplot(aes(x="",y=total_percent, fill=user_type)) +
  geom_bar(stat = "identity", width = 1)+
  coord_polar("y", start=0)+
  theme_minimal()+
  theme(axis.title.x= element_blank(),
        axis.title.y = element_blank(),
        panel.border = element_blank(), 
        panel.grid = element_blank(), 
        axis.ticks = element_blank(),
        axis.text.x = element_blank(),
        plot.title = element_text(hjust = 0.5, size=14, face = "bold")) +
  scale_fill_manual(values = c("#85e085","#e6e600", "#ffd480", "#ff8080")) +
  geom_text(aes(label = labels),
            position = position_stack(vjust = 0.5))+
  labs(title="User type distribution")
```
### 5.2 Steps and minutes asleep per weekday <a class="anchor" id="steps_and_minutes_asleep_per_weekday"></a>
Now, I aim to determine the days of the week when users are most active and when they tend to sleep more. Additionally, I will check if users meet the recommended daily step and sleep goals.
​
Here, I am computing the weekdays using the date column, and I am calculating the average daily steps walked and minutes slept for each weekday too.
```R
weekday_steps_sleep <- daily_act_sleep %>%
  mutate(weekday = weekdays(date))

weekday_steps_sleep$weekday <-ordered(weekday_steps_sleep$weekday, levels=c("Monday", "Tuesday", "Wednesday", "Thursday",
"Friday", "Saturday", "Sunday"))

 weekday_steps_sleep <-weekday_steps_sleep%>%
  group_by(weekday) %>%
  summarize (dailysteps = mean(totalsteps), daily_sleep = mean(totalminutesasleep))
```
Let's go ahead with the plotting now.
```R
library(pacman)
p_load(tidyverse, data.table,patchwork)
```
```R
steps_perweekday <- ggplot(weekday_steps_sleep) +
      geom_col(aes(weekday, dailysteps), fill = "#006699") +
      geom_hline(yintercept = 7500) +
      labs(title = "Daily steps per weekday", x= "", y = "") +
      theme(axis.text.x = element_text(angle = 45,vjust = 0.5, hjust = 1))
```
```R
sleep_perweekday <- ggplot(weekday_steps_sleep, aes(weekday, daily_sleep)) +
      geom_col(fill = "#85e0e0") +
      geom_hline(yintercept = 480) +
      labs(title = "Minutes asleep per weekday", x= "", y = "") +
      theme(axis.text.x = element_text(angle = 45,vjust = 0.5, hjust = 1))
  ```
Now, I will be using patchwork(R library) to arrange the plots as a single plot
```R
steps_perweekday + sleep_perweekday
```
In the charts above, we can deduce the following:
​
 * Users achieve the recommended daily step count of 7500 steps every day except on Sundays.
​
 * Users do not meet the recommended sleep duration of 8 hours.
### 5.3 Hourly steps throughout the day <a class="anchor" id="hourly_steps_throughout_the_day"></a>
​
Now, let's look at the intensity dataset to get a glimpse of users' activeness during the day. But before then, let's quickly fix some formatting issues.
```R
intensity$ActivityHour=as.POSIXct(intensity$ActivityHour, format="%m/%d/%Y %I:%M:%S %p", tz=Sys.timezone())
intensity$time <- format(intensity$ActivityHour, format = "%H:%M:%S")
intensity$date <- format(intensity$ActivityHour, format = "%m/%d/%y")
```
Now, let's go!
```R
int_new <- intensity %>%
  group_by(time) %>%
  drop_na() %>%
  summarise(mean_total_int = mean(TotalIntensity))
​
ggplot(data=int_new, aes(x=time, y=mean_total_int)) + geom_histogram(stat = "identity", fill='darkblue') +
  theme(axis.text.x = element_text(angle = 90)) +
  labs(title="Average Total Intensity vs. Time")
```
Upon examining the hourly visualization of Total Intensity, it became evident that individuals tend to be most active from 5 am to 10 pm. The peak of activity occurs during the hours of 5 pm to 7 pm.

### 5.4 Correlations <a class="anchor" id="correlations"></a>

We will now determine if there is any correlation between different variables: 

* Daily steps and daily sleep
* Daily steps and calories
```R
steps_and_sleep <- ggplot(daily_act_sleep, aes(x=totalsteps, y=totalminutesasleep))+
  geom_jitter() +
  geom_smooth(color = "red") + 
  labs(title = "Daily steps vs Minutes asleep", x = "Daily steps", y= "Minutes asleep") +
   theme(panel.background = element_blank(),
        plot.title = element_text( size=14))
```
```R
steps_and_calories <- ggplot(daily_act_sleep, aes(x=totalsteps, y=calories))+
  geom_jitter() +
  geom_smooth(color = "red") + 
  labs(title = "Daily steps vs Calories", x = "Daily steps", y= "Calories") +
   theme(panel.background = element_blank(),
        plot.title = element_text( size=14))
```
```R
steps_and_sleep + steps_and_calories
```
Judging from the combined plots above, i was able to deduced the following: 

* No significant correlation exists between users' daily activity levels, as measured by the number of steps, and their daily sleep duration.

* Otherwise, i should have seen a  positive correlation between the number of steps taken and the calories burned. Normal expectation is that, the more steps walked should result in a higher calorie expenditure. 

### 5.5 Use of smart device <a class="anchor" id="use_of_smart_device"></a> 

#### 5.5.1 Days used smart device <a class="anchor" id="days_used_smart_device"></a>

Now that I have seen some trends in activity, sleep, and calories burned, I want to understand how often the users in my sample use their device. That way, I can plan my marketing strategy and identify which features would benefit the use of smart devices.

I will calculate the number of users who use their smart device on a daily basis, classifying my sample into three categories, knowing that the date interval is 31 days:

High use: Users who use their device between 21 and 31 days.
Moderate use: Users who use their device between 10 and 20 days.
Low use: Users who use their device between 1 and 10 days.
First, I will create a new data frame by grouping by ID, calculating the number of days used, and creating a new column with the explained classification above.
```R
daily_use <- daily_act_sleep %>%
  group_by(id) %>%
  summarize(days_used=sum(n())) %>%
  mutate(usage = case_when(
    days_used >= 1 & days_used <= 10 ~ "low use",
    days_used >= 11 & days_used <= 20 ~ "moderate use", 
    days_used >= 21 & days_used <= 31 ~ "high use", 
  ))
  ```

I will now create a percentage data frame to enhance the visualization of the results in the graph. I am also ordering the usage levels.
```R
daily_use_percent <- daily_use %>%
  group_by(usage) %>%
  summarise(total = n()) %>%
  mutate(totals = sum(total)) %>%
  group_by(usage) %>%
  summarise(total_percent = total / totals) %>%
  mutate(labels = scales::percent(total_percent))

daily_use_percent$usage <- factor(daily_use_percent$usage, levels = c("high use", "moderate use", "low use"))
```
Now that I have my new table, I can create my plot.
```R
daily_use_percent %>%
  ggplot(aes(x="",y=total_percent, fill=usage)) +
  geom_bar(stat = "identity", width = 1)+
  coord_polar("y", start=0)+
  theme_minimal()+
  theme(axis.title.x= element_blank(),
        axis.title.y = element_blank(),
        panel.border = element_blank(), 
        panel.grid = element_blank(), 
        axis.ticks = element_blank(),
        axis.text.x = element_blank(),
        plot.title = element_text(hjust = 0.5, size=14, face = "bold")) +
  geom_text(aes(label = labels),
            position = position_stack(vjust = 0.5))+
  scale_fill_manual(values = c("#006633","#00e673","#80ffbf"),
                    labels = c("High use - 21 to 31 days",
                                 "Moderate use - 11 to 20 days",
                                 "Low use - 1 to 10 days"))+
  labs(title="Daily use of smart device")
```
![Uploading image.png…]()


​
