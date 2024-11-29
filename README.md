# Smart Load Protection and Management System

This project demonstrates how to use an ESP32 microcontroller to monitor key electrical parameters and control loads remotely via a Firebase Realtime Database. Designed as a complete IoT solution, it ensures safe energy usage, prevents overloading, and facilitates real-time load management.

---

## Project Overview

The system continuously monitors parameters such as temperature, voltage (maximum and minimum), and current (maximum and minimum). These values are sent to a Firebase Realtime Database, which updates in real time and displays data on a web dashboard. A load (represented by an LED) can also be controlled via the same web interface, ensuring seamless interaction between the user and the hardware.

### Features
- **Real-Time Data Monitoring**: Displays temperature, voltage, and current values in real-time.
- **Load Control**: Allows remote toggling of an LED to simulate load control.
- **Firebase Integration**: Synchronizes data to and from Firebase for real-time updates.
- **User-Friendly Web Dashboard**: A responsive and interactive interface for monitoring and control.

---

## Hardware Requirements
- ESP32 Development Board  
- Sensors for temperature, voltage, and current measurements  
- LED (to simulate a load)  
- USB Cable (for programming and power)  
- Access to a Wi-Fi network  

---

## Software Requirements
- Arduino IDE  
- Firebase Realtime Database  
- Firebase ESP32 Client Library  
- Web technologies: HTML, CSS, JavaScript  

---

## Firebase Setup

1. **Create a Firebase Project**:  
   - Visit the [Firebase Console](https://console.firebase.google.com/).  
   - Create a new project and enable the Realtime Database.

2. **Database Configuration**:  
   - Note down the database URL (e.g., `https://your-project.firebaseio.com/`).  
   - Generate an API key from the project settings.

3. **Database Rules**:  
   - Set up rules to allow read and write access for testing:  
     ```json
     {
       "rules": {
         ".read": true,
         ".write": true
       }
     }
     ```

4. **Install Firebase Library**:  
   - Use the Arduino Library Manager to install the Firebase ESP32 Client Library.

---

## Code Explanation

### Configuration
- Update the Firebase credentials, Wi-Fi SSID, and password in the code.  

### Data Monitoring
The ESP32 collects the following parameters and updates Firebase:  
- **Temperature**: Sensor readings from the temperature module.  
- **Vmax/Vmin**: Maximum and minimum voltage values.  
- **Imax/Imin**: Maximum and minimum current values.

### Load Control
An LED (representing a load) can be toggled via the web interface. The LED status is synced with Firebase and updated on the webpage in real time.

---

## How to Run the Project

1. **Clone the Repository**:  
   ```bash
   git clone https://github.com/your-username/smart-load-protection.git
   ```

2. **Set Up Firebase**:  
   - Configure the Firebase project and update the credentials in the code.

3. **Upload the ESP32 Code**:  
   - Open the `.ino` file in Arduino IDE and upload it to the ESP32.

4. **Host the Web Dashboard**:  
   - Open the `index.html` file in a browser or host it using services like Firebase Hosting or GitHub Pages.

5. **Monitor and Control**:  
   - View real-time updates of parameters on the web dashboard.  
   - Toggle the LED using the provided button.

---

## Web Interface

The web dashboard is built with HTML, CSS, and JavaScript. It uses Firebase SDK to dynamically display and control data. Key sections include:  
- **Parameter Monitoring**: Displays temperature, voltage, and current.  
- **LED Control**: Toggle button to turn the LED (load) ON or OFF.

### Hosting Options
- **GitHub Pages**  
- **Firebase Hosting**  
- **Netlify**  

---


## Future Improvements

1. Integrate additional sensors (e.g., energy consumption or power factor).  
2. Add data visualization charts for better insights.  
3. Implement authentication for database access.  
4. Send notifications for overloading or critical conditions.  
5. Create a mobile app for remote monitoring and control.

---

## License
This project is licensed under the MIT License. Feel free to use, modify, and distribute it.

---

## Acknowledgments
- Firebase ESP32 Client Library by Mobizt.  
- ESP32 documentation for IoT implementations.  
- Firebase for providing a reliable database solution.

---

Start contributing and explore the possibilities of IoT with Firebase!
