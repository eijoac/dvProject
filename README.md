## Summary
This chart shows the percentage change of employment by industry since the beginning of [the great recession](https://en.wikipedia.org/wiki/Great_Recession) in Dec. 2007.

## Motivation
One of the characteristics of this recent recession is the slow recovery of employment (relative to other recessions since 1950s). It's a topic that has been discussed numerous times by the media (see, for example, an [article](http://www.heritage.org/research/reports/2011/09/how-congress-can-support-not-hinder-labor-market-recovery) and a [chart](http://www.heritage.org/~/media/images/reports/2011/09/b2602/b2602_chart2750px.ashx) therein by The Heritage Foundation).

In this project, I am interested in the speed of employment recovery by industry. The US housing bubble and the sub-prime mortgage crisis are two of the many reasons that led to the recession. I am curious about how hard construction and financial sectors were hit in terms of employment recovery, and in general how fast employment recovers in other industries.

## Data
I obtained my raw data set on monthly employment by industry from [here](http://data.bls.gov/cgi-bin/surveymost?ce), and I then cleaned it to get the information I wanted for this project.

I only investigate industries at a highly aggregated level. I have 11 industries in total based the supersectors defined [here](http://www.bls.gov/iag/tgs/iag_index_naics.htm).

## Design
In order to show how fast job recovers in each industry, I choose to report monthly percentage change in employment relative to the beginning of the recession (Dec. 2007). Since the data are time series, line chart is a natural choice.

I have 11 industries in total, and hence 11 time series. In some sense, it might be a bit too much lines to be displayed on a single chart, so I provide an option for users to selectively plot any combination of industries that they are interested in. (This is achieved by following the dimple.js sample code [here](http://dimplejs.org/advanced_examples_viewer.html?id=advanced_interactive_legends).)

## Main findings

* Construction sector indeed has the slowest job recovery rate.
* Financial sector also has a slow job recovery rate. It's only better than three other sectors, Information, Manufacturing and Construction.
* Government sector (public jobs) are mostly not affected by the recession.
* Employment in Mining and Logging sector is quite volatile after the recession.
* In contrast to all other industry sectors, employment in Education and Health sector has been steadily growing since the recession started. (It's a big surprise to me.)

## Feedback
To be added

## What I want to improve on this graph
* I want to tell a story from the chart instead of simply showing the facts.
