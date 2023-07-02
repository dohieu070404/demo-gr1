
Monitoring and Controlling Smart Home sensors using Arduino with Web-App dashboard
====================================

                                            Winter 2023

Instructor - Stephen Chiong

Created By:-

*   Prathmesh Gujar
*   Simon Chauke
*   Ashish Gujral


Statement of problem
====================

We live in a world where things like house chores, security assurance, and even making coffee can be done by smart home devices. Our project delivers such solutions to the world that make it a more convenient place and help people focus on more important things by saving time.

However, from the tech perspective, smart home app development may be a challenging task:

*   Choosing data protocol BLE, Wi-Fi or another protocol?
*   How to connect several devices within one application?
*   Possibility of 3rd-party services integration like Google Home or Alexa?

Our team designed and developed the home automation system using the ESP-32 microcontroller, various electronic components, and a web-app that connected to the ESP-32 microcontroller via wifi. The developed system automated lights, temperature monitoring and fan control, soil moisture monitoring and irrigation control, and movement monitoring.

Significance of Study
=====================

The “SyncHome” research project is significant for several reasons:

1.  Affordable and Customizable Solution: The developed home automation system provides an affordable and customizable solution for homeowners to automate their homes.
2.  Energy and Water Conservation: The system enables homeowners to monitor and control their energy and water consumption, leading to energy and water conservation.
3.  Increased Convenience: The home automation system provides increased convenience to homeowners by allowing them to control their home appliances remotely through the web-app.
4.  Contribution to the Field: The project contributes to the field of home automation by providing a low-cost and customizable solution that can be easily replicated and adapted to meet individual needs.

Project Implementation
======================

Objectives
----------

The main objectives of this project were as follows:

1.  To design and develop an affordable and customizable home automation system using ESP-32 microcontroller.
2.  To automate lights, temperature monitoring and fan control, soil moisture monitoring and irrigation control, and movement monitoring.
3.  To create a user-friendly web-app for easy access and control of the home automation system.
4.  To evaluate the effectiveness and efficiency of the developed home automation system.

Proof of Progress
-----------------

Our team has made significant progress toward achieving its objectives. The following features/modules have been developed and implemented:

1.  ESP-32 microcontroller and Electronics components: The team has successfully designed and assembled the hardware system using ESP-32 microcontroller and various electronics components to automate lights, temperature monitoring and fan control, soil moisture monitoring and irrigation control, and movement monitoring. This module addresses objective 1.

![](images/image7.png)

Figure 1: Modelling LED’s circuit using TinkerCad.

2.  Web-App: The team has developed a full-stack web-app for easy access and control of the home automation system using MERN. The web-app allows users to register and login to access the automation controls. The web-app includes a dashboard with principal sensor control switches. The extended sensor controls and stats can be accessed by navigating to the specific sensor pages. This module addresses objective 3.

![](images/image6.png)

Figure 2: Web-app dashboard early prototype.

![](images/image3.png)

Figure 3: Temperature monitoring and AC control page.

3.  REST API: The team has developed and implemented REST API to enable easy and efficient communication between the web-app and the ESP-32 microcontroller. The REST API allows the web-app to send and receive data from the ESP-32 microcontroller in a predefined format. This module addresses objective 2.

4.  Sensor Data Collection: The team has developed and implemented sensor data collection modules to collect data from various sensors connected to the ESP-32 microcontroller, such as temperature sensors, humidity sensors, and light sensors. The collected data is formatted as JSON and sent back to the web-app using REST API, which stores it in the MongoDB Cloud Atlas. This module addresses objective 2.

![](images/image4.png)

Figure 4: User collection saved in MongoDB cloud.

Project Setup
=============

Circuit Design
--------------

Early circuits were designed using TinkerCAD. The circuit design is shown in the diagram below:

![](images/image5.jpg)

Figure 5: Circuit Design for the DC Motor.

Firmware Setup
--------------

It is critical to get familiar with the working and implementation of each electronics/ hardware component before assembling and programming. The team used the following firmware in the project:

