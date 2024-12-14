# Real-Time Location Tracker

This project is a **Real-Time Location Tracker** built using **Node.js**, **Socket.IO**, **Express**, and **Leaflet.js**. The application allows multiple users to share their live geolocation data, which is displayed on an interactive map.

---
## LiveURL
https://realtime-location-tracker-igdv.onrender.com

## Features

1. **Real-Time Location Updates**:
   - Users can share their current location using the browser's geolocation API.
   - All active users' locations are displayed on a shared map.

2. **Interactive Map**:
   - A map powered by **Leaflet.js** displays users' locations in real-time.

3. **Multi-User Support**:
   - Handles multiple clients, displaying each user's location with markers on the map.

4. **Dynamic Marker Management**:
   - Automatically adds markers for new users and removes them when users disconnect.

---

## Tech Stack

- **Backend**:
  - Node.js
  - Express
  - Socket.IO

- **Frontend**:
  - EJS (Embedded JavaScript Templates)
  - Leaflet.js (Interactive Map Library)
  - HTML/CSS

- **Other Libraries**:
  - Geolocation API (Browser)

---

## Setup Instructions

### Prerequisites
- Node.js (v16 or later)
- npm (Node Package Manager)

### Steps
1. **Clone the Repository**:
   ```bash
   git clone git@github.com:ArpitRautela/Realtime-Location-Tracker.git
   cd Realtime-Location-Tracker
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   ```

3. **Run the Server**:
   ```bash
   npm start
   ```

4. **Access the Application**:
   - Open your browser and navigate to: `http://localhost:3000`

---

## Project Structure
```
.
├── public
│   ├── css
│   │   └── style.css    # Styles for the application
│   └── js
│       └── script.js    # Client-side JavaScript for geolocation and map updates
├── views
│   └── index.ejs        # HTML template for the main page
├── app.js               # Main server file
├── package.json         # Project dependencies
└── README.md            # Project documentation
```

---

## How It Works

### Backend Workflow
1. The **server** is built using **Express** and listens for WebSocket connections using **Socket.IO**.
2. When a client connects:
   - The server logs the connection and listens for location updates (`send-location` event).
3. On receiving a location update:
   - The server broadcasts the location to all connected clients (`receive-location` event).
4. When a client disconnects:
   - The server informs other clients to remove the corresponding marker.

### Frontend Workflow
1. The client uses the **Geolocation API** to fetch the user's current location.
2. The location is sent to the server using a WebSocket connection.
3. The **Leaflet.js** map dynamically updates with new markers or adjusts existing ones based on the location data received.
4. When a user disconnects, their marker is removed from the map.

---

## Key Files

1. **app.js**:
   - Main server logic for managing WebSocket connections and broadcasting location data.

2. **public/js/script.js**:
   - Handles client-side geolocation and sends location updates to the server.
   - Updates the map with markers based on the received data.

3. **views/index.ejs**:
   - Serves the HTML layout for the application.

---

## Deployment
1. **Environment Variables**:
   - Set `PORT` to specify a custom port (default is 3000).

2. **Run in Production**:
   - Use a process manager like **PM2** or deploy to platforms like **Heroku** or **AWS**.

---

## Screenshots
### Real-Time Map View
![Screenshot 2024-12-14 032101](https://github.com/user-attachments/assets/30f8082a-35cc-46ff-af5c-9c770e33a953)
![WhatsApp Image 2024-12-14 at 12 48 43_de27821b](https://github.com/user-attachments/assets/31c888a8-afac-4566-9a0e-a8954d4a3fd4)

---

## Future Enhancements
1. **User Authentication**:
   - Add authentication for better user management.
2. **Custom Avatars**:
   - Display user-specific avatars on the map.
3. **Mobile App Integration**:
   - Extend functionality to mobile platforms.

---


