

<details open="open">
<summary>Table of Contents</summary>

- [About](#about)
   - [Project Overview](#project-overview)
   - [Learnings and Outcomes](#learnings-and-outcomes)
   - [Agile Methodology](#agile-methodology)
   - [Functional Features](#functional-features)
- [Framework and Services used](#framework-and-services-used)
- [Demo](#demo)
- [Workflow](#work-flow)
- [Getting Started](#getting-started)
  - [Setup](#setup)
  - [Deployment](#deployment)
- [Acknowledgements](#acknowledgement)
</details>

---

<table>
<tr>
<td>

# About
## Project Overview
This is a **MS Teams clone application** where users can communicate with each other via, ***one to one call*** and also ***group meetings*** which has features to *mute Audio/Video, Share screen and Chat*. This project is made as a part of submission in **Microsoft Engage 2021** mentorship program in a period of one month.

All the features and UI/UX has been developed from the scratch, using libraries and APIs, did not use any iframes and serviecs. A lot of effort has been made to build the project. 

## Learnings and Outcomes
I gained considerable exposure to the whereabouts of a live project.
This project has helped me develop an insight into the field of software development, from understanding the requirements to curate the best possible solution for the given problem statement to building a functional Web Application using [Agile Methodology.](#agile-methodology)

Being a beginner in Web Development, I learnt new languages, frameworks and worked on new platforms. I chose Nodejs for the backend as it is efficient, light weight and has a growing community, Reactjs for the UI/UX as it is fast, has rich user-interfaces and simple to use.

During the journey, I learnt from the leaders at Microsoft about, *Design Thinking*, *Agile Concepts*, and also got insights about great culture of Microsoft.


## Agile Methodology
The development of this project has been done using **Agile Methodology.**
Basicall I divided my time into 4-5 days Scrum Sprints wherein the each sprint focussed on 3 aspects: Feature Addition, UI/UX and bug fixing. So I developed the application working on backend and frontend simultaneously. Also I took suggestions and feedback from my mentors and used my application to communicate with my friends which helped me to getter a better idea of the bugs and other functional needs. 

## Functional Features
- One on One Call.
- Group Meetings.
- Chat feature.
- Audio and Video controls.
- User Authentication.
- Screen Sharing.

</td>
</tr>
</table>

# Demo
The Live website of the Teams Clone web application can be found [here](http://ms-team-clone.herokuapp.com/).
## Guide
- Sign-in/ Sign-up using a valid email-id and password which should be atleast 6 characters
- Allow the application to use your microphone and camera.
- You have reached the dashboard.
- Under the sub-heading  *Active Users* you can see the users which are logged in the app at the moment.
    - To setup a 1-1 call click on the user you want to call, a calling dialogue will appear if the user is available i.e. he is not in another call otherwise you will see that he is not available.
    - If the callee accepts your call you will enter the call, and video chat with him/her.
    - If the callee rejects your call you will see a dialogue that call rejected.
- In the bottom right section of your dashoard you will see the active meeting going on, to join a meeting click on the meeting, and enter.
- You can also create a new meeting by clicking on the create meeting button.
- You can Log-out of the application by pressing the Log-out button.


# Getting Started
## Setup
Follow these steps

- Install Nodejs in your computer. 
- Clone the repository.

  ``git clone https://github.com/MantavyaD/Microsoft-Engage-Mantavya.git``

- Open the server folder and in a terminal run :  `npm install`
- Run the command : `npm start` ,this will start the backend express server
- Open the frontend folder and in a terminal run :  `npm install`
- Run the command : `npm start` ,this will start the frontend react server

## Deployment 
The application is deployed to heroku. To deploy it:
- Create a new repository on Github.
- Create a new application on Heroku.
- Connect Heroku to Github and search for the repository
- Deploy Branch.


# Framework and Services Used
- **ReactJs.**: The front-end of the application is build on React.

- **express.js**:  Back-end web application framework for Node.js, our backend of the application is a express server.

- **peerJs**: PeerJS simplifies WebRTC peer-to-peer data, video, and audio calls and is used for managing group calls.

- **Cors**: Helps to connect the frontend to the backend.

- **Socket-io**: A javaScript library for realtime web applications used as the Signalling server.

- **Twilio**: Service which is used for TURN servers.

- **axios**: Library which is used to make requests to backend API, return TURN credentials from the API.

- **Firebase**: Used for User Authentication. 

- **socket-io-client**: Client side of the signalling server.


# Work Flow
The project uses WebRTC to eastablish peer connection with other peers with the help of socket.io, which acts as a signalling server and helps the browsers to communicate with servers.

<img src="Images\WebRTC-working.jpg" alt="Logo" width="600" height="350">
</br>

The process of setting up the call invloves the following steps:
### Exhachanging SDPs
- The caller calls RTCPeerConnection.createOffer() to create an offer with SDP
- The caller calls RTCPeerConnection.setLocalDescription() to set that offer as the local description
- The caller uses the signaling server to transmit the offer to the intended receiver of the call
- The recipient receives the offer and calls RTCPeerConnection.setRemoteDescription() to record it as the remote description
- The recipient then creates an answer by calling RTCPeerConnection.createAnswer()
- The recipient calls RTCPeerConnection.setLocalDescription(), passing in the created answer, to set the answer as its local description
- The recipient uses the signaling server to send the answer to the caller
- The caller receives the answer
- The caller calls RTCPeerConnection.setRemoteDescription() to set the answer as the remote description

### Exhachanging ICE Candidates
- Offer is created by the caller and set as local description (SDP)
- Caller asks STUN server to generate ICE candidates
- ICE candidates are received from STUN server and after setting local and remote description they can be exhchanged using signaling server
- Callee also ask STUN server to generate ICE candidates
- Both sides calls RTCPeerConnection.addIceCandidate(), when candidate will come through the signaling server.

<img src="Images\Workflow.jpg" alt="Logo" width="900" height="500">

# Acknowledgement
I would like to Microsoft to give me this opportunity.Also I would like thank my mentors who guided me in the journey and valuable feedbacks and suggestions.
