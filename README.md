## Summary
This chart highlights the very different paths of job recovery taken by each industry since [the great recession](https://en.wikipedia.org/wiki/Great_Recession).

For example, while some industries experienced significant employment loss after the recession and had extremely slow job recovery paths (see construction and manufacturing sectors), others seem to immune to the recession (see government and education & health sectors). As another example, while most industries had a slow but steady recovery path after their employment bottomed out, the path taken by the mining and logging sector is quite bumpy (volatile).

Which sector are you in? How does the job recovery path in your sector compare to your friends'? By clicking on the legend, you can selectively plot recovery paths for the sectors you are interested in.

## Motivation
One of the characteristics of this recent recession is its slow recovery of employment (relative to other recessions since 1950s). It's a topic that has been discussed numerous times by the media (see, for example, an [article](http://www.heritage.org/research/reports/2011/09/how-congress-can-support-not-hinder-labor-market-recovery) and a [chart](http://www.heritage.org/~/media/images/reports/2011/09/b2602/b2602_chart2750px.ashx) therein by The Heritage Foundation).

In this project, I am interested in the speed/path of employment recovery by industry in this recession. The US housing bubble and the sub-prime mortgage crisis are two of the many reasons that led to the recession. I am curious about how hard construction and financial sectors were hit in terms of employment recovery, and in general how fast employment recovers in other industries.

To my surprise, I found that the recovery paths for different industries are very different. I decided to make this *difference* cross industries a central theme of my visualization. Of course, while my main message is about the difference, readers can certainly discover more details from my graph.

## Data
I obtained my raw data set on monthly employment (seasonally adjusted) by industry from [here](http://data.bls.gov/cgi-bin/surveymost?ce), and I then cleaned it to get the information I wanted for this project.

I only investigate industries at a highly aggregated level. I have 11 industries in total based the supersectors defined [here](http://www.bls.gov/iag/tgs/iag_index_naics.htm).

## Design
In order to highlight the difference of job recovery path in each industry, I choose to report monthly percentage change in employment relative to the beginning of the recession (Dec. 2007). Since the data are time series, line chart is a natural choice.

I have 11 industries in total, and hence 11 time series. I use color coding to distinguish the sectors. The chart can deliver the main message well. It shows at a glance the very different recovery paths of each industry. However, in some sense, it might be a bit too much lines to be displayed on a single chart. In addition, some readers may only want to focus on comparison between certain sectors. Therefore, I choose to display five sectors by default, and I also provide an option for users to selectively plot any combination of industries that they are interested in. (This is achieved by following the dimple.js sample code [here](http://dimplejs.org/advanced_examples_viewer.html?id=advanced_interactive_legends).)

## Feedback

### Feedback led to version 2 (index2.html)

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

### Feedback led to version 3 (index3.html)

The last grader's feedback is very helpful. it quickly led to version 3.

**grader's main feedback**

This is probably the most important section of the whole project. In this rubric box it is requested your visualization describes a story, for example: identifying a relation in your data and using your graph to describe such finding in a visual way. When I start with a new project I always go directly to the visualization with the aim of identify the story it pretends to convey.

Currently, this chart is exploratory rather than explanatory. It's exploratory because the viewer is presented with all of the data, and the viewer can explore around and try to make conclusions about the data for himself. For this chart to be explanatory, you as chart maker need to tell a story about the data. You need to find something interesting and force the viewer to see what it was that you found interesting about the chart. In this point I agree with the main message from your wife's feedback: "(...)tell a story to me instead of showing these plain boring facts(...)", your visualization includes information that could be used to describe a story, but it is up to the viewer to find it.

From your data I can find multiple stories, like the one you mention: "health and education sector and to investigate further why the employment in that sector has been rising during and after the recession", this is definitely a good story to tell, but there are also others like how crisis affected the construction and financial sectors.

The second thing I did was to review your summary, and found it is phrased in exploratory words: "This chart shows the percentage change of employment by industry since the beginning of the great recession in Dec. 2007.". So, at this stage it is clear to me there is no clear story being described but data is presented for viewers to raise their own conclusions.

Note in this section of the rubric it is requested your visualization to describe a story that you identified in the dataset previously, that is, the exploratory step is in the dataset side while the explanatory step is in the visualization. Once you identify a valid story, you must describe it in the summary section, in order to point it to viewers. Apart of this, the feedback stage is quite important also since you want to use this as a test phase for your visualization, for that reason it is recommended you ask for comments not just related to design considerations, but also to the relationships they can identify in your visualization.

I think this is an interesting link where it is described the differences between explanatory and exploratory visualizations.

To end, design considerations are important since these are used to present the data to viewers in a direct and clear way. For that reason I would suggest to add a title, this helps your viewers to quickly understand the main objective of your visualization and so recognize your story.

###Feedback led to the final version

Marina and Andrew's feedback prompted me to think carefully again about the grader's suggestion. I revised my version 2 to the final version to incorporate the grader's feedback as well as my original motivation. (see [here](https://discussions.udacity.com/t/feedback-visualization/34560/13))

**Marina's feedback**

I truly liked the another...

But the focus is also interesting. The raising of the Education & Healthy is quite impressive as the fail of Construction.
One thing that passed by my mind is on the tooltip, add something like '3 months after the Dec/2007' or any 'magic date'. Maybe it would help to conduct the story.

Thanks again one more time and good look on the next submission.

**Andrew's feedback**
A few quick notes on your chart

- I think it is a clear message.
- Are these the best and the worst?? Perhaps expand a bit in some text under the heading, that there are gaps of up to 30% that persists today, that the rate in recent years are the same --- the construction jobs seems to never catch up
- Maybe try with the +y axis same height as -y (minus 30 to plus 30) -- the whitespace at the top may help reinforce the message
- Attribute your data source in a footnote perhaps

**my follow-up to Marina and Andrew's feedback**

Marina, you still like the previous chart, and Andrew, you asked me why education & health and construction sectors. Your feedback prompted me to think again. While it's true that the two sectors i picked are the best and worst and they are an interesting contrast, I could have chosen any two and make up a story. Also, by highlighting only two sectors, i lose quite a lot of info that i wanted readers to notice and perhaps to discover at first place (my original motivation).

Now, I decided to stick to my original motivation but to tell the story in a different way. This time, I want the readers to stay focused on one main message: the many different paths to the job recovery. I reverted my graph to the previous one and change the title so as to lead the reader to what i want. There are many potential stories behind the graph, but the main message i want the readers to take home is the very different paths to recover.

**Further feedback from Andrew**

I don't know how much time you have. The real challenge with your full chart is that there are 11 categories which makes it almost impossible to follow the the lines.

I think the are three or four paths in your data.

- bust and boom - mining (could go into the next group)

- ultimate winners - education leisure and business

- deep fall and never recover (ultimate losers) -- the bottom three lines

- back to normal - Other, trade and finance, government

Then maybe some of these ideas individually or combined

- add some text for each group,

- use a palette that assigns different shades of the same color to each group e.g. shades of red, shades of blue, shades of green, shades of purple to the three groupings. Use these colors in the text somehow to associate and perhaps a click button to selects only the members of that group together (i wonder i simple has any grouping features)

- three separate charts with more compressed y axis to show each group. (be sure to keep the y axis identical) (almost like sparklines)

For palettes you can try colorbrewer.org. Choose "sequential" and number of classes at top left (4) - click single hue and you will get a set of colored palletes. Click export and you get code.

You can also try heavier lines - or just heavier for the top group and bottom group and the middle group stick with lighter lines because it is the least interesting group. Sometimes heavier lines are needed to discern different shades.

Jay - one more simpler thought that keys off yours. Plot only the top 4 and the bottom 3, a tale of gains and losses, with shades from two colors.

**my follow-up**

Thanks again. Based on your suggestion, i am thinking of another potentially simpler solution. How about I only show a few representative sectors by default, say construction, manufacturing, education & health, mining & logging, and government. The main message here is the diverse paths to recovery, winners and losers in your words. I will still offer the options for the readers to select other sectors of their interest. In this way, i can still have all the industries (otherwise, you would always wonder about other sectors), I can make the graph less messy (by default), and I can highlight the main message.

## Many paths to recovery (my own takeaways)

I discuss my own takeaways from reading/studying the graph. Note that they are not necessary the main messages I want to deliver to the reader. The main message or the explanatory part I want to convey to the reader is, again, the very different paths of job recovery in each industries. However, that doesn't prevent a reader, like me, to get more out of the graph, i.e., to explore a bit more from the graph.  

The facts I see,

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

## Resources

1) dimple examples and API documentation from http://dimplejs.org/


