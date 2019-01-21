Introduction to Artificial Intelligence (AI) - Course Notes
============
January 2019
Chris Cameron

I am auditing [Microsoft Professional Program for Artificial Intelligence track](https://academy.microsoft.com/en-us/tracks/artificial-intelligence/).

The first of 10 courses is [Introduction to Artificial Intelligence (AI)](https://courses.edx.org/courses/course-v1:Microsoft+DAT263x+1T2019/course/) as part of

# Introduction

The only thing to install at the outset seems to be Python 3.6+ and Jupyter notebooks. Anaconda Python distribution is recommended.

## Before You Start

***Anaconda Python***

I Tracked down the docker images for Anaconda Python which is the preferred method of getting setup (Anaconda, not Docker - I prefer Docker)

- [miniconda3](https://hub.docker.com/r/continuumio/miniconda3)
- [anaconda3](https://hub.docker.com/r/continuumio/anaconda3)

got them locally using, e.g., `docker pull continuumio/miniconda3` as usual

Here are some copied usage instructions for miniconda3

`docker run -i -t continuumio/miniconda3 /bin/bash`

or

1. `docker run -i -t -p 8888:8888 continuumio/miniconda3 /bin/bash -c "/opt/conda/bin/conda install jupyter -y --quiet && mkdir /opt/notebooks && /opt/conda/bin/jupyter notebook --notebook-dir=/opt/notebooks --ip='0.0.0.0' --port=8888 --no-browser"`
2. You can then view the Jupyter Notebook by opening `http://localhost:8888` in your browser, or `http://<DOCKER-MACHINE-IP>:8888` if you are using a Docker Machine VM.

The instructions for anaconda3 are similar.

Basically I chose to use conda3 (the package manager) because then I can just choose to use parts of the anaconda distribution instead of the whole shebang at once ([see here for explanation of diff between miniconda and anaconda](https://stackoverflow.com/questions/45421163/anaconda-vs-miniconda/45421527#45421527))

Based on a GH issue in continuumio/docker-images I modified the above instructions to use `--ip='0.0.0.0'` instead of `--ip='*'`. Submitted a pull request [here](https://github.com/ContinuumIO/docker-images/pull/111).

Next thing I had to do was add `--allow-root` to the end of the `jupyter` command

So then it runs and you get some output telling you what URL to follow to open up Jupyter in your browser (use the ipv4 address at 127.0.0.1).

In a separate terminal I also started messing around using `docker exec -it goofy_shtern bash` (goofy_shterm was just the garbage name Docker gave to the container run in the `docker run` command - I should probably change the dockerfile to give it a name). I tried commands like `conda update`, `python --version` and `conda list` to make sure everything was hunkey dorey (it was).

# Machine Learning

## Machine Learning Fundamentals

### What is Machine Learning?

You have historical data (x) trying to predict a value (y). The historical data are often called records, cases, observations. They have a numerical characteristic. ML is calculating Y from X.

Supervised ML starts with observations that include known values for y, called labels. Since you started with data that includes the label, you can train the model with only some of the historical data, and withhold the rest, and then validate the model by comparing the value predicted by the function to the actual label value that you knew.

Unsupervised ML does not have labels. The model is trained by finding similarities between the observations. Once trained, each new observation is assigned to the cluster of observations with the most similar characterestics.

### Regression

He referred to the data as "features" this time, in the context of someone exercising, their age, weight, heart rate, duration, etc. The label in this case (y) is calories burned.

The job is to get an algorithm that learns what function operates on all of the features (x1, x2, x3) such that it predicts y correctly. So if the label is 231, you'd want  f(x1,x2,x3,...) = 231

Gather data from diverse participants (lots of x) and train the model on that data. Now you havea  generalized function f(x...)=y you can plot values of Y calculated for specific features of X values, you can interpolate new values of X to predict an unknown Y.

Since the data had a label you were trying to predict (supervised ML) you can train the model with only some of the data to evaluate its performance. Then you can use the model to predict f(x...) =y and compare the predictions (scored labels) to the (actual) labels.

The difference between predicted and actual = residual. You can measuer error using this.

Absolute ways:
- RMSE
- Mean absolute error

RMSE=5 means stddev of error is 5 calories (for the exerciser example). it's absolute in the sense of absolute units of Y I think.

Relative ways:
- Relative absolute error
- Relative squared error

These are scaled 0 to 1, with values closer to 0 meaning a better model (

- Coefficient of Determination (R-Squared)

This is scaled 0 to 1, with values closer to 1 meaning a better model.

###  Classification

Trying to categorize /classify something. A binary classifier applies an f(x) that ends up with y=0 or 1.

Usually it actually calculates a real number between 0..1 and you use a threshold to push it to 0 or 1.

Classification is a supervised learning technique, so you have to withhold some data to validate it.

predicted Y and actual Y are 1 => true positive
predicted Y and actual Y are 0 => true negative
predicted Y is 1 / actual Y is 0 => false positive
predicted Y is 0 / actual Y is 1 => false negative

Choosing a threshold value is important to deciding  which classification something gets into. Moving the threshold changes predictions. Maybe it's better to have false positives than false negatives, you can adjust it to be like that (e.g., let's say a positive result means a person has diabetes, better to be wrong about having it than being wrong about NOT having diabetes)

Confusion Matrix - predicted vs actual in a table 2x2 of values.

e.g.,

|p\a| 1 | 0 |
|---|---|---|
| 1 | 5 | 2 |
|---|---|---|
| 0 | 0 | 4 |
|---|---|---|

Metrics
- accuracy = number of correctly classified cases / total cases
  - Not super useful (gives an example about diabetics being 3% of population. you can make a 97% accurate model by just saying nobody has diabetes)
  - from matrix = (9/11) = 81.8% accurate
- precision = number of true positive / (true positive + false positive)
  - from matrix = (5/(5+2)) = 5/7 = 71.4% precise
- recall = number of true positive / (true positive + false negative)
  - from matrix = (5/(5+0)) = 5/5 = 100%
  - in the diabetes example this means we are correctly identifying all patients with diabetes, even though we said some had diabetes but they did not have it, we never said someone DIDNT have diabetes but they DID have it.

Recall is also known as the True Positive Rate
Similarly FP Rate = FP / (FP + TN)

You can plot True Positive Rate (TPR) against the False Positive Rate (FPR) on a chart. The chart is called Receiver Operator Characteristic (ROC) chart. The area under the curve (AUC) is an indication of how well the model predicts (under different thresholds- you have to adjust the threshold value to get different values of TPR vs FPR).

You want a large as possible AUC with the curve being as close to top left corner as possible (TPR is graphed increasing Y axis, FPR increasing X axis in the chart). Remember the values of each go from 0..1 so a perfect AUC would be 1. You can compare your AUC with that of a diagonal line which is a fifty fifty guess (AUC=0.5).

The model presented had an accuracy of 0.9, so you know it's at least out-performing guessing (lol - yay for ML)

### Clustering

Now we're going to talk about unsupervised learning

k-means clustering

plotting multiple features in n-dimensional space (e.g., x1, x2, x3, x4 plotted in 4 dimensions)

k is the number of clusters

plot k points at random locations that represent center points of our clusters. k=3, get 3 points or 3 center points for 3 clusters. then we identify which of the three centroids each point is closest to and assign them to clusters accordingly. Then we move each centroid to the true centroid of the points which were assigned to it.  then we reallocate the points in the cluster based on their nearest centroid and repeat the process until we have nicely separated clusters

You want clusters that separate data by the greatest extent possible

Couple ways to measure this

- average distance between the cluster centers compared to the average distance of the points in the cluster and their centers
- average distance between the cluster centers compared to the maximum distance of the points in each cluster and their centers
- A third way is PCA (principal component analysis) or ellipse clustering like Pavel vasak was doing at MIRARCO.

PCA is how you decompose the points in a cluster into directions. The first two components of the PCA components are represented as an ellipse. The first PC is along direction of maximum variance or major axis of ellipse. The second PC is along the minor axis of the ellipse.

A cluster which is perfectly separate from the first cluster shows up as an ellipse with the major axis of that ellipse perpendicular to the first ellipse's major axis.

If the second cluster is quite poorly separated from the first, the major axis of both ellipses will be nearly colinear and the ellipse may be more like a circle if it is less defined.

## Azure Machine Learning Studio

### What is Azure Machine Learning Studio?

Azure Machine Learning is a cloud service in Azure

So he says to go provision  (in the Azure Dashboard) a new Machine Learning Workspace but it looks like it's called Machine Learning Studio Workspace now.

Once it's provisioned you can go to the workspace and open up "Machine Learning Studio". You need to sign in AGAIN.

You can have multiple workspaces associated with your account and all switchable via a dropdown at the top of the Studio webapp.

### Creating an Experiment

he's basically just explaining the studio interface, showing uploading data sets and then spelunking through them using the dataset tools

he adds a "Join Data" module and drags the left and right datasets into it. after that you have to explain how to join the data together (probably explain which column in one table links to a column in the other). you can add rules too

in the properties of the join, you can do things like choose kind of join (inner, left outer, etc). you can also omit one of the key columns so you don't end up with two columns of keys.

Then you need to "Run" the experiment which queues a job, then you see a green checkmark and then you can visualize the output of the join.

Then he uses a Convert to CSV thing from the join module. (this is basically a data pipeline tool, pretty cool). He right clicks the CSV and says Open Notebook in Python3 which opens up a thing that makes a Jupyter notebook (cool).

Some cells are then populated in the notebook which have Python code. You can run each cell and end up with some output in the notebook. Right now all it does is shows the CSV as a table of data.

He then plops in some code to create a plot with matplotlib and something called seaborn.  Makes a pair plot (scatter plot) when run. Gets warnings because matplotlib is being built

The PairGrid is output at first just as a code object but then soon it turns into a pile of charts (really cool)

It shows a correlation between weight and height, duration and body temperature (non-linear, more curvey), duration and calories. very cooooool.

### Creating a Regression Model

He added an Edit Metadata module to explain that the Gender column is a categorical variable

Then he did an Apply Math Operation taking duration and heart rate to create a new feature, so he's created duration^2 and heartrate^2

Then he did an Apply Math Operation on the calories label using a natural log function to make sure he doesn't predict any NEGATIVE calories. So all predictions will be log(calories) ensuring always positive values for calories

Then Normalize Data modules.  For bell curved ones he uses Disease Score normalization. For the non-normal distributions (age, duration, duration^2) he uses min-max version of normalization.

Then He does another Edit MEtadata so that user_id and calories don't get used as features.

Then He does a Split Data module to split them into two different sets (becaues this is supervised ML) and he holds back 30% of the data.output 1 goes to Train model , output 2 goes to Score model (so does the result of Train Model) . Train Model is given Linear Regression for its training.

After Score, he sends output to Evalute Model separately Apply Math operation to un-log the ln_calories column.

So he runs the thing and visualizes Score Model.

Then he visualizes Evaluate Model. shows mean absolute error, root mean squared, relative absolute, relative square error, CoD as described in previous videos.

Then he visualizes Apply Math Operation (the final one)

Not great predictions but they are at least getting near so he feels it's producing pretty good prediction for calorie burn. Personally I think it's kind of weak correlation.

### Creating a Classification Model

He joins a diabetes.csv with a doctors.csv , applies math, blah blah. I'll just describe what's new/interesting.

He finds age is skewed to youth so he maths out ln(Age) to make it less skewed looking.

Claims that Physician is not predictive but I think it would be useful to find out if some Physicians calculate diabetes better than others, or if a particular physician is a source of error.

New: Two-Class Boosted Decision (as input into Train Model, other than the Training Dataset itself). You are training a Classifier using a 2-class boosted trees algorithm ***(I should read about these)***.

 He visualizes evaluate dataset and looks at the RoC curve which is actually quite good looking. AUC is very high. He had 99 False Positives and 108 False Negatives but 1399 True Positives and 2894 TNs. AUC=99.1% so he's got a pretty decent model here.

### Creating a Clustering Model

***Note: He goes through these models quite quickly. Either they are dealt with more in-depth later on in the course or I should probably find some pre-requisite material that describes these models in theory***

The new thing appears to be using a `k-means clustering` module as input to `train clustering model` module. he didn't use split data this time so maybe this is unsupervised ML this time? I think so. He wants to see if he ends up with 3 clusters in the data. In the results dataset there's an Assignments column with values 1,2,3 based on which cluster it was assigned to.

His PCA results show ellipses. One is elongated, then he's got a small perpendicular one, but then a big circle. So it's not well-separated. He re-runs it with 2 clusters. This time they are roughly perpendicular , meaning (for his dataset) there may be 2 different types of people coming in to donate blood.

### Publishing a Predictive Web Service

He goes back to the diabetes classifier example.

First, run the experiment (presumably to make sure it builds) he hits "Set up Web Service" which creates a Predictive Experiment which opens up a separate tab in the Studio (the first was a Training Experiment) so he calls it Diabetes Predictor. It copied a lot from the other experiment, but now there's a  Web Service Input connected to the initial Join Data at the start (presumably so they can put in their own input data!)

Some Apply Transformations are added  which do what the original thing did. (he hand-waves over this a bit). The trained model is even brought in as an input before rendering results as well.

He then deletes the original diabetes.csv  input since it has labels in it and creates a "Enter Data Manually" module where he says it has to be CSV with a header, pastes in some sample data with the header and no label column this time (so I guess the Web Service Input *doesnt* imply manual data input).

After Score Model there's a Web Service Output module. Then he re-runs it with the test data and everything checks out. The client is going to get back the data from Score Model, so he puts in an Apply SQL Transformation between Score Model and Web Service Output and basically it changes it to return Patient ID, Physician and Scored Lables renamed to DiabetesPrediction and the Score Probability to just Probability. So clients only need those four columns back.

He can choose Deploy Web Service (classic) or Deploy Web Service (new) (he chooses new). Changes the generated name,picks a price plan (chooses the one we made earlier during provisioning of the azure ML workspace). Click Deploy

A fancy webapp is generated and he glosses over it calling toward the next video.

### Consuming a Predictive Web Service

So you can go to the Test page and enter values and do a request-response button press. Instead he goes to the Consume Tab/page.

It lists primary key, secondary key (authentication stuff) request-response (endpoint) and another one for batch requests (endpoint)

Shows a Sample Code section for doing this from Python, C# or R.

Apparently you can use this with Excel as well. So say you have Excel filled in with columns that match the input needed by the published web service. So he uses the Azure Machine Learning add-in (find it in the Microsoft Store (a button in the Excel ribbon).).

So he presses the button and he has to fill in the batch request endpoint in as the URL and then grabs either the primary or secondary key to put into the API Key box of the add-in panel. Then you click Add which adds the diabetes predictor service. I'm going to avoid writing any more notes about this excel crap.

Then he brings up the Microsoft Azure Notebooks service (separate from Azure and Machine Learning Workspace, it's in preview still, and it's basically a way to deal with Jupyter notebooks I think)

Creates a new library, gives it a unique URL, keeps it private. Creates a new notebook in Python 3.6. (\*.ipynb). Generates a notebook server (looks just like Jupyter but online instead of in my docker container locally)

Got some code which uses the URL and APi keys from the Consume page for machine learning services. pasted it into the notebook. goes and grab his api key separately. explains how the code works a bit. Basically it sends json up and gets json back and then outputs something.

He runs the code and gets back a json document (yay). Implies you can go ahead and build a custom application against it, then video ends.

## Lab!

I completed Exercise 1 and Exercise 2 so far in the downloaded Lab1 PDF. Basically just puttering around in ML Studio and Notebooks (their Azure one, not my local dockerized one). Used some diabetes datasets so far to do not too much of anything.

The lab finishes with showing you how to export the Python 3.6 code but doesn't even go as far as the video lectures do in getting charts visible in Jupyter (MS Azure Notebooks)

### Review Questions

As I have not yet paid for the "Verified Track" ($99USD) I can't actually take the review questions

# Language and Communication

## Getting Started with Text Processing

### Introduction to Text Analytics

blah

### Word Frequency

Pareto Chart

Short words like a, as, an are called "stop words" so they are removed from word frequency count

Loads Moon.txt into jupyter

He normalizes the text to get rid of numbers, punctuation, etc (but not stop words?)

introduces `nltk` library

`FreqDist()` function

Convert to a `DataFrame` and print it

Pareto cart - column chart with more frequent to the left

displays top 60 words. first couple of words are 'the' 'and' 'to' etc

nltk has a standard set of stop words so he'll use it to filter them out.

re-does the Pareto and now top words are 'new', 'space', 'science', 'go', 'moon' so it's a better indicator of the topic

### Term Frequency - Inverse Document Frequency

Term Frequency - the relative frequency of a term within a document i.e., (term instances / total terms).

Inverse Document Frequency - relative number of documents within which the term appears. calculated as the log of total documents divided by the number of documents containing them, i.e., log(docs/docs with term)

Multiply TF by IDF to work out the overall importance of each term to the documents they appear

Now he loads Gettysburg address and some microsoft cognitive services documentation as a 2nd and third document and he wants to calculate the top 3 words in the 3 documents he's loaded.

Talks about a lib called `textblob` that makes working with text easier apparently.

### Stemming

*Stemming* is a technique used to identify words with a common root (e.g., sweet, sweetness, sweeting) and count them as the same.

Common technique is *Porter algorithm* which defines a sequence of rules for breaking words down into a common stem based on the pattern of consonants, vowels, common letter combinations and word endings and other syntactical elements.

Loads kennedy's inaugural address into jupyter, normalizes, gets rid of stop words, gets freq distribution, plotted as pareto, blah blah.

`nltk` has a a `PorterStemmer`. he'll use that then get the frequency of the stems instead because the pareto chart shows a whole bunch of words that don't quite identify anything about the speech including `let` `us`` world` etc.

now *power* and *nation* are showing up more because of words like powerful, nations, national, etc.

### Sentiment Analysis

Analyze text to discern whether the writer is happy, unhappy, or neutral about something.

He loads 160,000 tweets, labeled 4=positive, 0=negative.

He's going to train a machine learning model, has a compiled list of stopwords and a python script which is similar to previous videos but loads the custom stopwords. goes through everything, uses the PorterStemmer, etc etc. Transforms 4 to 1 and 0 to -1 to normalize the labels.

Then he uses a FeatureHashing which does 2 n-gram hashing to indicate whether certain phrases are used (need to learn more about this). then he only uses the numeric output of that (text isn't needed anymore) and trains a Classification Model with 70% of the data and publishes the output as a predictor web service (to predict the sentiment of a new tweet based on the training data)

Loads it into excel and it's predicting sentiment as positive or negative pretty well (kind of cool!!)

## Introduction to Natural Language Processing (NLP)

### Text Analytics

moving from sentiment analysis we can use text analytics API to extract semantic meaning and sentiment from the text

text analytics API is considered to be a Cognitive service.

showing how to provision it from azure instead of cognitive services website (AI+ Cognitive Services category) in Azure "Text Analytics Service (preview)"

set name, sub, location, pricing tier (free tier) use euxisting resource group, confirm stuff click Create

There are Access Keys in the text API service / resource that you will need to authenticate to it from another app. the Keys you need to bring into your jupyter notebook in order to make use of the textAnalytics service (URI, textKey are what they're called here)

request header has to include the textKey (why don't they just call this api key?) URI is the one to your specific instance of the text service

request body is the documents he wanst to parse (gettysburg and the MS document from previous lecture)

calling the `keyPhrases` method of the ApI so text/analytics/v2.0 API

get back a JSON document with a collection of documents which will have a document ID and then a list of the key phrases found in the document.

For the first one he gets things like 'new nation', 'great civil war', 'great battlefield', etc so it's informational.

For the second he gets 'speech developers', 'microsoft cognitive services', 'vision recognition', 'set of APIs', etc

Next example will be sentiment analysis.

So he calls the `sentiment` method this time. The score is normalized 0-1 so you can set a threshold yourself like 0.5 and below is negative, above is positive.

Document 1 comes back as positive (gettysburg address) and Document 2 comes back as negative (the documentation, lol)

### Speech Service

To work with Speech there are two models that need to work together

1. An acoustic model that maps audio to sound units or phonemes, which define how specific word fragments are pronounced in a given language
2. Then there's a language model that provides a probability distribution across a sequence of words

Shows  a seque;nce of phonemes which could easily be misinterpreted as "This cherries ferry come for table" but it's actually "This chair is very comfortable"

Back to Azure portal to make a Speech Service resource.

You need the region and access key (why no special URI this time?)

He's going to use Python and its REST interface

Loads a wav file to do speech-to-text first example

"The rain in Spain stays mainly in the plain" is the sound

To use this service you have to get an Access Token that is valid for 10 minutes. (in addition to the key and region from beforeA)

set up headers with the access token, content type (audio/wav), codec, sample rate, etc)

paramaters have language English US.

you get a json document back with text trasncribed from the audio sent up.

In this case the response came back as expected

Now he wants to see text-to-speech.

You have to pass up an XML document this time to the TTS service that explains everything you want like language, voice type (English US Female) and some text.

He runs it and it asks him to enter text "Peter Piper picked a peck of pickled peppers" and it's returned as speech correctly.

### Translation

Microsoft Translator API. Two different services, one for text, one for speech.

Demos text cuz it's easier.

Still need to initially get an access token for ten minutes expiry then a second call to do the actual translation.

you have to set the source language and the destination language.

He sends up some text in EN  and gets it back as FR for French.

### Real World AI - Skype Translator in the Classroom

Skype Propaganda showing two kids speaking to each other with delayed translations in their native language benig provided by skype. so cute yaaay (yes it's cool too)

## Language Understanding Intelligent Service

### What is LUIS

It's a service for responding to human communications.

Yaou interact with it through `utterances`, or fragments of language that need to be interpreted and from these utterances, LUIS identifies the most likely `intent/goal/action`. You could map some speech to "Book Flight" as an intent, for example.

### Creating a LUIS app

He provisions an app called "Home Automation" in "English" with a description hits done and creates it.

He creates some Intents from the intent tab. He creates a "Light On" intent.

He has a loaded "utterance" that says "switch the light off". (it's just text)

He highlight the word "Light" and can call it an entity. He creates a new Entity called "Light", type Simple.

Creates a "Light Off" intent, enters the utterance (says off isntead of on at the end) and highlights "Light" to use the existing Light Entity.

Now he's going to Train the app. Opens a test window and types an utterance to see which Intent comes out (Light On comes back). He also tries "Turn the light on" and it comes back with Light On Intent again even though the utterance is a bit different.

Now he tries to publish it to production, basically just a bunch of boring Azure stuff

### Consuming a LUIS app

Consumes it from jupyter again. has some code that takes in a text command, then calls the service via URI and tokens and whatnot, and then gets back the intent in the json document.

Then he'll display a particular image depending on if the intent is Light On, Light Off, or neither.

### Improving a LUIS app

Active Learning - how you can get your service to improve over time (learn new utterances, interpret them correctly)

he tries "turn out the light" and the app can't identify the right intent

He goes back tot he build tab of his luis app. which shows endpoint utterances. He clicks the result it got and re-links it to the Light Off intent, and then he clicks Train to retrain it, tests it with the test button and tries "put out the light" which goes to "Light Off" with 55% confidence instead of nothing.

he then re-publishes to production and tries again from Python and he gets the Light Off picture. Neat.

### Real World AI - Starship Commander

More propaganda. Could be a neat game.

## Lab

This time the lab is in a jupyter notebook instead of the PDF. Sweet.

I should learn about `pandas`, `nltk` libraries separately.

Man sometimes their jupyter instance is a POS. Run cell fails to do anything a lot, no progress to see.

I am skipping everyhting until it says `Using the Text Analytics Cognitive Service` because this lab isn't a lab until then it's just "Press run cell and observe" so far.

In "Create Bing Speech Service" it says to create a 'Bing Speech' resource but it looks like it's been renamed 'Speech' in the Azure portal since the lab was made.

Well, of course this means later you install "SpeechRecognition" package which apparently supports the Bing Speech API but since that's changed to Speech service now the credentials won't validate when trying to transcribe audio

See https://github.com/Uberi/speech_recognition/issues/385

Looks like the [PR for it](https://github.com/Uberi/speech_recognition/pull/389/files) hasn't been merged yet, so i'm just going to move on. it was demo'd in the video just fine anyway.

AHh shit, this affects the last example in the Lab as well when you combined Speech and LUIS. It's basically just the LUIS example being fed results from the speech transcription so no biggie.

# Computer Vision

## Getting Started with Image Processing

### Image Processing Basics

talks about PIL and matplotlib.pyplot

opens an images as a numpy array

I would hardly call this "Image Processing Basics"

### Equalization

talks about cumulative distribution functions (CDF)

For image processing you usually want an equalized image so there isn't too much crazy contrast differences.

Diagonal line going up towards the right is equalized perfectly.

he does a histogram of his profile shot showing an uneven distribution of grayscale values

then he does a CDF of it and gets a not quite diagonal rise in slope, it's a hill

he re-runs the image through an hist_eq function, and gets a histogram that's less spiky and is more equal in values, and his CDF is more or less a diagonal line going up to the right (filled underneath too)

Shitty - he didn't even really show an eq() algorithm :(

### Filters

images have noise, obscuring features

talks about gaussian filter to de-noise an image

gauss blur the image because it averages out all areas of the image, even contrasting sections

median filter applies the median value instead of an average, so doesn't look blurry

he goes to jupyter and adds random_noise() to his image. then tries gaussian and median to show the result (from scipy.ndimage.fliters) *god damn he pronounced scipy "Sky Pie"*

### Edge Detectors

Sobel edge detection
- applies two masks, one for vertical, the other for horizontal
- it only reallyl works properly on grayscale
- you can calculate a magnitude by adding the two masks together and using hypot() function, then normalize
- you end up with a grayscale image where white is an edge and black is not an edge

### Corner Detection

Harris algorithm for corner detection. hand-waves about its implementation, but mentions you can get implementations anywhere.
- works by putting a square "patch" around an area and determines if the average intensity goes down sharply when you move horizontally and vertically
- even detects things like eyes in a face

## Working with Images and Video

### Image Classification (Custom Vision)

customvision.ai is another microsoft cognitive service

makes a new project in customvision.ai projects page. you can choose your azure sub or a "limited trial" separate from that (he chooses the trial). picks Classification / Multiclass / Food

adds 9 pictures of carrots. adds `carrot` as a tag to associate with those photos. the carrots have different colours and orientations. then he adds pictures of apples of various colours and shapes , specifies `apple` tag and uploads.then 

then he hits the green Train button which creates a new iteration. apparently it is well trained with 100% precision and recall. makes it the default iteration so that when a web service calls into this, it uses this trained model as the default

goes to settings gear, sees the keys and endpoints he needs. since it's already trained you need the prediction key and endpoint. jumps to jupyter and installs an SDK designed to work with the custom vision service (hopefully this doesn't fail later in the lab like the other one...). plugs in the key and endpoint, and project id

has two test images in the code which are an apple and a carrot (not in the original sample, i assume)

and tada, the apple is tagged apple with 99.86% and carrot is tagged carrot with 99.97%

### Image Analysis

### Face Detection and Recognition

### Video Basics

### The Video Indexer

### The Video Indexer API

### Real World AI - Seeing AI

Propaganda time

## Lab

# Conversation as a Platform

## Introduction to Bots

## Building Intelligent Bots

## Lab

# Learning More

## Beyond the Basics

## Where Do I Go from Here?



