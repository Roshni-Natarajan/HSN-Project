
Project Review
=====================================================


## Overview

1) Briefly summarize the experiment in this project.
In SDN, openflow protocol offloads the control plane of all the switches to a central controller. Thus, the behaviour of a network is defined by a central software.
The forwarding decision can be taken in three places - Data plane, Switch CPU and Controller. The fowarding decision performed at the controller would be different than when the decision is done at the ovs switch. The forwarding decision when done at ovs
switch has lesser delay giving higher throughput contrary to the decision at controller, which results in higher delay and lesser throughput.


2) Does the project generally follow the guidelines and parameters we have
learned in class?
Yes, the project follows the guidelines and parameters we have learned in class.
The goal of the experiment is specific and focused.
They have provided the rspec files and images of each steps in reserving resources while performing the experiment so there is clarity in the applied methodology.
They have selected the reasonable metrices and parameters.
For visualization, they have submitted the steps along with the processed outputs through some shell and python scripts.
Since, they have provided well documented experimental procedure in a clean and precise manner, one should be able to reproduce the experiment.


## Experiment design

1) What is the goal of this experiment? Is it a focused, specific goal?
Is it useful and likely to have interesting results?
The goal of the experiment to find the difference in the performance when the forwarding decisions is made at the controller and the ovs switch. Yes, the goal is focussed
and specific since, they are clearly specifying that they want to see the difference in performance.
It is useful and likely to have interesting results, as the experiment concludes with the performance evaluation when the decision is
made at switch and controller, by measuring the delay and throughput by using iperf and ping.


2) Are the metric(s) and parameters chosen appropriate for this
experiment goal? Does the experiment design clearly support the experiment goal?
The metrics and parameters chosen were throughput, delay and the switching decision made at the controller and the switch for the experimental goal.
Yes, the experimental design clearly supports the experimental goal since the delay and throughput will make a clear difference on the performance level
when the switching decision is performed at different places.


3) Is the experiment well designed to obtain maximum information with the
minimum number of trials?
They have conducted 4 trials for each flow control to measure the throughtput and also, 4 trials for each flow control to measure the delay. They have processed
the result of the ping through bash script to get delay for each flow control. Since, they have come accross a conclusive result with these number of trials, the
experiment is well designed to obtain maximum information with the minimum number of trials.


4) Are the metrics selected for study the *right* metrics? Are they clear,
unambiguous, and likely to lead to correct conclusions? Are there other
metrics that might have been better suited for this experiment?
Yes, the metrices selected for study are the right metrices.
They are clear enough to lead to correct conclusions as we can see difference in the performance through throughput.

5) Are the parameters of the experiment meaningful? Are the ranges
over which parameters vary meaningful and representative?
The parameters of the experiment are meaningful due to the inherent difference in delay in design of the sdn .
The idle timeout can be varied in range of 0,11 through 65535 and the hard timeout in range of 0 through 65535.
The authors have chosen hard timeout and idle timeout to be 30 and 10 for proactive flow, 1 and 1 for reactive flow controls.In my opinion, the ranges
over which parameters vary seem meaningful but would have been more representative if the authors would have shown with some other values in the possible range
to further support the meaningfulness of the parameters.


6) Have the authors sufficiently addressed the possibility of interactions
between parameters?
The authors have addressed in their proposal that there would be no interactions between the parameters
since the two are completely different scenarios.



7) Are comparisons made reasonably? Is the baseline selected for comparison appropriate
and realistic?
The comparisons made are reasonable since the baseline selected for comparison is appropriate and realistic due to the design of the SDN
architecture itself. The delays are inherent when decisions are made at the switch and the controller, resulting in the difference in performance level.


## Communicating results


1) Do the authors report the quantitative results of their experiment?
The authors have reported the quantitative results of their experiment through throughput and delay (which was processed from output of ping).

2) Is there information given about the variation and/or distribution of
experimental results?
The authors have not given informations about the variation or distribution of experimental results for some other set up like change in the number of
flows or number of server cluster, different values of idle time and hard time.


