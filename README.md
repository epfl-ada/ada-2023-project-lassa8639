# Is YouTube Riding the Mental Health Wave?

## Table of Contents 📋
1. [Abstract](#abstract)
2. [Research Questions](#research-questions)
3. [Proposed Additional Datasets](#proposed-additional-datasets)
4. [Methods](#methods)
5. [Proposed Timeline](#proposed-timeline--internal-milestones-im-)
6. [Organization Within the Team](#organization-within-the-team)
7. [Questions for TAs](#questions-for-tas-optional)

---

## Abstract 📝
<!-- A brief overview (around 150 words) describing the project's idea and goals. Discuss the motivation behind the project, the story you aim to tell, and why it's significant. -->

In this study, we try to investigate the trend of the mental health on Youtube and how it can influence new content generated as well as new channels creation.
We use the dataset YouNiverse and retrieve the mental health related videos by identifying key words like `mental health`, `solitude` in their text descriptions.
By then looking at the channels categories of these videos, at the visualization evolution of the channels and the videos and with other methods, we aim to detect the influence that talking about mental health can have. An eventual correlation will then allow us to breakdown the different reasons for this to happen, and will lead us to make several different conclusions about mental health discussion on Youtube.


## Research Questions ❓
<!-- - List the specific research questions you plan to address during the project. This helps to outline the scope and focus of your data analysis. -->
Here are the specific research questions we plan to address :
- Is mental health a trends on Youtube ?
- Which topics predominate in the mental health category ? 
- Is there an impact on new content ? 
- Did old channels (who were not speaking about mental health) start speaking about (i.e followed the trends) ?
- Can we see an increase (or decrease) in performance (subscribers, views, likes, ...) for channels that speak about mental health ?


## Proposed Additional Datasets 📊
<!-- - If applicable, provide a list of additional datasets you intend to use. Include details on how you plan to acquire, manage, process, and enrich these datasets. Consider data size and format, and demonstrate that you've familiarized yourself with relevant documentation. -->
- Our analysis is well-supported by the existing (huge) dataset, and we find it sufficiently comprehensive for our research questions. Thus, we will not incorporate additional datasets.

## Methods 🔍
<!-- - Briefly describe the methods and techniques you intend to use for the data analysis. This could include statistical methods, machine learning algorithms, or any other relevant approaches. -->
Methods and techniques divided by each dataset that we intend to use for our analysis: 

- ### [Video Metadata](#video-metadata-yt_metadata_enjsonlgz) [yt_metadata_en.jsonl.gz] :

**Video Filtering**: 
The method is based on `snowball keywords matching`. First, we deisgn a comprehensive keywords list regarding mental health and retrieve videos whose text fields match with the words. Then we iteratively look at the retrieved the result and append new words to the list which we found useful. A more detailed description of the method is explained in the notebook.

**Comparing trends**: To compare trends between different topics, we would like to first select a set of topics representative in their respective categories that we hypothesiz:

1. Ephemral trend: Topics that represent a short-term impulse on people posting same kind of videos. Example such as `Ice Bucket Challenge`, `Pokémon GO`, and `Black Friday`, etc.
2. Long-term trend: Topics that reveal a real ongoing social problem including `climate change`, `gender inequality`, and `online data privacy`.
3. Control group: Topics that receive limited attention but the numbers of videos increase because of the user growth in YouTube. Examples are `ancient babylonia` and `Charlie Chaplin`

<!-- From the resulting plots in the notebook, we discover the plot line pattern for each topic is:
| Topic                | Topic Type           | Line pattern         |
| -------------------- | -------------------- | -------------------- |
| Mental health        | *To be investigated* | Gradual Increase     |
| Gender inequality    | Long-going trend     | Gradual Increase     |
| Climate change       | Long-going trend     | Gradual Increase     | 
| Black Friday         | Ephemral trend       | Periodic Spikes      |
| Pokémon GO           | Ephemral trend       | Sudden Peaks         |
| Ice Bucket Challenge | Ephemral trend       | Sudden Peaks         |
| Ancient Babylon      | Control group            | Gradual Increase     |
| Charlie Chaplin      | Control group            | Fluctuating Patterns |
| Comedy               | Control group            | Gradual Increase     | -->


<!-- 1. Sudden Peaks: A sharp increase in the number of videos over a short period might suggest a trend, especially if it's followed by a sharp decline. Trends often correlate with a viral event or a fad that quickly gains and then loses public interest.
2. Gradual Increase: A steady or sequential increase in the number of videos over a longer period may indicate a growing concern or interest in an issue, suggesting it's an ongoing topic rather than a fleeting trend.
3. Sustained Levels: If after a rise, the number of videos remains consistently high instead of dropping back down, this could imply that the topic has evolved into an enduring issue.
4. Periodic Spikes: Repeated spikes could indicate recurring interest in a topic, which could be a trend that comes back in waves, possibly tied to seasonal events or recurring triggers. Examples are Black Friday as shown in our code, election, Olympics etc.
5. Fluctuating Patterns: If the number of videos varies irregularly without a clear trend or seasonality, this could indicate fluctuating interest in the topic. Such a pattern may be driven by sporadic events or news that intermittently captures public attention.  -->

<!-- From the result we see: Videos related to mental health issues are likely to follow a gradual increase pattern, which either be categorized into long-term trend or control groups. Notice,
*  Real social problems usually have a long-term impact on people's lives, which keeps the conversation going and leads to a steady creation of content.
*  On the other hand, control group videos may have been faded out from people's focus, yet they increase proportionally together with the rising number of YouTube users. We can notice that their proportion to all videos have a rather constant expectation value in long term. -->

**Predominant subtopics in mental health**: We first categorize the keywords into several subtopics [General, Lonely, Depress, Stress, Suicide, Trauma, Disorder]. Then we count their respective frequency mentioned in the text description of each video record. And draw a pie chart to see the proportion. Also, we track the trend of the variation of the proportion to see how they evolve during the years. However, the trend appears rather random and we couldn't figure out useful conclusion out of this.

<!-- | Subtopics                | Keywords           |
| -------------------- | -------------------- | 
| General        | [mental health, mental illness, emo, psycho, psychiatr] | 
| Lonely    | [solitude, alone, lonely, loneliness]     |
| Depress      | depress     | 
| Stress        | stress,  anxiety, anxious      |
| Suicide          | suicid         |
| Trauma | trauma, ptsd         |
| Disorder     | disorder          |  -->

- ### [Channel Metadata](#channel-metadata-df_channels_entsvgz) [df_channels_en.tsv.gz] : 
Processing the channel metadata is an important step in understanding the context of a video on YouTube. It allows us to gain insights into the creator's content, their audience, and the overall tone of their channel. In this section, we will focus on two main tasks: filtering the channel and analyzing its metadata in the context of mental health.

1. The first task is to filter the channel metadata based on the videos we identified in the previous step. We need to find the corresponding channel of the filtered video metadata. This will give us a better understanding of the subscribers, other videos, and ranking of these relevant channels.

2. After filtering the channel metadata, we can move on to the second task, which is to analyze the metadata. This involves looking at the channel's names, categories, and other relevant information to gain insights into the creator's content. We can also analyze the channel's engagement metrics, such as the number of subscribers and views to understand its popularity and reach.

Overall, processing the channel metadata is an important step in understanding the context of a video on YouTube. It allows us to gain insights into the creator's content, their audience, and the overall tone of their channel. By filtering and analyzing the metadata, we can make more informed decisions about the videos we watch and the creators we follow.



- ### [Time-series Data](#time-series-data-df_timeseries_encsvgz) [df_timeseries_en.csv.gz] : 
- ### [Comment Table](#comment-table-youtube_commentstsvgz) [youtube_comments.tsv.gz] : 
    Given considerations of project feasibility, including both the size and type of data required, the utilization of this dataset is omitted.

## Proposed Timeline & Internal Milestones (IM) 📅
<!-- | Idea Generation                   | Week 1     | Week 6    |
| Data Story Context                | Week 7     | Week 7    |
| Data Preprocessing                | Week 7     | Week 8    | -->
| Task                              | Start Week | End Week  |
| --------------------------------- | ---------- | --------- |
| First Analysis & Results (IM1)    | Week 8     | Week 9    |
| Comparative Evaluation            | Week 9     | Week 10   |
| Second Analysis & Results (IM2)   | Week 10    | Week 13   |
| Web Site Implementation           | Week 10    | Week 13   |
| Final Check & Submission (IM3)    | Week 13    | Week 14   |

- Note that between the Week 9 to 11 we'll also have the Homework 2 to work on it. The time will be split between the project and the homework.

## Organization Within the Team 🤝
<!-- - List internal milestones for the team, leading up to project Milestone P3. This section helps ensure everyone is on the same page regarding responsibilities and progress. -->
In the pursuit of enhanced efficiency, task allocation within our team adheres to a systematic approach. Given the existence of three entirely independent datasets, distinct teams have been designated for each dataset: the [Video Metadata](#video-metadata), [Channel Metadata](#channel-metadata), and [Time-series Data](#time-series-data).

Recognizing the challenging nature of the [Video Metadata](#video-metadata), a proportionally augmented team has been assigned to navigate its complexities. Concurrently, parallel efforts are dedicated to exploring the data story, web site implementation, and the comprehensive contextual framework of the analysis.

After we look at the data and get some initial results, we'll compare them. In the next rounds of analysis, we might work together to combine datasets if it makes sense. This way, everyone on the team stays involved and contributes to the analysis.

## Questions for TAs ❓
<!-- - Include any questions you have for the teaching assistants regarding the proposed project. This is an optional section, but it's a good opportunity to seek clarification or guidance. -->
1. Looking at the plots, result of several our experiment, we sometimes find it hard to draw any determined conclusions (Comparing trend, predominant subtopics ...). How do we proceed in the future to make the best of what we have achieved so far?
