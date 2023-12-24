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

library(tidyverse)
library(here)
library(skimr)
library(janitor)
library(lubridate)
library(ggrepel)
library(magrittr)
library(ggplot2)
library(patchwork)

### 4.2 Importing datasets <a class="anchor" id="importing_datasets_4_2"></a>

After understanding the datasets and the business questions at hand, I will just go ahead and import the necessary datasets that will help me answer the business questions. 
 
 * Daily_activity 
 * Daily_sleep 
 * Hourly_steps

* daily <- read.csv(file = "../input/bellabit/dailyActivity_merged.csv")
* hourlysteps <- read.csv(file = "../input/bellabit/hourlySteps_merged.csv")
* dailysleep <- read.csv(file = "../input/bellabit/sleepDay_merged.csv")
* intensity <- read.csv(file = "../input/bellabit/hourlyIntensities_merged.csv")

### 4.3 Preview our datasets <a class="anchor" id="preview_our_datasets_4_3"></a>
 
 In this section, I will examine my chosen data frames and review the summary statistics for each column.

head(daily)
str(daily)

head(hourlysteps)
str(hourlysteps)

head(dailysleep)
str(dailysleep)

### 4.4 Cleaning and formatting <a class="anchor" id="cleaning_and_formatting_4_4"></a>
Having gained a better understanding of my data structures, I will proceed to process them, searching for any errors or inconsistencies.
​
#### 4.4.1 Veryfying number of users
Before I continue with my cleaning process, I want to determine the number of unique users in each data frame.

n_unique(daily$Id)
n_unique(hourlysteps$Id)
n_unique(dailysleep$Id)


#### Result: The result shows 33, 33 and 24 for number of users represening daily activities, hourlystep and daily sleeps repectively.


#### 4.4.2 Duplicates
A quick search for any duplicate:

* sum(duplicated(daily))
* sum(duplicated(hourlysteps))
* sum(duplicated(dailysleep))


#### Result: The result shows 0, 0 and 3 indicating no duplication in daily activities and hourly sleeps datasets. 3 duplicates in daily sleep which i will be handling next.


#### 4.4.3 Remove duplicates and N/A
Removing the 3 duplicates seen in dailysleep dataframe.

* daily <- daily %>%
  distinct() %>%
  drop_na()

* hourlysteps <- hourlysteps %>%
  distinct() %>%
  drop_na()

* dailysleep <- dailysleep %>%
  distinct() %>%
  drop_na()


#### 4.4.4 Clean and rename columns 
I want to ensure that column names have the correct syntax and consistent format across all datasets, as we will be merging them later on. I am changing the format of all columns to lowercase.


* clean_names(daily)
daily<- rename_with(daily, tolower)

* clean_names(hourlysteps)
hourlysteps <- rename_with(hourlysteps, tolower)

* clean_names(dailysleep)
dailysleep <- rename_with(dailysleep, tolower)


#### 4.4.5 Consistency of date and time columns
I will concentrate on cleaning the date-time format for daily_activity and daily_sleep since I will be merging both data frames. Since the time component in the daily_sleep data frame is not needed, I will use 'as_date' instead of 'as_datetime
​
