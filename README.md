## Summary
This chart shows the percentage change of employment by industry since the beginning of [the great recession](https://en.wikipedia.org/wiki/Great_Recession) in Dec. 2007.

## Motivation
One of the characteristics of this recent recession is the slow recovery of employment (relative to other recessions since 1950s). It's a topic that has been discussed numerous times by the media (see, for example, an [article](http://www.heritage.org/research/reports/2011/09/how-congress-can-support-not-hinder-labor-market-recovery) and a [chart](http://www.heritage.org/~/media/images/reports/2011/09/b2602/b2602_chart2750px.ashx) therein by The Heritage Foundation).

In this project, I am interested in the speed of employment recovery by industry in this recession. The US housing bubble and the sub-prime mortgage crisis are two of the many reasons that led to the recession. I am curious about how hard construction and financial sectors were hit in terms of employment recovery, and in general how fast employment recovers in other industries.

## Data
I obtained my raw data set on monthly employment (seasonally adjusted) by industry from [here](http://data.bls.gov/cgi-bin/surveymost?ce), and I then cleaned it to get the information I wanted for this project.

I only investigate industries at a highly aggregated level. I have 11 industries in total based the supersectors defined [here](http://www.bls.gov/iag/tgs/iag_index_naics.htm).

## Design
In order to show how fast job recovers in each industry, I choose to report monthly percentage change in employment relative to the beginning of the recession (Dec. 2007). Since the data are time series, line chart is a natural choice.

I have 11 industries in total, and hence 11 time series. I use color coding to distinguish the sectors. In some sense, it might be a bit too much lines to be displayed on a single chart. In addition, some readers may only want to focus on comparison between certain sectors. Therefore, I provide an option for users to selectively plot any combination of industries that they are interested in. (This is achieved by following the dimple.js sample code [here](http://dimplejs.org/advanced_examples_viewer.html?id=advanced_interactive_legends).)

## Main findings

1. Construction sector indeed has the slowest job recovery rate.
2. Financial sector also has a slow job recovery rate. It's only better than three other sectors, Information, Manufacturing and Construction.
3. Government sector (public jobs) are mostly not affected by the recession.
4. Employment in Mining and Logging sector is quite volatile after the recession.
5. In contrast to all other sectors, employment in Education and Health sector has been steadily growing since the recession started. (It's a big surprise to me.)
6. Although the recession officially ended in June 2009, at that time employment in most sectors didn't recover.

Now, I offer some comments on the above facts.

1/2) Housing bubble and financial market are where the trouble got started. No wonder that the employment in construction and financial sectors were hit hard.

3) Public jobs are the most stable ones unless the government cuts spendings, which is not something it wants to do during a recession.

4) One factor other than the recession that may affect employment in logging and mining sector is the global energy market. Since that market has been quite volatile in recent years (think of the gas price), that could be a reason why the employment in the sector is volatile. However, note that the employment in the sector only accounts for 0.6% of the total non-farm employment, so it contributes little to the overall performance of the job recovery.

5) The rising in employment in the education and health sector could simply be a long-term trend started before the recession, or it could be that people went back to school due to loss of jobs. Further investigation is needed. Checking employment in sub-sectors should help reveal some info.

6) I believe that in general job recovery lags behind output/GDP recovery in a recession.

## Feedback
Below are the feedback from teja (Udacity Coach), Marina (Udacity student) and my wife. I also included my reply and work that was done to improve my visualization in response to the feedback. teja and Marina's feedback and my reply can also be found [here](https://discussions.udacity.com/t/final-project-feedback-request-employment-recovery-by-industry-since-the-recent-recession/33768/2).

**teja's feedback and my follow-up**

Your first draft seems to have a lot of thought behind it :smile: . In addition to the points that you have already come up with here are some of my thoughts:

1) I think you can just use the year for x-axis labels instead of month+year since the tooltip already includes this information.

my follow-up: I want to make sure that people can tell that it's a monthly time series right away, so I want to keep the month there. What I did is to use the abbreviated month and 2-digit year so the labels don't take a lot of space on the x-axis.

