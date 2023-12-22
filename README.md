# Is YouTube Riding the Mental Health Wave?
## Data Story Website

*Authors : Shaochen Bai, Liyu Zhang, Meichen Guo, Alessio Desogus & Alessandro D'Urso*

>NOTE: we are using plotly to have interactive plots which cannot be displayed on milestone_P3.ipynb. But you can find the results in our data story listed below.

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

- Deadlines coming! Have you ever felt _stressful, anxious or even depressed_?

- Have you ever _posted your pressure on YouTube_, or simply seek guidance from _videos talking about mental problems_ on the platform? 

- Do you know there are growing amount of discussions about mental health on Youtube?

- What are they like? How many talk about them? How they influence today's channel content?

Follow our analysis and find out! Centered on the topic of mental health on YouTube, our main goal is to __look for the trend, track their contents and see the channels response toward it__. 


## Research Questions ❓

Here are the specific research questions we plan to address :
- Is mental health a trend on YouTube?
- Which topics predominate in the mental health category?
- What is the common sentiment when people talk about mental health, and what does that reveil?
- Can we see an increase (or decrease) in performance (subscribers, views, likes, ...) for channels that speak about mental health?
- Did channels that were not speaking about mental health start more often to speak about it?


## Proposed Additional Datasets 📊

- Our analysis is well-supported by the existing (huge) dataset, and we find it sufficiently comprehensive for our research questions. Thus, we will not incorporate additional datasets.

## Methods 🔍

Methods and techniques divided by each dataset that we intend to use for our analysis: 

- ### [Video Metadata](#video-metadata-yt_metadata_enjsonlgz) [yt_metadata_en.jsonl.gz] :

**Video Filtering:** The method is based on `snowball keyword matching`. First, we design a comprehensive keyword list regarding mental health and retrieve videos whose text fields match the words. Then we iteratively look at the retrieved result and append new words to the list that we found useful. A more detailed description of the method is explained in the notebook.

**Comparing trends:** To compare trends between different topics, we would like to first select a set of socially important topics representative in their respective categories, which is `climate change` and `gender inequality`.

**Predominant subtopics in mental health:** We first categorize the keywords into several subtopic categories [General, Lonely, Depress, Stress, Suicide, Trauma, Disorder], and people into several groups [Man, Woman, Teenager, Senior] and see their trend and number.

- ### [Time-series Data](#time-series-data-df_timeseries_encsvgz) [df_timeseries_en.csv.gz] : 

In this section, our primary objectives are the followings :

**Identify Gain in Views and Subscribers for Mental Health Channels**: By analyzing the time-series data, our goal is to detect if mental health video uploading signify increased views and subscribers growth within mental health-related channels. This exploration provides valuable insights into emerging trends and their dynamic behaviors.

**Select the most symbolic channel**: from the analysis of before, we try to find channels that mostly reflect the abovementioned gainings

**Identify an increasing number of uploads of mental health video**: if really thre is a gain in views when uploading a mental helath video, then, singularly, do channels upload more of it

<!-- - ### [Channel Metadata](#channel-metadata-df_channels_entsvgz) [df_channels_en.tsv.gz] : 

In this section, we will focus on two main tasks: filtering the channel and analyzing its metadata in the context of mental health.

**Filter the channel metadata**. The step is based on the filtered result from metadata. We find the corresponding channel and dig deeper into understanding of the subscribers, other videos, and ranking of these relevant channels.

**Analyze channel metadata**: This involves looking at the channel's names, categories, and other relevant information to gain insights into the creator's content. We also analyze the channel's engagement metrics, such as the number of subscribers and views to understand its popularity and reach. -->

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
