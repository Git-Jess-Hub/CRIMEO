# CRIMEO: CRIMinal behavioral patterns mining and extraction from VidEO contents
This repo contains the implementation of the extraction of criminal behaviour patterns from video frames by Frame Splitting using OpenCV and VideoCapture and the Object Detector Technique Yolov7.

# Pre-requisites
The project was developed using python 3.0 environment created on the Anaconda platform with the following packages. GPU is not required. The tests were performed on a machine with an Intel Core I7 CPU and 8 GB RAM, under Windows 10.<br />
&nbsp;  &nbsp;  •	pandas<br />
&nbsp;  &nbsp;  •	json<br />
&nbsp;  &nbsp;  •	opencv-python<br />
&nbsp;  &nbsp;  •	matplotlib<br />
&nbsp;  &nbsp;  •	kafka<br />
&nbsp;  &nbsp;  •	neo4j<br />
Installation with pip:<br />
&nbsp;  &nbsp;  •	pip install pandas<br />
&nbsp;  &nbsp;  •	pip install json<br />
&nbsp;  &nbsp;  •	!pip install opencv-python<br />
&nbsp;  &nbsp;  •	Pip install matplotlib<br />
&nbsp;  &nbsp;  •	pip install kafka-python<br />
&nbsp;  &nbsp;  •	pip install neo4j<br />
Software installation<br />
&nbsp;  &nbsp;  •	Anaconda: https://anaconda.org/ <br />
&nbsp;  &nbsp;  •	Kafka server 3.1.0: https://kafka.apache.org/downloads <br />
&nbsp;  &nbsp;  •	Neo4j:  https://neo4j.com/download/ <br />

Install yolov7.weights from this link: https://www.mediafire.com/file/ciborhbd48wq175/yolov7.weights/file and push it inside the folder Video Streaming after it is extracted.
   
# Dataset
We have got our data videos from iStock, an online royalty-free, international micro-stock photography provider based in Calgary, Alberta, Canada. This firm offers millions of videos related to Crime-Domain. https://www.istockphoto.com/search/2/film?excludenudity=false&phrase=woman%20knife%20attack 

# Approach
Step 1: Download the zip file code, and extract it <br />
Step 2: Go to “Kafka” folder, open three different “cmd” and run the following commands:<br />
&nbsp;  &nbsp; 1.	##Run zookeeper server## (bin\windows\zookeeper-server-start.bat config\zookeeper.properties)<br />
&nbsp;  &nbsp; 2.	##Run server## (bin\windows\kafka-server-start.bat config\server.properties)<br />
&nbsp;  &nbsp; 3.	##Create topic## (bin\windows\kafka-topics.bat --create --topic testOntology --bootstrap-server localhost:9092)<br />
Step 3: <br />
&nbsp;  &nbsp; 1.	Run neo4j and create project called “ontologytest” and click ‘start’ (here we work on default database “neo4j”)<br />
&nbsp;  &nbsp; 2.	Create our ontology by running the cypher queries in the file Ontology Cypher Queries.txt inside the Ontology Cypher Queries folder after extracting it<br />
Now, the nodes and relationship are created.<br />
Step 4: Go to anaconda and run our environment:<br />
&nbsp;  &nbsp; 1.	Open the consumer file consumer.ipynb and run it <br />
&nbsp;  &nbsp; 2.	Open the producer file producer.ipynb and run it <br />
Step 5: Go to neo4j again and we can apply our cypher queries, for example we can run this query:


![Screenshot (629)](https://user-images.githubusercontent.com/115569513/198700506-d94fc69b-472a-4512-b7ef-1bcc3d095fe8.png)
