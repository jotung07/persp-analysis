Final Exam
================
Xi Chen
December 6, 2017

Edelman, B. G., & Luca, M. (2014).
==================================

Summarize the Research Design and Explain the Computational Methods
-------------------------------------------------------------------

By conducting an observational study on Airbnb, this paper investigated the magnitude of discrimination on Airbnb. In order to empirically examine the differences in listing prices between black and non-black hosts, the researchers collected snapshots of all New York City landlords and their listings offered in Airbnb. The data included formation about the hosts, the rental prices they asked, the characteristic of their properties, and guests' reviews. Then, the researchers hired Amazon Mechanical Turk workers to rate the photos of the apartment in each listing with a seven-point scale, and categorize the race of the hosts.

This research design leverages computational methods, especially mass collaboration, to help with the research questions. For example, in order to identify the hosts' race, the researchers hired Mechanical Turk workers to code the race of the hosts into eight categories. The researchers also hired another group of Mechanical Turk workers to rate the photos of the apartment. Besides, in the data collection process, the researchers may utilize computational web scrapers, as they did in the other paper.

Evaluate the Effectiveness of the Research Design
-------------------------------------------------

### Characteristics of Big Data

Since the data was collected from Airbnb, an online marketplace with very large market size, this research design would have both good and bad characteristics of big data (Salganik, 2017).

In terms of good characteristics, firstly, the data was "big": as the authors mentioned, "As of 2013, Airbnb has 300,000 listings." Therefore, the research could benefit from the plentiful information in this large dataset. Secondly, the data was "always-on". Since Airbnb is an online marketplace, which has businesses running all the time, researchers can collect data all the time as well. Thirdly, the research design can also benefit from "non-reactive". The participants didn't know that their information was collected by the researchers, so we don't need to worry too much about the potential social desirability bias in the data.

In terms of bad characteristics, firstly, the data could be "incomplete" and "inaccessible". As the authors mentioned in the paper, even though they considered the effects of consumer demand as important factors, they had to forego this analysis because "Airbnb site provides only limited information about demand", and "Airbnb was not willing to share data for this project". Therefore, these characteristics may bring limitations to the research's effectiveness.

### Validity

The data in this research only included landlords from one city: New York, so the samples may be "non-representative", which is also one of the bad characteristics of big data. Selecting representative samples and avoiding potential biases are essentially important for an observational study. If the samples are not representative, the validity, especially the external validity of the research would be seriously undermined. In addition, hiring Mechanical Turk could be a double-edged sword. On one hand, it is easy to hire several Mechanical Turk workers to help with numerously easy tasks. On the other hand, Mechanical Turk has been criticized a lot that some of the workers just do the HITS for money, so they may not take the tasks so serious and careful. This may lead to more dirty data.

### Causal Mechanisms

In addition, we should be very careful when we try to draw causal mechanisms from observational studies. Even though the authors found big differences in rents between black and non-black hosts, it was questionable to draw a conclusion without controlling for potential confounding variables. As the authors suggested: ". many factors influence the rents received by hosts --- and race is likely correlated with some of these factors." Therefore, the authors tried to control for several variables, such as all of the information that a guest saw or the main characteristics of the listing. These efforts should be appreciated, but we still need to worry that the confounding variables may not be completely eliminated in the research.

Edelman, B., Luca, M., & Svirsky, D. (2017)
===========================================

Summarize the Research Design and Explain the Computational Methods
-------------------------------------------------------------------

By conducting a field experiment on Airbnb, this paper argued that discrimination persists and may even be exacerbated in online platforms. The research design in this paper consisted of three parts:

Firstly, the researchers collected information about the hosts, one listing offered by each host, and the past guests for each host on Airbnb in five cities: Baltimore, Dallas, Los Angeles, St. Louis, and Washington, DC. Each host had only one listing to be collected. When dealing with the hosts' information, the researchers hired Mechanical Turk workers to assess several demographical variables in each host's profile, including race, gender, and age. The information of past guests was also categorized in terms of race, gender, and age by Face ++. Besides, the researchers collected information such as the price, the number of rooms, and rantings, for each listing.

Secondly, the researchers created twenty Airbnb guest accounts. All these accounts had identical information except for guests' names and gender. There were four treatment groups, and in each group, hosts were contacted by a guest with a name that signaled either African American male, or African American female, or white male, or white female.

Thirdly, after sending 6,400 messages to hosts from guest accounts with different names, the researches tracked host responses, and categorized these responses into six groups: "Yes", "Conditional yes", "No response", "Conditional No", and "No".

Several computational methods had been employed in this research design. In terms of collecting data, the researchers used scrapers to collect data, and web browser automated tools to communicate with hosts. In order to analyze host characteristics, the researchers hired Mechanical Turk Workers to code several demographical information for each host's profile image. In order to examine the effect of prior experiences with guests, the researchers utilized Face++, a face-detection API, to recognize past guests by race, gender, and age.

Evaluate the Effectiveness of the Research Design
-------------------------------------------------

### Characteristics of Big Data

