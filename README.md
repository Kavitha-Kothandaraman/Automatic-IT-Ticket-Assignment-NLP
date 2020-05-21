# Automatic-IT-Ticket-Assignment-NLP
To build an AI-based classifier model to assign the tickets to right functional groups by analyzing the given description
# Understanding the Business
In any IT industry, Incident Management plays an important role in delivering quality support to customers. An incident ticket is created by various groups of people within the organization to resolve an issue as quickly as possible based on its severity. Whenever an incident is created, it reaches the Service desk team and then it gets assigned to the respective teams to work on the incident.

The Service Desk team (L1/L2) will perform basic analysis on the user's requirement, identify the issue based on given descriptions and assign it to the respective teams.

The manual assignment of these incidents might have below disadvantages: More resource usage and expenses. Human errors - Incidents get assigned to the wrong assignment groups Delay in assigning the tickets More resolution times If a particular ticket takes more time in analysis, other productive tasks get affected for the Service Desk If this ticket assignment is automated, it can be more cost-effective, less resolution time and the Service Desk team can focus on other productive tasks.
# Objective
Our objective here is to build an AI-based classifier model to assign the tickets to right functional groups by analysing the given description with an accuracy of at least 85%.

Dataset - https://drive.google.com/open?id=143R3O0o3s3YyC2ZAoVDZOWM1APiNtGPA
# Steps followed
Text in Description is pre-processed by removing unwanted characters and words. Some descriptions are given in other languages which are translated to english internally. Stop words are removed and all the words are lemmatized.

With this pre-processed description the words in the corpus are tokenized and embeddings were created with word2vec. Embedding was also generated with glove.

Different NLP algorithms were tried out - RNN, LSTM, GRU, Traditional ML algorithms such as RandomForest and SVM were tried out.
# Limitations
As part of Data pre-processing, we had grouped all assignment groups with less than 10 entries as one group (misc_grp) which had reduced the Target class from 74 to 50 groups. While applying this model in the real world there could be additional intervention required to classify the tickets if it has been classified as misc_grp by our model. Since the number of elements reported under misc_grp are less, we expect this intervention to be done less often.
# Conclusion
Although this model can classify the IT tickets with 91.24% accuracy, to achieve better accuracy in the real world it would be good if the business can collect additional data around 300 records for each group.
