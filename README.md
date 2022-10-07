[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
![contributors](https://img.shields.io/github/contributors/sravankr96/data-512-homework_1.svg)
![codesize](https://img.shields.io/github/languages/code-size/sravankr96/data-512-homework_1.svg) 

# data-512-homework_1

This repository contains analysis of page views of wikipedia articles intended for the Homework 1 for DATA 512 Human Centered Data Science course at the University of Washington - Masters in Data Science program

# Goal of this Project: Professionalism & Reproducibility

data-512-homework_1 project is an exercise with primary focus on incorporating the best practices for reproducibility and openness, as outlined in ["Assessing Reproducibility"](http://www.practicereproducibleresearch.org/core-chapters/2-assessment.html) and ["The Basic Reproducible Workflow Template"](http://www.practicereproducibleresearch.org/core-chapters/3-basic.html) from The Practice of Reproducible Research.

## Datasource Information

The data for this project is extracted from the wikimedia pageviews API. The pageviews API ([documentation](https://wikimedia.org/api/rest_v1/#!/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through the previous complete month. We will make use of this API to extract the page view information of a set of [dinosaur articles](https://docs.google.com/spreadsheets/d/1zfBNKsuWOFVFTOGK8qnTr2DmHkYK4mAACBKk1sHLt_k/edit?usp=sharing)

Feel free to go through the below additional documentation
- [Pageviews API Documentation](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews)
- [Wikimedia Foundation REST API terms of use](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)


## Repository Structure:
Here are the main folders in our github data-512-homework_1 repository:
```bash
data-512-homework_1
├── HW1_dino_page_visits_analysis.ipynb
├── JSON_data
│   ├── dino_monthly_cumulative_201507-202209.json
│   ├── dino_monthly_desktop_201507-202209.json
│   └── dino_monthly_mobile_201507-202209.json
├── LICENSE
├── README.md
├── dinosaur_genera.cleaned.SEPT.2022.xlsx
├── figures
│   ├── least_view_month_articles.png
│   ├── min_max_viewed_articles.png
│   └── top_10_most_viewed_articles.png
├── intermediate_files
│   ├── articles_list.csv
│   ├── dino_monthly_cumulative_201507-202209.csv
│   ├── dino_monthly_desktop_201507-202209.csv
│   └── dino_monthly_mobile_201507-202209.csv
└── requirements.txt
```

We will follow a sequence of steps in this project

## 1. Dependencies and Setup

Python 3.10 is used to develop this project. Python package requirements are automatically installed when you execute the cells in the jupyter notebook.
Before proceeding with the execution of project in jupyter notebook, please replace the below line
```bash
  BASE_PATH = '/Users/sravan/PycharmProjects/DATA-512-HCD/data-512-homework_1'
```

## 2. Data Aquisition

We will be using the above mentioned wikimedia API to fetch the pageview data related to the articles listed in the above mentioned excel file. We will then dump this data in the ``` JSON_data``` folder. We will store all our data in three files one each for mobile access, desktop access, cumulative views of the articles.

We will aslo store the intermediate data in the folder ```intermediate_files```. These files contain data related to the list of articles we are processing here and the csv formatted response data to enable us manually navigate the data in a tabular format and confirm our findings. 

JSON_data/dino_monthly_desktop_201507-202209.json - JSON file containing all articles pages view data for desktop access type
JSON_data/dino_monthly_mobile_201507-202209.json - JSON file containing all articles pages view data for mobile access type
JSON_data/dino_monthly_cumulative_201507-202209.json - JSON file containing the cumulative page views of all articles for both desktop and mobile access type

## 3. Analysis and intermediate files

We will be using the Pandas python library to perform different transformation in our data, starting from datetime conversions to gouping the data by article to find max/min/mean views that we will be further showcasing in the visualizations. Below are the intermediate files that we save to manually explore the data in a tabular format and validate our finding through the scripts.

intermediate_files/articles_list.csv - CSV file containing the list of article titles we process in this project
intermediate_files/dino_monthly_desktop_201507-202209.csv - CSV file containing all articles pages view data for desktop access type
intermediate_files/dino_monthly_mobile_201507-202209.csv - CSV file containing all articles pages view data for mobile access type
intermediate_files/dino_monthly_cumulative_201507-202209.csv - CSV file containing the cumulative page views of all articles for both desktop and mobile 

## 4. Visualizations

We will be using the famous Matplotlib python visualization library here

- Figure showing Maximum Average and Minimum Average articles

The first visualization is a time series for the articles that have the highest average page requests and the lowest average page requests for desktop access and mobile access. The graph has four lines (max desktop, min desktop, max mobile, min mobile).

[Maximum and Minimum average view articles](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/min_max_viewed_articles.png)
![Alt text](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/min_max_viewed_articles.png "Articles with fewest Months of Data")

- Figure showing Top 10 Peak Page Views

The second visualization is a time series for the top 10 article pages by largest (peak) page views over the entire time by access type. The graph has the top 10 for desktop and top 10 for mobile access (20 lines).

[Top 10 articles by views](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/top_10_most_viewed_articles.png)
![Alt text](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/top_10_most_viewed_articles.png "ML Pipeline Hyperparameter Diagram")

- Figure showing articles with fewest months of Data

The third visualization is a time series of the articles that have the fewest months of available data. The plot will have relatively short time series, some may only have one month of data. The graph has the 10 articles with the fewest months of data for desktop access and the 10 articles with the fewest months of data for mobile access.

[Top 10 least view data articles](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/least_view_month_articles.png)
![Alt text](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/least_view_month_articles.png "Articles with fewest Months of Data")

## Missing data and Exception handling

It is possible that few of the articles view data is missing in cases where an article is not available for the date we are looking against. In such cases we have used a generic exception handling to let us know what is the reason of exception and the response from the request to wikimedia API.

## Authors
- [Sravan Hande](https://github.com/sravankr96)

![GitHub Contributors Image](https://contrib.rocks/image?repo=sravankr96/data-512-homework_1)

## License
This work is licensed under MIT license. Read through the attached LICENSE file for more details about the use and distribution of this work.
