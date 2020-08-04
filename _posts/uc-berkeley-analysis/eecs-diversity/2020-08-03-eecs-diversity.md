---
title: Diversity in EECS at UC Berkeley
date: 2020-08-03 12:00:00 +00:00
modified: 2020-08-03 12:00:00 +00:00
tags: [projects]
description: An analysis of diversity in EECS at UC Berkeley.
---

At UC Berkeley, the EECS department has struggled with issues of diversity, equity, and inclusion for decades. The Daily Cal has been reporting on diversity initiatives since [2012](https://www.dailycal.org/2012/11/13/female-students-still-struggling-to-find-foothold-in-computer-science/), with a number of articles published since then that highlight the [small fraction of female graduates](https://www.dailycal.org/2013/11/15/gender-disparity-eecs-persists/) in computer science (2013), projects studying [gender breakdowns by major](http://projects.dailycal.org/cs-gender/) (2016), columns discussing the [toxic stress culture](https://www.dailycal.org/2019/02/27/toxic-stress-culture/) perpetuated by a homogenous student body, and Op-Eds urging students and faculty to [uplift women in tech](https://www.dailycal.org/2019/04/05/campus-must-uplift-women-in-tech/) (2019).

Over the past few years, the EECS department has taken strides towards addressing these complex issues – a [multi-page website](https://eecs.berkeley.edu/about/diversity) highlights some of the initiatives taken by the department. In a 2018 Berkeley Engineering [newsletter](https://engineering.berkeley.edu/news/2018/06/tsu-jae-king-liu-named-new-dean-of-berkeley-engineering/), Dean Tsu-Jae Liu wrote:

> "Although people from every segment of society can contribute to and benefit from endeavors in engineering, today the diversity of students who study engineering is not representative of society. Creating a more inclusive environment that welcomes and supports the success of all students is critical to maximizing the impact of our educational and research programs."
>
> Dean Tsu-Jae Liu

Despite these efforts, transparency around applications, admissions, and student demographics in the department have been lacking over the past few years; the department's [By the Numbers](https://eecs.berkeley.edu/about/by-the-numbers) focuses more on statistics concerning the overall number of undergraduates and awarded degrees, rather than identifying concrete data regarding demographic backgrounds in the department. Without transparency around these fundamental data points, it's difficult to know where we've come from, where we currently lie, and where we should focus our efforts on in the future.

In this article, I present a variety of different insights into data surrounding diversity in computer science at Berkeley. This is a two-part series; this article contains an analysis of Undergraduate Applications data, filtered to **all freshman intending to begin in Fall with an intended major of EECS or L&S CS**, spanning freshman entering the 2000-01 academic year to upcoming term (2020-21). The second article will contain an analysis of departmental census data.

All data for this analysis comes from [Cal Answers](https://calanswers.berkeley.edu/home). To view any visualizations in full screen, right click the graph and select "Open Frame in New Tab/Window."

***

# A Historical Perspective

To begin, let's take a look at how applications, admissions, and SIR's have changed over the past 20 years. 

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph1.html" height="400" width="100%"></iframe>

SIR's (Statement of Intent to Register) may be informally referred to students who have "committed" to UC Berkeley. Notice the dip in applications around the dot-com bust (2002-2005) and the upward trend in applications beginning around 2010. 

### Demographic Breakdowns: Gender, Ethnicity, and Family Income 

#### Gender

Let's see how the gender ratio has progressed over time. 



<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph2.html" height="400" width="100%"></iframe>

A couple of interesting takeaways:

- There's a **local minimum** in the fraction of female-identifying students that SIR'ed in the **2007-08 academic year** (which, since these students would have SIR'ed around May 2007, falls right before the market peak in October 2007 and subsequent crash). **92.7% of students in that year identified as male.**
- Over the past three years, the fraction of male-identifying SIR'ed students has increased from an all-time low of 65% (2018-19) to 69% (2019-20) & 71% (2020-21). This implies that the incoming freshman class will be ~71% male and ~29% female.
- **Yield is almost consistently higher for males**; that is, the ratio of admitted to SIR'ed male-identifying students is greater than that of female-identifying students. 

***

#### Ethnicity

UC Berkeley provides [three different categories](https://wikihub.berkeley.edu/display/calanswers/Student+Applicants%3A+Data+Dictionary) for ethnicity, broken down by different granularities. In these plots, we use the most broad categorization – otherwise, the number of lines becomes overwhelming to analyze. Note that unlike the graph above, the applications are separated from the admitted and SIR'ed students.

*Note: double-clicking on a category in the legend will isolate only that category.*

***

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph3.html" height="400" width="100%"></iframe>

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph4.html" height="400" width="100%"></iframe>

***

Some observations from these graphs:

- The **fraction of Asian applicants has always dominated**. In particular, it's been on the upswing since 2017 (a seven-point increase from 2017-2020).
- The **fraction of White/Other applicants has been decreasing** steadily since around 2007 (time of the financial crisis?) – whereas the proportion of International, and even Underrepresented Minorities (URM's), have been gradually increasing.
- **Though the proportion of URM's that applied this year decreased slightly (~1 percent), the fraction of URM's that were admitted and SIR'ed was significantly larger this year (~10 percent increase in both admitted/SIR'ed).** This may or may not have been due to decisions made by the university in anticipation of yield rates in the midst of the COVID-19 pandemic. 



#### Family Income

Applicants report parental income in five different segments ranging from $0-25K to $150K+, with an additional "opt-out" option.

***

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph5.html" height="400" width="100%"></iframe>

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph6.html" height="400" width="100%"></iframe>

***

 A couple of observations about these graphs:

- There was a sharp decline in high-income families this academic year, though the number of unreported/unknown incomes sharply inclined. Perhaps some high-income families chose to not report their income?
- In the **years following the recession (2008-2010)**, the percentage of low-income applicants decreased slightly, whereas the percentage of **high income applicants started an upward trend.** This may be due to societal changes around that period of time (i.e. what demographics were impacted by the recession) – though the presence of the unknown option makes this less obvious. It'll be interesting to see what this looks like next year, after the full economic impacts of COVID-19 ripple through the population.



# The 2020-21 Incoming Freshman Class

Let's now take a visual look at what the demographic breakdown of this incoming class looks like. To accurately represent the incoming class, we use tree maps to visualize different permutations of demographic classes (ex: low-income male-identifying student).

A tree map consists of rectangular boxes that, in this case, correspond to the number of applicants that fall into a particular demographic class. The coloring of the rectangular boxes varies by map: some maps are shaded by Admit Rate, whereas others are shaded by just the number of applicants in the class. 

Hover over the boxes to view statistics about a particular class.

*To view a tree map in full screen, right click the map and select Open Frame in New Tab.*

### Identifying Majority and Minority Demographic Classes: Ethnicity & Gender

Below are two maps representing the same data, with different shading. These maps represent the incoming class grouped by Ethnicity and Gender (in that order). Note the **first is shaded by headcount**, where dark reds illustrate small populations and dark blues represent large proportions. **The second is shaded by admit rate**, where dark reds illustrate populations with lower admit rates (aka impacted, highly-competitive demographics) and dark blues represent populations with higher admit rates.

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph7.html" height="650" width="100%"></iframe>

In the map above, note the dominant demographic classes in terms of population density: Chinese and South Asian male-identifying students dominate the population, with 119 South Asian and 133 Chinese male-identifying students. On the other hand, there are only 10 African American female-identifying students. However, these numbers must be analyzed relative to admission rates; the map is shaded by **admit rate**, which indicates what fraction of the demographic class was admitted. Note the inverse relationship between population size and admit rate.

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph8.html" height="650" width="100%"></iframe>

### Identifying Majority and Minority Demographic Classes: Family Income & Race

The following map truly symbolizes the demographic inequalities present in this year's class; these trends mirror larger societal inequalities present in California and across the country. Pay close attention to the levels here – students are first split by family income, and then ethnicity. **The dominance of the $150K+ South Asian demographic is striking.**

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph9.html" height="650" width="100%"></iframe>

However, the inverse relationship that was so evident in the previous map (Gender/Ethnicity) isn't as clear-cut here: White and International students in the $150K+ and Income Not Reported categories have a slightly lower admit rate than South Asians, despite encompassing a smaller overall population. Moreover, the $60-80K demographic has a slightly higher admit rate than the $0-25K demographic; however, more analysis is necessary to reach a conclusion from that observation.

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph10.html" height="650" width="100%"></iframe>



### Comparing Ethnicity & First-Generation College Students

In this map, first-generation college students represent individuals who don't have a parent who's been to college. In the graph below, "NFG" stands for **Not First-Generation** and "FG" stands for **First-Generation**. Note the differences in what demographics have larger first-generation student populations (ex: Mexican American/Chicano students) and those that have much smaller first-generation populations (ex: South Asian/International). Again, note the relationships between particular demographics and admit rate.

<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph11.html" height="650" width="100%"></iframe>



# The Most Important Visual of All: The Effect of Stacked Demographic Inequalities

This visual contains arguably the most important takeaway from this entire analysis. What's contained below is a four-dimensional representation of student demographics: gender, ethnicity, income, and first-generation. The sharp differences in color represent the effect of stacked inequalities in this semester's freshman class: demographic classes that are dark blue inherently start out in a significantly different position than demographic classes that are dark red. **These inequalities represent why organizations that help support minorities in Computer Science are more important than ever.**




<iframe scrolling="no" style="border:none;" seamless="seamless" src="../../../assets/html/eecs-diversity/graph12.html" height="650" width="100%"></iframe>



# Support Minorities in STEM

Below is a list of groups that support minorities in STEM at UC Berkeley. **Please, please check out the work that they're doing: given the demographic split in the map above, it's more important than ever to help bring equity to the forefront of a computer science education at UC Berkeley!**

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