1.  ESP-32 microcontroller: The ESP-32 is a microcontroller that can be used as a web server to connect with web apps and send sensor data using REST API via wifi.
2.  DHT22 sensor: The DHT22 is a basic, low-cost digital temperature and humidity sensor. It uses a capacitive humidity sensor and a thermistor to measure the surrounding air’s humidity and temperature.
3.  DC Motor: DC Motor or direct current motor is an electrical machine that transforms electrical energy into mechanical energy by creating a magnetic field that is powered by direct current. A DC motor is controlled using L298N Motor Driver. The direction and speed of a DC motor is determined by how we provide power to it.
4.  LED: A light-emitting diode (LED) is a semiconductor device that emits light when current flows through it. Electrons in the semiconductor recombine with electron holes, releasing energy in the form of photons.
5.  PIR Motion Sensor: The working principle of this sensor is based on the change of the infrared radiation on the moving object. If an object is emitting the infrared ray but not moving, it is NOT detected by the sensor. If an object is moving but not emitting the infrared ray, it is NOT detected by the sensor. Animals and humans emit infrared rays naturally. Therefore, the animals and humans can be detected by the sensor if they are moving.
6.  Resistive Soil Moisture Sensor: A resistive soil moisture sensor works by using the relationship between electrical resistance and water content to gauge the moisture levels of the soil. You’ll observe these sensors to possess two exposed probes that are inserted directly into the soil sample.

To set up the Firmware, follow the circuit design provided in the above section. Connect ESP-32 to your computer using micro-usb data transfer cable. Clone the Arduino Sketch from github: https://github.com/prathmesh300346562/synchome.git 

, then edit the wifi name and password fields in the code to allow wifi access, finally, use Arduino-IDE to upload the Sketch to ESP-32. You will see the notifications showing IP address upon successful execution of Sketch.

Firmware setup is completed, electronic components are ready to use.

Web-app Setup
-------------

The ESP-32 web server needs to be set up separately and connected to the local network for the SyncHome web app to communicate with it. Please refer to the Firmware section for setup instructions.

In order to run this application locally, you must have node installed on your computer. To check if you already have it installed, enter node -v in your terminal.

Once you have confirmed that node is installed, cd into a folder on your computer and run the following command to clone the repository:

git clone https://github.com/prathmesh300346562/synchome.git

Then cd into the root folder and open it in your code editor. For Visual Studio Code:

 cd  synchome

Next, install all of the required dependencies for both the backend folder and the frontend folder. cd into the backendfolder and run npm install .

