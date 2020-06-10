#### Kaggle profile
https://www.kaggle.com/jmithani

#### Competition of interest
The [Spooky Author Identification](https://www.kaggle.com/c/spooky-author-identification) competition challenges players to create a classification algorithm to predict which famous horror author wrote a given snippet of text. I was drawn to this because of its subject matter – I love work in the digital humanities and applying computational methods to literature. To participate, players need to train their algorithm on the provided training set, apply the algorithm to the test data, and return a CSV file with the probability that each sentence belongs to HP Lovecraft, Edgar Allen Poe, and Mary Shelley. Each sentence has only one match, and each submission is evaluated by its multi-class log loss.

#### Look through a recent issue of a journal in your field. Find a paper that you think could have been reformulated as a human computation project. How would you formulate the data collection as a human computation project? How might this improve the study?

#### In the InfluenzaNet project a volunteer panel of people report the incidence, prevalence, and health seeking behavior related to influenza-like-illness (ILI) (Tilston et al. 2010; Noort et al. 2015).
##### Compare and contrast the design, costs, and likely errors in InfluenzaNet, Google Flu Trends, and traditional influenza tracking systems.
All three systems rely on varying levels of human effort: Google Flu Trends passively collects data from someone searching for keywords; InfluenzaNet requires a patient to know what symptoms are so they can accurately report them when they occur; and traditional tracking systems depend on patients seeing a physician when they are ill. Traditional systems require a patient making an appointment to see a doctor, while GFT and InfluenzaNet both take their samples from people with access to computers. As such, cities and affluent areas are more likely to be represented in data collection.

GFT has the potential to overpredict in times of heightened awareness, and Google suggesting similar search terms (i.e. other symptoms) can introduce a large amount of noise to they system. It does, however, provide an immediate, accurate overview of the state of IFI at any given time. GFT requires working with Google, who can change their structure of algorithm at any time. Google Search is also a blackbox algorithm, so human interpretability is always somewhat out of grasp.

InfluenzaNet provides more information about specific cases than GFT, and is tied to a unique person who can be tracked season after season. It does require aggressive recruiting efforts and a certain level of education for participants; researchers need to be able to trust that participants are reporting and recognizing their symptoms accurately. There is more overhead in InfluenzaNet, both in terms of software creation and maintenance and the educational materials that need to be made in order to ensure validity of the system.

Last, traditional influenza tracking systems have the advantage of relying on the clinician’s expert diagnosis but depend on people making appointments to see their doctor. Numbers could be predicted from this, but there is no one model that will work for every community. 

##### Consider an unsettled time, such as the swine flu outbreak. Describe the possible errors in each system.
Google Flu Trends could over-predict based on people searching for information about a pandemic, or a heightened sense of hypochondria. In fact, this is true for all three systems – people making more appointments for the doctor because they think they are ill, InfluenzaNet participants over-reporting or inaccurately evaluating their symptoms. 
