# Is YouTube Riding the Mental Health Wave?
## Data Story Website

*Authors : Shaochen Bai, Liyu Zhang, Meichen Guo, Alessio Desogus & Alessandro D'Urso*

**Read our full data story [here](https://alessiodesogus.github.io/youniverse/).**

## Table of Contents 📋
1. [Abstract](#abstract)
2. [Research Questions](#research-questions)
3. [Proposed Additional Datasets](#proposed-additional-datasets)
4. [Methods](#methods)
5. [Proposed Timeline](#proposed-timeline--internal-milestones-im-)
6. [Organization Within the Team - Work Repartition](#organization-within-the-team)
7. [Sources](#sources)

---

## Abstract 📝

In this study, we try to investigate the trend of mental health on YouTube and how it can influence new content generated as well as new channel creation. We use the dataset YouNiverse and retrieve the mental health-related videos by identifying keywords like `mental health`, and `solitude` in their text descriptions. By then looking at the channel categories of these videos, at the visualization evolution of the channels and the videos, and with other methods, we aim to detect the influence that talking about mental health can have. An eventual correlation will then allow us to break down the different reasons for this to happen and will lead us to make several different conclusions about mental health discussions on YouTube.


## Research Questions ❓

Here are the specific research questions we plan to address :
- Is mental health a trend on YouTube?
- Which topics predominate in the mental health category?
- Is there an impact on new content?
- Did old channels (that were not speaking about mental health) start speaking about (i.e. followed the trends)?
- Can we see an increase (or decrease) in performance (subscribers, views, likes, ...) for channels that speak about mental health?


## Proposed Additional Datasets 📊

- Our analysis is well-supported by the existing (huge) dataset, and we find it sufficiently comprehensive for our research questions. Thus, we will not incorporate additional datasets.

## Methods 🔍

Methods and techniques divided by each dataset that we intend to use for our analysis: 

- ### [Video Metadata](#video-metadata-yt_metadata_enjsonlgz) [yt_metadata_en.jsonl.gz] :

**Video Filtering:** The method is based on `snowball keyword matching`. First, we design a comprehensive keyword list regarding mental health and retrieve videos whose text fields match the words. Then we iteratively look at the retrieved result and append new words to the list that we found useful. A more detailed description of the method is explained in the notebook.

**Comparing trends:** To compare trends between different topics, we would like to first select a set of topics representative in their respective categories that we hypothesize:

1. Ephemral trend: Topics that represent a short-term impulse such as `Ice Bucket Challenge`, and `Black Friday`, etc.
2. Long-term trend: Topics that reveal a real ongoing social problem including `climate change` and `gender inequality`.
3. Control group: Topics that receive limited attention but increase in video numbers because of the general user growth. Examples are `ancient Babylonia` and `Charlie Chaplin`.

**Predominant subtopics in mental health:** We first categorize the keywords into several subtopic categories [General, Lonely, Depress, Stress, Suicide, Trauma, Disorder]. Then draw a pie chart based on their frequency proportions and track the variation during the years.

- ### [Time-series Data](#time-series-data-df_timeseries_encsvgz) [df_timeseries_en.csv.gz] : 


In this section, our primary objectives are the followings :

**Identify Trends in Views and Subscribers for Mental Health Channels** : By analyzing the time-series data, our goal is to detect patterns that signify increased views and subscriber growth within mental health-related channels. This exploration provides valuable insights into emerging trends and their dynamic behaviors.

**Examine View and Subscriber Distributions**: Our analysis involves studying the distribution of views and subscribers from three perspectives:

   - **All Datetimes:** Considering the overall distribution of views and subscribers.
   - **Initial Datetime for Each Channel:** Focusing on a fixed time point, the first datetime for each channel.
   - **Last Datetime:** Examining the data at the last datetime to understand recent trends.

This multifaceted approach enhances our understanding of viewership and subscription dynamics over time.

- ### [Channel Metadata](#channel-metadata-df_channels_entsvgz) [df_channels_en.tsv.gz] : 

In this section, we will focus on two main tasks: filtering the channel and analyzing its metadata in the context of mental health.

**Filter the channel metadata**. The step is based on the filtered result from metadata. We find the corresponding channel and dig deeper into understanding of the subscribers, other videos, and ranking of these relevant channels.

**Analyze channel metadata**: This involves looking at the channel's names, categories, and other relevant information to gain insights into the creator's content. We also analyze the channel's engagement metrics, such as the number of subscribers and views to understand its popularity and reach.

- ### [Comment Table](#comment-table-youtube_commentstsvgz) [youtube_comments.tsv.gz] : 
Given considerations of project feasibility, including both the size and type of data required, the utilization of this dataset is omitted.

## Proposed Timeline & Internal Milestones (IM) 📅

| Task                              | Start Week | End Week  |
| --------------------------------- | ---------- | --------- |
| First Analysis & Results (IM1)    | Week 8     | Week 9    |
| Comparative Evaluation            | Week 9     | Week 10   |
| Second Analysis & Results (IM2)   | Week 10    | Week 13   |
| Web Site Implementation           | Week 10    | Week 13   |
| Final Check & Submission (IM3)    | Week 13    | Week 14   |

## Organization Within the Team - Work Repartition 🤝

Given the existence of three entirely independent datasets, distinct teams have been designated for each dataset: the [Video Metadata](#video-metadata), [Channel Metadata](#channel-metadata), and [Time-series Data](#time-series-data). Concurrently, parallel efforts are dedicated to exploring the data story, website implementation, and the comprehensive contextual framework of the analysis.

| Team Member        | Work Done   | 
| --------------     | ----------  | 
| Liyu Zhang         | Channel metadata analysis, sentiment analysis, visualizations for data story, website development.          |    
| Meichen Guo        | Channel metadata analysis, textual context for data story development.       | 
| Alessio Desogus    | Time-series analysis, website creation & development, textual context for data story and README.          | 
| Alessandro D'Urso  | Time-series analysis, visualizations for data story, textual context for data story.         | 
| Shaochen Bai       | Video metadata analysis, pre-proccessing data, visualizations for data story, website development.        | 

## Sources 📚