To run frontend execute npm run dev. This should build and run the frontend locally  on [http://localhost:5173/](https://www.google.com/url?q=http://localhost:5173/&sa=D&source=editors&ust=1688333078539600&usg=AOvVaw1zO1AnLALhRkBmljwl99oX).

Then return to the backend folder and run npm install again. Execute npm start to run the backend. This should start the app’s server. We are not using any env variables to keep things simple. The server should connect to database with confirmation shown in the console.

You should see a login/register screen with form. Register to create a new account. Login with your newly created account to see the dashboard with welcome message and control switches.

Software Design Architecture
============================

The software design architecture of the SyncHome web-app and ESP-32 web server can be explained as follows:

The front-end of the SyncHome web-app is built using React, a JavaScript library for building user interfaces. The React components render the web-app's UI and handle user interactions such as registering, logging-in and controlling home automation. The front-end components communicate with the back-end through REST API calls.

The back-end of the SyncHome web-app is built using Node.js and Express.js. The Express.js middleware handles incoming REST API requests from the front-end and communicates with the MongoDB database to retrieve and store data. The back-end also communicates with the ESP-32 web server through REST API calls to control home automation.

The SyncHome web-app uses MongoDB, a NoSQL database, to store user data, home automation settings, and sensor data. MongoDB provides a flexible and scalable solution to store and retrieve data efficiently.

Insert uml diagram here

![](images/image2.png)

The ESP-32 microcontroller acts as a web server and is responsible for receiving REST API requests from the SyncHome web-app, controlling the electronics components, and sending sensor data back to the web-app. The ESP-32 web server is programmed using Arduino IDE and uses the ESP-32's built-in wifi module to communicate with the web-app.

The SyncHome web-app and ESP-32 web server communicate with each other using REST API calls. The web-app sends REST API requests to the back-end to retrieve and store data, while the ESP-32 web server sends REST API requests to the back-end to control home automation settings and send sensor data.

Overall, the SyncHome web-app and ESP-32 web server software design architecture leverage the MERN stack to create a scalable, efficient, and user-friendly home automation solution. The front-end, back-end, database, and ESP-32 web server work together to enable home automation, store and retrieve data, and provide a seamless user experience.

![](images/image1.png)

Figure: Software Architecture Design for the project.

Testing
=======

The software testing phase is critical to ensure that the web-app and ESP-32 web server function as expected. The testing was done manually by the team members. The software testing process for the SyncHome project included Integration tests, Functional tests, and Performance testing. The testing process ensured that the SyncHome project worked correctly and met the project objectives. All tests passed successfully, indicating that the SyncHome project is ready for real world application.

Integration tests were performed to test the interaction between the various components of the SyncHome project. The integration tests covered the interaction between the front-end, back-end, database, and ESP-32 web server. We have used state lifting techniques in Reactjs such as Context API to preserve and share the App states on all pages. The integration tests ensured that the components could communicate with each other correctly, and the data was transferred without errors.

Functional tests were performed to test the individual functions of the SyncHome web-app and ESP-32 web server. The functional tests included testing the registration and login functionality, controlling home automation using API’s, and retrieving sensor data. The functional tests ensured that the SyncHome project's features worked correctly.

Performance testing was performed to test the SyncHome project's ability to handle a large number of sensor data. The performance testing included testing the web-app's response time, ESP-32 web server's ability to handle sensor data, and the database's ability to store and retrieve data efficiently. Using multiple sensors together was creating time delay during runtime. To solve this issue, we have incorporated parallel programming in ESP-32 for lag free execution. The performance testing ensured that the SyncHome project could handle a high volume of sensor data and met the project objectives.

Unfortunately, the SyncHome project did not involve survey testing therefore we don't have feedback from users to evaluate the usability, user experience, and overall satisfaction of a product or service. However, this should not affect our project as its primary focus is on functionality rather than usability.

Moreover, testing performed by the team members might introduce bias into the testing process. To mitigate such bias, the team tried to involve external testers whenever possible to provide additional perspectives and feedback. However, it is essential to acknowledge that bias due to testing performed by the team members might still exist to some extent.

Project Setup on another machine
================================

The process of Project setup on another machine is similar to the last section. Therefore,  follow the instructions in the previous section.

Takeaways/Conclusion
====================

Smart home software development is a complex process and requires patience and teamwork so that everything functions seamlessly.

This Research Project challenged us to expand our knowledge beyond the technologies learnt during our academic career as we explored tools such as arduino esp-32 microcontroller and electronics circuit design. It served as an excellent opportunity to break out of our comfort zone to develop skills such as:

*   Programming the ESP-32 microcontroller using Arduino IDE to implement the web server, REST API, and sensor data collection.
*   Sourcing of electronic components.
*   Working with UI libraries such as Material UI, and ChartJs. Working with backend libraries like node-fetch and multer.

Workload Distribution
=====================

Workload distribution was fair and equally distributed.

*   Simon: Dashboard design, Frontend Development and API integration.
*   Ashish: Frontend Development and UI, Data visualisation, and App State Management.
*   Prathmesh: Circuit design and Research , ESP-32 programming, and Backend Development.

Citations
=========

1.  Material-UI: https://mui.com/material-ui/getting-started/installation/
2.  ChartJS: https://www.chartjs.org/
3.  ESP-32: https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html
4.  Arduino-IDE: https://www.arduino.cc/en/software
5.  Context API and use Reducer: https://javascript.plainenglish.io/react-auth-hook-context-api-and-usereducer-8567a2ef0d89
