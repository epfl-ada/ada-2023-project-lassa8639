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
We use the dataset YouNiverse and we filter it, identifying the mental health related videos as the ones containing, in title, description or tag, some key words like INSERT.
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

- ### [Video Filtering]
To effectively filter relevant videos from a large dataset for mental health-related content, we've established a robust method centered around keyword string matching. We begin by creating a custom keyword list tied to mental health topics. As we parse the dataset in manageable batches, we examine video descriptions, tags, and titles, requiring at least two to match our keywords for a video to be considered relevant. Utilizing pd.DataFrame.str.contains, we identify these matches efficiently.

Upon extracting a subset of videos, we manually review them to discover any prevalent but previously unlisted keywords. These are then added to our keyword list, and the process is repeated to refine our results. Additionally, we apply a secondary filter to remove certain categories, notably Music and Movies, as they often contain misleading keywords like lonely or alone that could result in false positives.


- ### [Video Metadata](#video-metadata-yt_metadata_enjsonlgz) [yt_metadata_en.jsonl.gz] :
We propose the below categorization system for patterns of video numbers related to a certain topic:

1. Sudden Peaks: A sharp increase in the number of videos over a short period might suggest a trend, especially if it's followed by a sharp decline. Trends often correlate with a viral event or a fad that quickly gains and then loses public interest.
2. Gradual Increase: A steady or sequential increase in the number of videos over a longer period may indicate a growing concern or interest in an issue, suggesting it's an ongoing topic rather than a fleeting trend.
3. Sustained Levels: If after a rise, the number of videos remains consistently high instead of dropping back down, this could imply that the topic has evolved into an enduring issue.
4. Periodic Spikes: Repeated spikes could indicate recurring interest in a topic, which could be a trend that comes back in waves, possibly tied to seasonal events or recurring triggers. Examples are Black Friday as shown in our code, election, Olympics etc.
5. Fluctuating Patterns: If the number of videos varies irregularly without a clear trend or seasonality, this could indicate fluctuating interest in the topic. Such a pattern may be driven by sporadic events or news that intermittently captures public attention. 

And we try to match the above patterns to below Youtube video types:

1. Ephemral trend; examples in our implementations are Ice Bucket Challenge, Pokémon GO, and Black Friday.
2. Long-going trend that reveals real social problems; our implementation includes climate change, gender inequality, and online data privacy.
3. Some old topics that aren't likely to be new trend; numbers of these videos are likely to increase linearly proportional to the total video numbers; examples are ancient babylonia and Charlie Chaplin

As shown by the resulting plots in the notebook, we can discover that for the number of videos under each topic:
| Topic                | Video type           | Plot pattern         |
| -------------------- | -------------------- | -------------------- |
| Mental health        | *To be investigated* | Gradual Increase     |
| Gender inequality    | Long-going trend     | Gradual Increase     |
| Climate change       | Long-going trend     | Gradual Increase     | 
| Black Friday         | Ephemral trend       | Periodic Spikes      |
| Pokémon GO           | Ephemral trend       | Sudden Peaks         |
| Ice Bucket Challenge | Ephemral trend       | Sudden Peaks         |
| Ancient Babylon      | Old topic            | Gradual Increase     |
| Charlie Chaplin      | Old topic            | Fluctuating Patterns |
| Comedy               | Old topic            | Gradual Increase     |

From current level's analysis, videos related to mental health issues are more likely to follow a gradual increase in their video numbers. According to our current analysis, mental health videos can either be categorized into long-going trend or old topic.
*  Real social problems usually have a long-term impact on people's lives. This consistent impact keeps the conversation going, leading to a steady creation of content.
*  On the other hand, old topics may have been faded out from people's focus, yet they may increase proportionally together with the rising number of YouTube users. In our analysis for percentage of old topic videos out of all videos, we can notice that their plots have a rather constant expectation value in long term.

More examples under each video type will be involved for more accurate inference.

- ### [Channel Metadata](#channel-metadata-df_channels_entsvgz) [df_channels_en.tsv.gz] : 
- ### [Time-series Data](#time-series-data-df_timeseries_encsvgz) [df_timeseries_en.csv.gz] : 
- ### [Comment Table](#comment-table-youtube_commentstsvgz) [youtube_comments.tsv.gz] : 
    Given considerations of project feasibility, including both the size and type of data required, the utilization of this dataset is omitted.

## Proposed Timeline & Internal Milestones (IM) 📅

| Task                              | Start Week | End Week  |
| --------------------------------- | ---------- | --------- |
| Idea Generation                   | Week 1     | Week 6    |
| Data Story Context                | Week 7     | Week 7    |
| Data Preprocessing                | Week 7     | Week 8    |
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
1.
