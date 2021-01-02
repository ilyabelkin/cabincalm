# Project Title
**Cabin Calm - AI at the edge of the forest**

## Summary
"Cabin calm", the opposite of "cabin fever" is a final [Building AI course](https://buildingai.elementsofai.com/) project. In keeping with the spirit of the course, imagine you are one of the lucky mökki (a Finnish cabin) owners and would like to enjoy magical moments of being there even if you cannot visit in person. All without breaking the bank. And having a peace of mind about some undesired events and visitors.


## Background
![Mökki](https://upload.wikimedia.org/wikipedia/commons/9/98/Gamla_Hinkab%C3%B6le_februari_2008.png)

**Cabin Calm** attempts to solve the following problems:
* Cabins are usually seasonal and not being there 365 days a year means missing a lot of interesting moments. What if a deer decides to visit? Or a less wanted visitor like a bear?
* Remote surveillance comes with a high cost, and not just the equipment. It's often not economical to have unlimited Internet connection in rural and remote areas to receive images or view live video feed, and/or use Cloud-based AI
* There might be natural or artificial disasters that would require an emergency visit to complete repairs
* Owners may want to receive alerts about very specific events and visitors, and reduce the number of nuisance alarms
* Make trespassers aware they are being monitored, and even pretend the owner is at home


## How is it used?
* General-purpose surveillance camera is installed at a remote site, possibly powered by a renewable source of energy. The camera is set up to detect motion or line crossing, and send the images and video for further processing, e.g. by saving them to a network location, using FTP or Samba protocol
* Raspberry Pi 4B with or without accelerator hardware (Movidius, Coral or Kneron) could serve as the compute layer as well as NAS and use a general-purpose TensorFlow Lite models to analyze the audio-visual information
* Once an interesting object is detected, the system could either alert the owner immediately by a text message or textual email, or add the information to a daily digest ("today 1 bear, 2 deer and 53 squirrels have visited, and you've lost a tree, but it missed the cabin")
* If there is a damage to the property, or a trespasser detected, a more detailed email is sent and a webhook is invoked to trigger a critical alert, i.e. calling the owner
* In case of Internet connection problems, the system would send the alert as soon as the connection is restored, or record it as evidence
* If the camera has tracking capabilities, it could follow the intruder, and an audible alarm would sound to alert them of the surveillance
* If humans are detected, audio could also be processed and a transcript sent to the owner
* Why not pretend that the owner is at home and answer some questions that the visitor could have?
* There should be a way for the owner to request additional details based on the textual information received, either to receive the original media in full, or view the live feed
* There should be a way to tell the system of incorrectly recognized objects and eventually improve the accuracy


## Data sources and AI methods
* Supervised learning is used
* Image classification, natural language processing and other existing models could be used: https://www.tensorflow.org/lite/models
* The owner could help improve the detection further by telling the system about improperly recognized objects / speech in the specific environment


## Challenges
* At the very least, we need to reliably power the equipment and design the system to recover from possible failures
* Depending on the integration approach, separate camera and compute may introduce high latency
* Local laws might require certification of all the equipment by an electrical authority
* Like any technology, edge AI could be used to harm people, for mass surveillance or military purposes. My consolation is that Cabin Calm suite would not introduce anything radically new that could help advancing such applications


## What next?
* If you are a Developer, a cabin owner, or both, you're welcome to help
* Surveillance equipment designers and manufacturers are best suited to solve this kind of problems and profit; I'll be happy to take part in a joint project


## Licence
The goal is to use a permissive licence, but it will depend on the technologies used. TensorFlow, for example, is licensed under Apache: https://github.com/tensorflow/tensorflow/blob/master/LICENSE

## Acknowledgments

* The following picture is used without changes: [Gamla Hinkaböle Pyttis restaureringsarbete 2008 (Pyhtää) by Stahjo](https://commons.wikimedia.org/wiki/File:Gamla_Hinkab%C3%B6le_februari_2008.png#filelinks) / [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)

