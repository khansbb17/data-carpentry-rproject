

library("tidyverse")
str(surveys)
#select columns
select (surveys,species_id, weight)
#select rows
filter(surveys, year==1995)
# Pipes: %>%

surveys %>% 
    filter(year==1995) %>%  
    select(species_id, weight)

#select only the rows with species weight less 
#than 5, then select only the species id, sex
#weight

exercise <- surveys %>% 
  filter(weight < 5) %>% 
  select (species_id, sex, weight)

#create new column
#mutate()

data_with_kg <- surveys %>%
  mutate(weight_kg=weight/1000)

surveys %>%
  mutate(weight_kg=weight/1000, weight_kg*2)
 
  

surveys %>%
  mutate(weight_kg=weight/1000, weight_kg*2) %>%
  head()


surveys %>%
  mutate(weight_kg=weight/1000, weight_kg2=weight_kg*2) %>%
  head()

surveys %>%
  filter(!is.na(weight)) %>% 
  mutate(weight_kg=weight/1000, weight_kg2=weight_kg*2) %>%
  head()

surveys %>%
  group_by(sex) %>% 
  summarise(mean_weight=mean(weight,na.rm=TRUE))

# Data summarised accroding to the Average weight
summarise_two <- surveys %>%
  filter (!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex, species_id) %>% 
  summarise(mean_weight=mean(weight))

#Use the previous commands add a new column that gives the
# minimum weight and maximum weight)

survey_minimum <- surveys %>%
  filter (!sex=="") %>% 
  filter(!is.na(weight)) %>%
  group_by(sex, species_id) %>% 
  summarise(mean_weight=mean(weight), min_weight=min(weight))

survey_maximum <- surveys %>%
  filter (!sex=="") %>% 
  filter(!is.na(weight)) %>%
  group_by(sex, species_id) %>% 
  summarise(mean_weight=mean(weight), max_weight=max(weight))

#Counting
Count_sex <- surveys %>%
  filter(!sex=="") %>% 
  count(sex)

#Counting
Count_sex_species <- surveys %>%
  filter(!sex=="") %>% 
  count(sex,species)

#Using the previous command
#remove the missing values first (using filter), and re-run

surveys %>%
  filter (sex=="M" | sex=="F" ) %>%
  group_by (sex) %>% 
  summarise(mean_weight=mean(weight,na.rm=TRUE))



surveys %>%
  filter (sex=="") %>%
  group_by(sex) %>% 
  summarise(mean_weight=mean(weight,na.rm=TRUE))

#Sorting (arranging)

Sorting_sex_species <- surveys %>%
  filter(sex== '') %>%
  count(sex, species) %>% 
  arrange(species, desc(n))


#Reshaping the data

