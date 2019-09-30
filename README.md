
<img src="img/rcattlogo.png" alt="rcATT logo">

<p align="center">Reports Classification by Adversarial Tactics and Techniques</p>

<p align="center"><img src="https://img.shields.io/badge/made%20with-python-blue.svg" alt="made with python">   <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="license MIT">    <!--<img src="https://img.shields.io/github/release-date/ValLGY/rcATT" alt="release date">--></p>

A python tool to predict Att&ck tactics and techniques from cyber threat reports.

## Usage

This tool is designed to predict tactics and techniques from the ATT&CK framework (https://attack.mitre.org/) in cyber threat reports, such as the ones that can be linked in https://otx.alienvault.com/ or https://exchange.xforce.ibmcloud.com/.

rcATT is useable either by a command-line interface or a graphical interface. Both versions have the same functionalities:
<ul>
  <li>predict tactics and techniques from a given cyber threat reports in a text format</li>
  <li>order and visualize the confidence of the classifier for each techniques and tactics, even the one predicted as non-included in the report</li>
  <li>save results in a json file in a STIX format</li>
  <li>give feedbacks to the tool by modifying the prediction to positive or negative</li>
  <li>save the feedbacks and/or the results to the training set</li>
  <li>retrain the classifier with new data</li>
</ul>


<p align="center"><img src="img/ExampleStix.jpg" alt="rcATT stix ouput" title="Example of output STIX file" height="350"><br>
Example of output STIX file</p>

## Installation
This tool requires:
<ul>
  <li>python >= 3.5</li>
  <li>joblib</li>
  <li>flask</li>
  <li>pandas</li>
  <li>pickle</li>
  <li>numpy</li>
  <li>stix2</li>
  <li>sklearn</li>
  <li>nltk, and the following packages:<ul><li>punkt</li><li>stopwords</li><li>wordnet</li></ul></li>
  <li>colorama</li>
</ul>
Then simply download the tool and run that app file with python.

## How to use rcATT
### Command-line interface
#### Predict tactics and techniques from a given cyber threat reports in a text format
For the command line tool, save your report in a text file. Then use the command : python -p -i [report in a text file]

The results will be displayed sorted by likelihood of presence.
<p align="center"><img src="img/rcATTcmd.jpg" alt="rcATT command-line help" height="350">
<img src="img/rcattcmdres.gif" alt="rcATT command-line results" height="350"></p>

#### Give feedbacks to the tool by modifying the prediction to positive or negative
Use the command line: python app.py -f [list of tactics and techniques] -i [input a result .json file generated by rcATT] -o [output .json file]

#### Save the feedbacks and/or the results to the training set
Use the command python app.py -a -i [.json file provided by rcATT]

#### Retrain the classifier with new data
Use the command python app.py -t

#### Save results in a json file in a STIX format
In the command-line version, this step is included in the prediction or the feedback functionalities by adding an -o [output json file] to the command given. Precise a name and a date using -n [title of the report] and -d [date of publication].

### Graphical interface
#### Predict tactics and techniques from a given cyber threat reports in a text format
Enter the report in the text area and click the "predict" button.
<p align="center"><img src="img/rcATTgui.jpg" alt="rcATT GUI" height="350"></p>

#### Give feedbacks to the tool by modifying the prediction to positive or negative
Click the "Correct the results" button.
<p align="center"><img src="img/rcattguichange.gif" alt="rcATT change results" height="350"></p>

#### Save the feedbacks and/or the results to the training set
Click the "Save the results for training" button.
#### Retrain the classifier with new data
Click the "&#9881;" button.

#### Save results in a json file in a STIX format
Click the "Export the results" button and fill in the form (if not filled in, default values will be given) 
<p align="center"><img src="img/rcATTgui2.jpg" alt="rcATT save in stix" height="350"></p>

## More details

This tool is the result of a Mater thesis on the prediction of tactics and techniques in cyber threat reports. You can find more details on this work in the following paper: [link to the paper]