Similar to the paper above, the data in this paper was also collected from Airbnb, so the research design would have both good and bad characteristics of big data (Salganik, 2017). For example, the data was "big": as the authors mentioned, Airbnb offers three times of listings as many as Marriott's rooms worldwide as of November 2015. The authors sent roughly 64,00 messages to hosts, which created a big dataset. An example of bad characteristics is "incomplete". Since there was a noticeable amount of "No response" in the data, it was hard to examine theses participants' actual choices.

### Validity

The authors showed their efforts on external validity by including five cities: Baltimore, Dallas, Los Angeles, St. Louis, and Washington, DC. These five cities have varying levels of Airbnb usage and come from diverse geographic regions, so the samples would be more representative, compared to the data in the above paper which had only one city, New York. For internal validity, the authors only randomly selected one listing per host if the host had multiple listings, and each host would not be contacted for more than one transaction. These efforts would benefit the research's validity. However, when they collected profile pictures of past guests, the researchers only chose the ten most recent reviews on each listing page. Ten is a relatively small number in terms of sample size, which may bring potential limitations to validity.

### Causal Mechanisms

As the authors stated, "One might worry that results are driven by differences in host responses that are hard to classify, such as conditional "Yes" responses. Similarly, we would be concerned if our findings were driven by differences in response rate. African American accounts might be more likely to be categorized as spam, or hosts may believe that African American accounts are more likely to be fake." These issues are good examples of limitations in terms of mechanisms. The authors argued that these concerns could be mitigated by the results that the big difference occurred in simple "Yes" or "No" responses, instead of other intermediate responses, such as conditional "Yes". However, these confounding variables were hard to control for or eliminate in this experiment. Anther limitations of this research also included no effect of past reviews on discrimination was observed, and the experiment didn't figure out the underling mechanisms: if discrimination occurred due to race or social class.

### Heterogeneity of Treatment Effects

By examining the effects across different subgroups, the authors' effort of dealing with the heterogeneity of treatment effects should be appreciated. The authors checked the treatment effects by host characteristics, including race and gender. The results masked heterogeneity across genders: both male and female hosts had racial discriminate.

Identify the Value-added of Conducting Both Research Projects
=============================================================

Both papers show that racial difference and discrimination occurs on Airbnb. The observational study focused on the role of race in listing prices offered by hosts, and we learned that non-black hosts charged significantly more than black hosts for the equivalent properties on Airbnb. The field experiment focused on the role of race in guests' acceptance rate, and we learned that acceptance rate of guests with African American names were significantly lower than that with white names. The observational study focused more on the supply side: from the perspective of hosts, while the field experiment focused more on the demand side: from the perspective of guests. By running both of these two research projects, we can have more comprehensive understanding of the racial discrimination on Airbnb from different aspects.

With an observational study, researchers could identify the general trend or observe interesting phenomena under natural conditions, but it is hard to investigate the underlying mechanisms because many confounding variables are not being controlled. With a field experiment, which has treatment groups and control group, researchers could focus on examining the treatment effects and the underlying mechanisms by controlling other irrelevant variables. However, the participants may be "reactive" to the treatments when they know their behaviors are being observed, and then the treatment effects would be undermined. In general, field experiments have better internal validity, while observational studies have better external validity. However, this is not the case between the 2014 observational study and 2017 field experiment. The 2014 observational study's external validity was hurt by the fact that its data only included one city, New York, while the 2017 field experiment included five cities with various characteristics, which benefits its external validity. In conclusion, by running both the 2014 observational study and 2017 field experiment, we can leverage the benefits and drawbacks of these two research methods.

Apply A Digital Survey-based Research Design
============================================

Both of these two papers examined the racial discrimination on sharing economy, so I would apply a digital survey-based design based on this issue. However, I don't think a survey approach is a very good choice for this research question, because it is an ethically sensitive issue. When survey respondents answer questions related to this topic, social desirability bias would be very likely to occur. Therefore, I would ask participants questions about their own experience of being discriminated, or what do they think others' experience of being discriminated.

For example, the first set questions I would ask participants include: "Do you have experience of being discriminated when using Airbnb as a guest or host? (Five-point scale: from "Often" to "Never")

In the second set of questions, the participants were told that there are five Airbnb applicants (these applicants would have similar backgrounds, but different race). Then the participants were asked to rate these applicant's possibility to be accepted. (1: The one who is mostly likely to be accepted, 5: the one who is less likely to be accepted.)

By asking from these perspectives, the respondents' answers would be much more trustworthy. The survey will be distributed through Amazon MTurk, and the participants will get money reward by completing the survey.

There are two types of errors that often occur in the survey approach: representation error and measurement error. With regard to representation error, the data collected from the Mechanical Turk is a convenience sample, which is one of the non-probability sampling methods. The Mechanical Turk sample may not represent the complete population well. For example, there are some experienced Mechanical Turk workers who are so familiar with the MTurk mechanisms, so that they may guess or even understand the purpose of the surveys. With regard to measurement error, since racial discrimination is a sensitive issue, the respondents may guess the purpose of the questions, and then the social desirability bias may undermine the results. These confounding variables may negatively affect the effectiveness of the survey design. To deal with these potential drawbacks, I will increase the qualification required for the participants, and employ advanced statistical methods to identify and remove the uncareful respondents and outliers. I wish these could improve the quality of the data.
