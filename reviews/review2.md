
Project Review
=====================================================


Please write detailed comments answering the questions below.
Do not just answer "yes" or "no" - comment on *how well* the authors
address each of these aspects of experimentation, and offer
suggestions for improvement.

## Overview

1) Briefly summarize the experiment in this project.
Ans) In this experiment, we measure the difference in performance in terms of delay and throughput when traffic is switched at the OVS-Switch or at the Controller.
The throughput and delay are calculated using respective Rscript that take in the raw data obtained, which further can be used to represent the captured data
in the form of graphs.


2) Does the project generally follow the guidelines and parameters we have
learned in class?
Ans) The experiment is short, to the point and easily reproducible, has a simple set up and it mostly follows the guidelines and parameters we have learned in class.
One point where it didn’t successfully follow the guidelines is that the project is incomplete, not all the goals set initially were accomplished.



## Experiment design

1) What is the goal of this experiment? Is it a focused, specific goal?
Is it useful and likely to have interesting results?
Ans) The goal of the experiment is to measure the difference in performance in terms of delay and throughput when traffic is switched at the OVS-Switch or at the Controller.
Yes, it is a focused goal, specifically on the performance part of the experiment, where it is measured in two different scenarios.
The experiment does result in a unique visual graphic data, which can be used to easily infer the difference between the stated parameters.
This experiment does show which path is the best to choose when the traffic is enabled at different areas, it is useful data, but not to a great extent.

2) Are the metric(s) and parameters chosen appropriate for this
experiment goal? Does the experiment design clearly support the experiment goal?
Ans) The metrics and parameters that were chosen are indeed appropriate for this experiment goal.
Yes, the experiment design supports the experiment as the end result is all about the visual difference between the performances between when the traffic is enabled
at the OVS Switch or at the Controller. This was clearly visible in the box graphs that were generated at the end of the experiment.

3) Is the experiment well designed to obtain maximum information with the
minimum number of trials?
Ans) The experiment has a simple set up, which resulted in not having to perform large number of trials.

4) Are the metrics selected for study the *right* metrics? Are they clear,
unambiguous, and likely to lead to correct conclusions? Are there other
metrics that might have been better suited for this experiment?
Ans) Finding out the performance of a network when there is variation in  the traffic, I would say the metrics that were selected for this experiment are the correct metrics.
They have led to results that clearly show the difference in performance in different scenarios. One other metric that they could have used is ‘Latency’,
but it would yield more or the same result as the delay.

5) Are the parameters of the experiment meaningful? Are the ranges
over which parameters vary meaningful and representative?
Ans) Yes, the parameters f the experiment are meaningful. They are simple and directly help in fulfilling the goal of the experiment.
The ranges selected for this experiment are quite small, but as we are to find the delay and throughout it would be meaningful to use such ranges.

6) Have the authors sufficiently addressed the possibility of interactions
between parameters?
Ans) The authors have clearly stated that there would be no interactions between parameters as the two scenarios in this experiment are completely independent experiments.


7) Are comparisons made reasonably? Is the baseline selected for comparison appropriate
and realistic?
Ans) The comparisons made are indeed reasonable, as they adhere to making the experiment simple and reproducible, so is the baseline selected for comparison.
Its realistic as it can be reproduced in a real life scenario, which was demonstrated with a simple but similar network in this experiment.


## Communicating results


1) Do the authors report the quantitative results of their experiment?
Ans) The authors have just stated the final conclusion in words in their report, but have attached the link to the box graph that they have obtained from the experiment in a different file.

2) Is there information given about the variation and/or distribution of
experimental results?
Ans) There was nothing in specific that was mentioned about the variations in the experiment results.

3) Do the authors practice *data integrity* - telling the truth about their data,
avoiding ratio games and other practices to artificially make their results seem better?
Ans) After reproducing the experiment myself, I can say that the authors did maintain data integrity. Their results were same as the one’s I could reproduce.

4) Is the data presented in a clear and effective way? If the data is presented in
graphical form, is the type of graph selected appropriate for the "story" that
the data is telling?
Ans) The data is represented in a graph form, the graphs that were generated were not the prefect form of data representation for this kind of experiment,
but were reasonable enough to make out the difference of performance of the different scenarios.

5) Are the conclusions drawn by the authors sufficiently supported by the
experiment results?
Ans)Yes, the conclusions draws by the author were sufficiently supported by the experiment results that I could reproduce from.


## Reproducible research


1) Did the authors include instructions for reproducing the experiment in 3 ways (Raw data -> Results,
Existing experiment setup -> Data, and Set up experiment)? Are the instructions clear
and easy to understand?
Ans) Yes, the authors included instructions for reproducing the experiment in the three ways. They mentioned how the raw data can be used for
plotting the graphs using Rscript, for different cases. Yes, the instructions are easy to understand.

2) Were you able to successfully produce experiment results?
Ans) Yes I was able to reproduce the experiment results. But only for the part that was mentioned in the author’s project report,
and not the entire goals that were mentioned in the initial project goal, as they were not demonstrated by the authors.

3) How long did it take you to run this experiment, from start to finish?
Ans) It took me about a 2 hours to run this experiment, from start to finish.

4) Did you need to make any changes or do any additional steps beyond the documentation in order to successfully complete this experiment? Describe *in detail*. How long did these extra steps or changes take to figure out?
Ans) I did not need to make any changes or take additional steps beyond the ones mentioned in the documentation in order to complete the experiment,
every step was clearly mentioned, even with supportive links to other websites for small steps.

5) In the [lecture on reproducible experiments](http://witestlab.poly.edu/~ffund/el6383/files/Reproducible+experiments.pdf), we mentioned six degrees of reproducibility. How would you characterize this experiment - where does it fall on the six degrees of reproducibility?
Ans) I would characterize this experiment as degree 4 of reproducibility. The main reason for it being is that it can be easily reproduced and that the it
requires the user to have a private ssh key, which is not given for a new user, they’ll have to generate it. The experiment doesn’t require much time to be performed either.


## Other comments to authors

Please write any other comments that you think might help the authors
of this project improve their experiment.


the experiment setup was simple, and the steps mentioned were to the point, hopefully you'l get to complete your project.