3) Do the authors practice *data integrity* - telling the truth about their data,
avoiding ratio games and other practices to artificially make their results seem better?
The authors have practiced data integrity since they have used their experimental data without any manipulations.
They have not used incomparable bases and combined them to their advantage so have avoided the ratio games to artificially make their results look better.

4) Is the data presented in a clear and effective way? If the data is presented in
graphical form, is the type of graph selected appropriate for the "story" that
the data is telling?
The data is presented in a clear and effective way through box plot.It shows the median average value, cases that fall inside the box, shows the
upper and lower marks for the cases chosen and also some exceptions that might happen.It shows the comparative variation in delay and throughput for two
chosen parameters which successfully represents the aim of the experiment.
Thus, the selected graph is appropriate for presenting the data.

5) Are the conclusions drawn by the authors sufficiently supported by the
experiment results?
We can see that the throughput is higher when forwarding decision is made at the switch as the delay is lesser while throughput
is lesser when forwarding decision is made at the controller as the delay is more. Thus, the experiment results sufficiently support the conclusions drawn by the
authors as we can clearly see the difference in performance.

## Reproducible research



1) Did the authors include instructions for reproducing the experiment in 3 ways (Raw data -> Results,
Existing experiment setup -> Data, and Set up experiment)? Are the instructions clear
and easy to understand?
Yes, the authors have included instructions for reproducing the experiment in 3 ways (Raw data -> Results, Existing experiment setup -> Data and set up experiment) .
Yes, the instructions provided by authors are easy and clear to understand as they have attached images of every steps to perform the experiment along with the required codes.
They have provided all the script files ,rpsec files , instructions to install the R studio and some problems that might come with probable solutuion.


2) Were you able to successfully produce experiment results?
Yes, I was able to successfully produce the experiment results.

3) How long did it take you to run this experiment, from start to finish?
After working out with some of the problems I faced initially, it took me around 2-3 hours to run this experiment.

4) Did you need to make any changes or do any additional steps beyond the documentation in order to successfully complete this experiment? Describe *in detail*. How long did these extra steps or changes take to figure out?
By using the given rpsec file I was able to reserve the resources and login to the machines. But I came accross error saying invalid private rsa key, eventhough I followed the instructions
to edit the empty key file and resource.py file to replace the default vaules the authors have provided.
Also, with the live setup , I was able to login as a guest and go to the specified directory.But, I was not able to run the final run script to perform the experiment. I figured out later
that the key file was empty and the authors didnt put their private key in the key file.
So, finally I followed their instructions to work on the project without using their rspec file. But, I used their script files to produce the data files .
It took me around 2-3 hours to figure out the key problems. Even with the script files provided by the authors , it took me around 72 hours to carryout the experiment.
Majority of time was spent on integrating the working of the controller, ovs switch and two hosts from the management virtual machine.

5) In the [lecture on reproducible experiments](http://witestlab.poly.edu/~ffund/el6383/files/Reproducible+experiments.pdf), we mentioned six degrees of reproducibility. How would you characterize this experiment - where does it fall on the six degrees of reproducibility?
On the degrees of reproducibility , I would like to put the project on number 3. Even though the live setup and rpsec file didnot work directly, the authors have provided
sufficient instructions to reproduce the experiment.


## Other comments to authors

Please write any other comments that you think might help the authors
of this project improve their experiment.

 I would like to suggest the problems I  faced.
-For the live setup I found the resource.py file with author's login credentials : username, password and location for private key. But, I found that the key file was empty .So, probably the authors forgot to put their private keys on the key file.
-The instruction says that the files ping_processor1.sh and ping_processor2.sh are in directory SCRIPTS but they are present in directory DATAFILES so while running
commands "bash ping_processor1.sh ping_output_1 ping_output_2 ping_output_3 ping_output_4" and "bash ping_processor2.sh ping_output_5 ping_output_6 ping_output_7 ping_output_8
"to generate delay files we need to add the correct paths.