2) You could highlight the interval on the chart corresponding the recession period. Maybe place an svg rectangle at the background of the chart. Something like the following image (just adjusted one of the values in this example):

my follow-up: I really liked this comment. The recession officially ended in June 2009, and I think I should convey this info in some way in my graph. So I added a shaded area to indicate the period of recession. I also added a note on the x-axis.

3) It wasn't obvious to me at first glance that by change you meant change with respect to the value at Jan 2008. The line plots of just the employee count in your raw data would give you the same trends but I guess it make more sense to look at it as a percentage change with respect to during the recession period.

my follow-up: the change is actually with respect to Dec. 2007. The first x-axis tick label isn't for the origin, but it's not obvious. My solution is to add grids to make it more obvious. The shaded area, the title of the graph and the note on the x-axis also make it better for user to realize that the origin is not Jan 2008.

4) Whether the employment in mining and logging industry is relatively more volatile in general is something that piqued my interest. Each kind of industry has a different spatial and temporal(seasonal) distribution of activity which contributes to this.

my follow-up: I offered some comments on my main findings.

5) The uninterrupted growth of employment in the education and health industries was also interesting point. Are they recession-proof? Maybe it could be a proxy for people going back to get advanced degrees during that period? (This could be a potential subplot for your data viz project)

my follow-up: I offered some comments on my main findings.

6) It looks like some sectors are still in the process of recovery (I'm assuming the time taken to recover to be defined by the time taken by a sector to regain the employment numbers it had at the start of the recession). It would be worth commenting on how fast or slow some industries are to recover.

my follow-up: I offered some comments on my main findings.

7) Would the correlation between the time series' give some indication of how they are influenced by each other. Some of these relations may be intuitively obvious.

my follow-up: I didn't compute the autocorrelations between the series. I offered some comments on my main findings.

**Marina's feedback and my follow-up**

I really liked the plot on percentage. This metric gives a nice idea about how the industry is getting recovered.

1) The big question is 'how was before the Recession'? One improvement would be, have a step further on the animation that shows historical data from 1945, for instance, using the same parameter, the relation with 2008. Specially because there is the statement: 'One of the characteristics of this recent recession is the slow recovery of employment (relative to other recessions since 1950s).'

And maybe it can show the bubble before crisis.

Something like http://www.nytimes.com/interactive/2012/05/17/business/dealbook/how-the-facebook-offering-compares.html?_r=01 but to the past.

my follow-up: The overall job recovery in this recent recession relative to previous ones has been extensively discussed. For example, see the graph [here](http://www.heritage.org/research/reports/2011/09/how-congress-can-support-not-hinder-labor-market-recovery). It's true that the comparison between this recession and the previous ones *by industry* is less studied. It's an interesting question, but not my focus in this project. In this project, i want to first check how job recovers by industry in this given recession.

2) On the graphic itself, the title says 'Start of 2007 recession' but the 0% variation data is from Jan/2008. It looks a bit funny, 'Is the title incorrect? Something I missed?'

my follow-up: see my follow-up 3) to teja's comment.

3) I don't think there are too many sector in your data. It makes the effect of the volume: half of the sector have recovered, half not. If we want to see the detail, we can use the legend.

my follow-up: For some people, it may be too much lines on a single chart. Or, someone may only want to focus his/her attention on two industries. I provided an option to selectively plot any combination of industries.

I like the comment on the volume. It's good to know the average weight of each industry in terms of employment. I added this info in the legend.

**my wife's feedback**

1) too much lines in a graph

my follow-up: see my follow-up 2) to Marina's comment.

2) tell a story to me instead of showing these plain boring facts

my follow-up: I offered some comments on my main findings. However, I have to say that I need to do much more to tell a real good story out of this graph. In fact, one potential good story I am thinking about is to focus on the health and education sector and to investigate further why the employment in that sector has been rising during and after the recession. This is likely to be a separate project and require more investment in time.

## Resources

1) dimple examples and API documentation from http://dimplejs.org/


