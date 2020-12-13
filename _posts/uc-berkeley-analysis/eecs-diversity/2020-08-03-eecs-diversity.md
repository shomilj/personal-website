---
title: Diversity in EECS at UC Berkeley

date: 2020-08-03 12:00:00 +00:00
modified: 2020-08-03 12:00:00 +00:00
tags: [projects]
description: An analysis of diversity in EECS at UC Berkeley.
image: /assets/html/eecs-diversity/social.png
---

<meta name="viewport" content="width=1024">
At UC Berkeley, the EECS department has struggled with issues of diversity, equity, and inclusion for decades. The Daily Cal has been reporting on diversity initiatives since [2012](https://www.dailycal.org/2012/11/13/female-students-still-struggling-to-find-foothold-in-computer-science/), with a number of articles published since then highlighting [small fraction of female graduates](https://www.dailycal.org/2013/11/15/gender-disparity-eecs-persists/) in computer science (2013), projects studying [gender breakdowns by major](http://projects.dailycal.org/cs-gender/) (2016), columns discussing the [toxic stress culture](https://www.dailycal.org/2019/02/27/toxic-stress-culture/) perpetuated by a homogenous student body, and Op-Eds calling out students and faculty to do more to [uplift women in tech]() (2019).

Over the past few years, the EECS department has taken strides towards addressing these complex issues – a [multi-page website](https://eecs.berkeley.edu/about/diversity) highlights some of the initiatives taken by the department. In a 2018 Berkeley Engineering [newsletter](https://engineering.berkeley.edu/news/2018/06/tsu-jae-king-liu-named-new-dean-of-berkeley-engineering/), Dean Tsu-Jae Liu wrote:

> "Although people from every segment of society can contribute to and benefit from endeavors in engineering, today the diversity of students who study engineering is not representative of society. Creating a more inclusive environment that welcomes and supports the success of all students is critical to maximizing the impact of our educational and research programs."
>
> Dean Tsu-Jae Liu

Despite these efforts, transparency around applications, admissions, and student demographics in the department has been lacking over the past few years; the department's [By the Numbers](https://eecs.berkeley.edu/about/by-the-numbers) focuses more on statistics concerning the overall number of undergraduates and awarded degrees, rather than identifying concrete data regarding demographic backgrounds in the department. Without transparency around these fundamental data points, it's difficult to know where we've come from, where we currently lie, and where we should focus our efforts on in the future.

In this article, I present a variety of different insights into both historical and present-day surrounding diversity in computer science at Berkeley. This is a two-part series. This article contains an analysis of Undergraduate Applications data for freshman applying into EECS or L&S CS, spanning from 2000 to the upcoming academic year (2020-21). The second article will contain an analysis of departmental census data.

All data for this analysis comes from [Cal Answers](https://calanswers.berkeley.edu/home). To view any visualizations in full screen, right click the graph and select "Open Frame in New Tab/Window." The source code for this project is available at [GitHub](https://github.com/shomilj/cal-answers). A supplementary analysis tool is available at [admissions.shomil.me](https://admissions.shomil.me).

**Update 12/13/2020: To view Fall 2020 UC Berkeley EECS & L/S CS Census Demographics, [click here](https://github.com/shomilj/cal-answers/blob/master/fall-2020-eecs-cs-census.ipynb).**

***

# A Historical Perspective

To begin, let's take a look at how EECS/CS applications, admissions, and SIR's have changed over the past 20 years. 

<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~shomil/3.embed?showlink=false"></iframe>

SIR's (Statement of Intent to Register) may be informally referred to students who have "committed" to UC Berkeley. Notice the dip in applications around the dot-com bust (2002-2005) and the upward trend in applications beginning around 2010. 

### Demographic Breakdowns: Gender, Ethnicity, and Family Income 

#### Gender

Let's see how the gender ratio has progressed over time. 

<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~shomil/6.embed?showlink=false"></iframe>

A couple of interesting takeaways:

- There's a **local minimum** in the fraction of female-identifying students that SIR'ed in the **2007-08 academic year** (which, since these students would have SIR'ed around May 2007, falls right before the market peak in October 2007 and subsequent crash). **92.7% of students in that year identified as male.**
- Over the past three years, the fraction of male-identifying SIR'ed students has increased from an all-time low of 65% (2018-19) to 69% (2019-20) & 71% (2020-21). This implies that the incoming freshman class will be ~71% male and ~29% female.
- **Yield is almost consistently higher for males**; that is, the ratio of admitted to SIR'ed male-identifying students is greater than that of female-identifying students. 

***

#### Ethnicity

UC Berkeley provides [three different categories](https://wikihub.berkeley.edu/display/calanswers/Student+Applicants%3A+Data+Dictionary) for ethnicity, broken down by different levels of precision. In these plots, we use the most broad categorization – otherwise, the number of lines becomes overwhelming to analyze. Note that unlike the graph above, the applications are separated from the admitted and SIR'ed students.

*Note: double-clicking on a category in the legend will isolate only that category.*

***

<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~shomil/12.embed?showlink=false"></iframe>

<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~shomil/10.embed?showlink=false"></iframe>

***

Some observations from these graphs:

- The **fraction of Asian applicants has always dominated**. In particular, it's been on the upswing since 2017 (a seven-point increase from 2017-2020).
- The **fraction of White/Other applicants has been decreasing** steadily since around 2007 (time of the financial crisis?) – whereas the proportion of International, and even Underrepresented Minorities (URM's), have been gradually increasing.
- **Though the proportion of URM's that applied this year decreased slightly (~1 percent), the fraction of URM's that were admitted and SIR'ed was much larger this year (~10 percent increase in both admitted/SIR'ed).** This may or may not have been due to decisions made by the university in anticipation of yield rates in the midst of the COVID-19 pandemic. 



#### Family Income

Applicants report parental income in five different segments ranging from $0-25K to $150K+, with an additional "opt-out" option.

***

<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~shomil/14.embed?showlink=false"></iframe>

<iframe width="100%" height="400" frameborder="0" scrolling="no" src="//plotly.com/~shomil/16.embed?showlink=false"></iframe>

***

 A couple of observations about these graphs:

- There was a sharp decline in high-income families this academic year, though the number of unreported/unknown incomes sharply inclined. Perhaps some high-income families chose to not report their income?
- In the **years following the recession (2008-2010)**, the percentage of low-income applicants decreased slightly, whereas the percentage of **high income applicants started an upward trend.** This may be due to societal changes around that period of time (i.e. what demographics were impacted by the recession) – though the presence of the unknown option makes this less obvious. It'll be interesting to see what this looks like next year, after the full economic impacts of COVID-19 ripple through the population.



# The 2020-21 Incoming Freshman Class

Let's now take a visual look at what the demographic breakdown of this incoming class looks like. To accurately represent the incoming class, we use tree maps to visualize different permutations of demographic classes (e.g. low-income male-identifying students).

A tree map consists of rectangular boxes that, in this case, correspond to the number of applicants that fall into a particular demographic class. The coloring of the rectangular boxes varies by map: some maps are shaded by Admit Rate, whereas others are shaded by just the number of applicants in the class. 

Hover over the boxes to view statistics about a particular class.

*To view a tree map in full screen, right click the map and select Open Frame in New Tab.*

### Identifying Majority and Minority Demographic Classes: Ethnicity & Gender

Below are two maps representing the same data, with different shading. These maps represent the incoming class grouped by Ethnicity and Gender (in that order). Note the **first is shaded by headcount**, where dark greens illustrate large populations and light greens represent small populations. **The second is shaded by admit rate**, where dark reds illustrate populations with higher admit rates and lighter reds/oranges represent populations with lower admit rates (e.g. impacted populations).

<iframe width="100%" height="650" frameborder="0" scrolling="no" src="//plotly.com/~shomil/18.embed?showlink=false"></iframe>

In the map above, note the dominant demographic classes in terms of population density: Chinese and South Asian male-identifying students dominate the population, with 119 South Asian and 133 Chinese male-identifying students. On the other hand, there are only 10 African American female-identifying students. However, these numbers must be analyzed relative to admission rates; the map below is shaded by **admit rate**, which indicates what fraction of the demographic class was admitted. Note the inverse relationship between population size and admit rate.

<iframe width="100%" height="650" frameborder="0" scrolling="no" src="//plotly.com/~shomil/20.embed?showlink=false"></iframe>

### Identifying Majority and Minority Demographic Classes: Family Income & Race

The following map truly symbolizes the demographic inequalities present in this year's class; these trends mirror larger societal inequalities present in California and across the country. Pay close attention to the levels here – students are first split by family income, and then ethnicity. **The dominance of the $150K+ South Asian demographic is striking.**

<iframe width="100%" height="650" frameborder="0" scrolling="no" src="//plotly.com/~shomil/22.embed?showlink=false"></iframe>

However, the inverse relationship that was so evident in the previous map (Gender/Ethnicity) isn't as clear-cut here: White and International students in the $150K+ and Income Not Reported categories have a slightly lower admit rate than South Asians, despite encompassing a smaller overall population. Moreover, the $60-80K demographic has a slightly higher admit rate than the $0-25K demographic; however, more analysis is necessary to reach a conclusion from that observation.

<iframe width="100%" height="650" frameborder="0" scrolling="no" src="//plotly.com/~shomil/24.embed?showlink=false"></iframe>


### Comparing Ethnicity & First-Generation College Students

In this map, first-generation college students represent students who don't have a parent who's been to college. In the graph below, "NFG" stands for **Not First-Generation** and "FG" stands for **First-Generation**. Note the differences in what demographics have larger first-generation student populations (ex: Mexican American/Chicano students) and those that have much smaller first-generation populations (ex: South Asian/International). Again, note the relationships between particular demographics and admit rate.

<iframe width="100%" height="650" frameborder="0" scrolling="no" src="//plotly.com/~shomil/29.embed?showlink=false"></iframe>


# The Most Important Visual of All: The Effect of Stacked Demographic Inequalities

This visual contains arguably the most important takeaway from this entire analysis. What's contained below is a four-dimensional representation of student demographics: gender, ethnicity, income, and first-generation. The sharp differences in color represent the effect of stacked inequalities in this semester's freshman class: demographic classes that are dark green inherently start out in a significantly different position than demographic classes that are light green. **These inequalities demonstrate why organizations that help support minorities in Computer Science are necessary and important.**



<iframe width="100%" height="650" frameborder="0" scrolling="no" src="//plotly.com/~shomil/26.embed?showlink=false"></iframe>



# Support Minorities in STEM

**As a final note, please check out the work that these groups are doing: given the demographic split in the map above, these groups are an essential part of bringing equity to the forefront of a computer science education at UC Berkeley!**

- [Association of Women in EE & CS (AWE)](http://awe.berkeley.edu/) 
- [Black Engineering and Science Students Association (BESSA)](http://ucberkeleybessa.com/)
- [CS KickStart (CSK)](http://cs-kickstart.berkeley.edu/)
- [Hispanic Engineers and Scientists (HES)](http://hes.berkeley.edu/)
- [Society of Women Engineers (SWE)](http://swe.berkeley.edu/)





# Appendix

- [Table 1: Gender Breakdowns for the 2021 Application Season](/assets/html/eecs-diversity/table1.txt)
- [Table 2: Ethnic Breakdowns for the 2021 Application Season (Level 1)](/assets/html/eecs-diversity/table2.txt)
- [Table 3: Ethnic Breakdowns for the 2021 Application Season (Level 2)](/assets/html/eecs-diversity/table3.txt)
- [Table 4: Ethnic Breakdowns for the 2021 Application Season (Level 3)](/assets/html/eecs-diversity/table4.txt)
- [Table 5: Family Income Breakdowns for the 2021 Application Season](/assets/html/eecs-diversity/table5.txt)


> If you notice any corrections and/or typos – or want to ask questions or have comments about this analysis, please reach out to me! My Berkeley email is shomil@[...] edu.

