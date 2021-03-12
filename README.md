## Pipeline status ![](https://github.com/Virajdatt/Python_Docker/actions/workflows/main.yml/badge.svg)
Simple docker image for running a Flask App:-

The flask server serves a static html, which asks for an input sentece. The input sentence is then posted to the flask server and it creates a TextBlob object, of the input sentence and returns the sentiment polarity based on the words in the input sentence. 

The implementation can be seen in the New.py script.


We can create a docker image out of it using the command :
$docker build -t <name_of_image> . # . stands for the current directory

We can run the so created image using the command:
$docker run -d -P <name_of_image>

We can then check the mapping of port from host to container by running the command(under PORTS):
$docker ps 

In browser run localhost:5000 to get the following:-

## Front-End
![Front-End Image](/images/Front-End.png)

## Infernce
![Infernce Image](/images/Infernce-textblob.png)


This repo now has  github actions setup, the github actions do the following.

<ol>
<li>Copy the repo over to a remote Ubuntu Server, which has docker pre-installed</li>
<li>Build our docker image on the remote server</li>
<li>Spin up a docker container using the image built in above step</li>
<li>Test the container app with a curl get request on port 5000</li>
<li>NOTE:- This wont be hosting the app</li>

<li>NOTE:- The line 19 under /.github/workflows/main.yml enables one to skip the github actions if commit message has the string "ci skip"</li>
</ol>

# TO-DO
<ol>
<li>Imporve the frontend using CSS, javascript and anyother javascript frameworks.</li>
<li>Use a better backend for sentiment inference.</li>
<li>Include actions to deploy to a hosting platform.</li>
</ol>
</br>
**P.S:- The repo was built a couple of years ago when I was trying to learn flask, docker and used this
repo for taking notes.**
                                                                                  
