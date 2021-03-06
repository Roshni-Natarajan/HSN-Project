Project Report for EL6383
===========================

## Team : 

	1. Jatan Nilesh Gandhi
	2. Roshni Natarajan
	3. Santhosh Kumar Rajendran
    
## Experiment Design :

**TOPIC :**  (SDN) Difference in performance when forwarding is done at the Switch or the Controller.
	
**GOAL :** To measure the difference in performance in terms of delay and throughput when traffic is switched at the OVS-Switch or at the Controller.
	
**Metrics :** 
	
The two metrics that were measured are :

	1. Throughput
	2. Delay 
 
In the SDN architecture, the packet forwarding decisions can be taken in three places, namely at the 

	1. Data-Plane or 
	2. Switch-CPU or 
	3. Controller.
	
Because of this design, there is an inherent difference in delay and consequently on the throughput when the forwarding is done at these three different layers. Thus these metrics were measured.
	
**Parameters :**
	
The two parameters are : 

	1. Switching done at OVS-Switch
	2. Switching done at the Controller
		
**Data Collection** : 
	
**iperf** and **ping** were used in order to collect Data once the experiment setting was configured. 
	
	
**Analysis :** 
	
Raw Data is obtained by running the Python script (explained below). In order to analyse the results, we use Box Plots plotted with the help of "R". 
	
Rscript is written to plot the Throughput obtained in both Reactive Flow Control and Proactive Flow Control by using the Raw Data from iperf.
	
In order to create the Rscript to plot the Delay, we need to process the ping output obtained. This is done using Shell Scripts named "ping_processor1.sh" and "ping_processor2.sh".
	
The required box plots are generated by running the respective Rscripts. 
	
Intially, to measure the Jitter too was part of the Goal, but due to a time constraint only the Throughput and Delay were measured. 

We thought Raw Data would be sufficient for analysis but we had to process the output obtained from ping. Hence we use a processing script named "ping_processor#.sh". 
This script creates a file that stores the average delay values obtained from ping. This file is later used in R to plot the Delay. 


**Implementation :** 
	
An experiment setup of 2 Hosts connected through an OVS Switch was achieved. The OVS switch is controlled by the Controller. 
	
**To portray the switching done at the OVS Switch[ Proactive Flow Control] :** 
	
The Hard Time and Idle Time of the Controller are set to 30 and 10 respectively. 
	
Traffic is sent from Host 1 to Host 2 and Throughput(using iperf) and Delay(using ping) are measured.
	
**To portray the switching done at the Controller[ Reactive Flow Control] :** 
	
The Hard Time and Idle Time of the Controller are set to 1 and 1 respectively.
	
Traffic is sent from Host 1 to Host 2 and Throughput(using iperf) and Delay(using ping) are measured.
	
The above steps are executed by running a Python Script named **" run_experiment.py"**. This script performs the entire experiment by creating the network steup and measuring values at both the scenarios.
	
The various **Tools** used in order to implement the experiment are : 
	
	1. Geni 
	2. Python 
	3. iperf 
	4. ping 
	5. Shell
	
**Results :** 
		
The experiment results convey that : 
		
Reactive Flow Control has a higher Delay when compared to Proactive Flow Control.
			
Proactive Flow Control has a Better Throughput than Reactive Flow Control. 

## **Instructions for Reproduction :** 

## **1. Experiment Setup :** 

**Experiment Instructions :** 

Clone the Bit Bucket project : https://bitbucket.org/SanthoshKumarR/el6383-hsn-project

`git clone https://bitbucket.org/SanthoshKumarR/el6383-hsn-project`

This has all the files required to perform the experiments.

DATA_FILES 	: Has the experiment data captured by us.

RSPEC_FILES : Has the rspec files required to deploy the resources we need.

SCRIPTS 	: This has all the shell and python scripts required to perform the experiment.


**Experiment Procedure :** 

(1) Create 3 Slices

On Slice 1 : Deploy the management VM. Use the Rspec provided (mgmt_rspec.xml) to deploy the management VM. Screenshot provided.

![Management_Rspec.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/Management_Rspec.png)

On Slice 2 : Deploy controller. Use the Rspec provided (controller_rspec.xml) to deploy the controller VM. Screenshot provided.

![Controller_Rspec.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/Controller_Rspec.png)

On Slice 3 : Deploy OVS-switch and hosts. Use the Rspec provided (ovs_rspec.xml) to deploy the OVS-switch and hosts. Screenshot provided below.

![OVS_Rspec.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/OVS_Rspec.png)
	
(2) Wait until ALL the components are READY.

(3) Login to the Management VM using your Private Key(id_geni_ssh_rsa).

(4) Install the required Packages by running the following commands in the Management VM.

	sudo apt-get install python-pip
	sudo apt-get install python-dev
	sudo pip install pycrypto	
	sudo pip install paramiko
	
(5) Clone the Bit Bucket project : https://bitbucket.org/SanthoshKumarR/el6383-hsn-project

`git clone https://bitbucket.org/SanthoshKumarR/el6383-hsn-project` onto the Management VM.

(6) Change working directory to **“SCRIPTS”** using the following command 
	
`cd el6383-hsn-project/SCRIPTS/`

Link on how to edit using vi : [http://www.howtogeek.com/102468/a-beginners-guide-to-editing-text-files-with-vi/](http://www.howtogeek.com/102468/a-beginners-guide-to-editing-text-files-with-vi/)

(7) Copy the contents of the Private key(id_geni_ssh_rsa) into the Blank file named **“ id_geni_ssh_rsa “** that can be found in the current working directory. 
 	
Get the contents from your desktop’s id_geni_ssh_rsa and paste it in the id_geni_ssh_rsa present in the VM. This can be done by using vi.
The contents look like this : 
![Private Key content](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/96d9b33d371a5c6795bae4789fd0d7c81abe2ee0/SCREENSHOTS/private_key.png)

(8) Change the Permission of “id_geni_ssh_rsa” by 
		
`chmod 0600 id_geni_ssh_rsa`

(9) Modify the **Resource.py** to replace the existing details with your details by following the Comments in the file.

Controller Hostname Screenshot : 
![Hostname Controller.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/Hostname%20Controller.png)

OVS Hostname Screenshot : 
![Hostname OVS.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/Hostname%20OVS.png)

Host1 host name and portnumber Screenshot : 
![Hostname host1.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/Hostname%20host1.png)

Host2 host name and portnumber Screenshot : 
![Hostname host2.png](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/30e119918d0310e573eebc49ff28c62bf23e162b/SCREENSHOTS/Hostname%20host2.png)

## 2. **Execution :** 

(10) Run the Python Script(run_experiment.py) using the following command. 

`./run_experiment.py`
	
The above Python script performs the entire experiment and generates the required Raw Data Files for two different scenarios.

(a) Switching at the OVS :
iperf outputs
ping outputs

(b) Switching at the Controller :	
iperf outputs
ping outputs

## 3. **Data Analysis :** 

(11) Using the **ping_processor#.sh** generate the Processed Data files for the Ping Outputs by : 

Generate “ Delay_1 “ file by running : 

	bash ping_processor1.sh ping_output_1 ping_output_2 ping_output_3 ping_output_4
       
Generate “ Delay_2 “ file by running : 

	bash ping_processor2.sh ping_output_5 ping_output_6 ping_output_7 ping_output_8

(12) In order to communicate the results of the experiment we require R. The instructions to install R are present in the Lab 2b link. The link is as follows :

[https://bitbucket.org/ffund/el6383/src/c91349619100eca34af28298fa4289bf7311c4a8/lab2b/?at=master](https://bitbucket.org/ffund/el6383/src/c91349619100eca34af28298fa4289bf7311c4a8/lab2b/?at=master)
	
If the server doesn’t restart or doesn't connect, try the following command : 
 	
	export LC_ALL=“en_US.UTF-8” 	
	rstudio-server restart

Now login to R using the HostName of the Management VM. 

(13) Now, we can run the R scripts “tput.R” and “Delay.R” as follows : 

Navigate to el6383-hsn-project -> SCRIPTS  
 
Click on **More** and select **“Set As Working Directory“**

![R working directory](https://bytebucket.org/SanthoshKumarR/el6383-hsn-project/raw/96d9b33d371a5c6795bae4789fd0d7c81abe2ee0/SCREENSHOTS/R_working_dir.png)
	
Run the **“tput.R”** and **“Delay.R”** files to obtain the respective plots. 


## ** Existing Setup Details **

**Guest user details : **

Username : guest, Password : Guest1234

	Management VM : pcvm3-50.genirack.nyu.edu
	Controller VM : pcvm5-16.instageni.ku.gpeni.net
	OVS VM : pcvm1-34.genirack.nyu.edu
	HOST_1 VM : pc1.genirack.nyu.edu (port 41531)
	HOST_2 VM : pc1.genirack.nyu.edu (port 41532)
