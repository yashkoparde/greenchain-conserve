# GreenChain Conserve: Smart Waste Management System

## Project Overview

GreenChain Conserve is an innovative IoT-based smart waste management system designed to track waste disposal, optimize collection, and facilitate resource allocation. It leverages a smart bin equipped with sensors to monitor waste levels and an integrated platform for data management and processing.

## Key Features

*   **Smart Waste Bins**: IoT-enabled bins with ultrasonic sensors detect waste levels and human interaction.
*   **Real-time Event Tracking**: Records `OPEN` and `CLOSE` events when waste is deposited, along with distance measurements.
*   **Backend API**: A robust Node.js backend with Express.js and MongoDB to ingest, store, and retrieve waste event data.
*   **Processor Portal**: A frontend dashboard for waste processors to view aggregate waste metrics, manage inventory, and submit demand requests for waste materials.
*   **Data Synchronization**: Enables synchronization of waste data across the platform.

## Architecture

The GreenChain Conserve system is composed of three main components:

1.  **ESP32 Smart Bin (Hardware)**: An ESP32 microcontroller connected to an ultrasonic sensor. It detects objects (e.g., a hand) near the bin opening, measures the distance, and sends `OPEN` and `CLOSE` events to the backend API via Wi-Fi.
2.  **Backend Server (Node.js)**: Built with Express.js, this server acts as the central hub for data. It receives events from the ESP32 devices, stores them in a MongoDB database, and provides API endpoints for retrieving waste data.
3.  **Frontend Portals (React)**: User interfaces developed with React, Vite, and TypeScript. Currently, a 
Processor Portal exists, allowing users to interact with the system's data.

### Technology Stack

**Backend:**

*   **Node.js**: JavaScript runtime environment.
*   **Express.js**: Web application framework for Node.js.
*   **MongoDB**: NoSQL database for storing waste event data.
*   **Mongoose**: ODM (Object Data Modeling) library for MongoDB and Node.js.
*   **CORS**: Middleware for enabling Cross-Origin Resource Sharing.
*   **Dotenv**: Module to load environment variables from a `.env` file.

**Frontend:**

*   **React**: JavaScript library for building user interfaces.
*   **Vite**: Fast frontend build tool.
*   **TypeScript**: Superset of JavaScript that adds static typing.
*   **Framer Motion**: Animation library for React.
*   **Lucide React**: Icon library.

**Hardware/Firmware:**

*   **ESP32**: Microcontroller for the smart bin.
*   **Ultrasonic Sensor**: Measures distance to detect waste and human interaction.
*   **Arduino IDE**: Used for programming the ESP32.

## Getting Started

### Prerequisites

*   Node.js (LTS version recommended)
*   MongoDB instance (local or cloud-hosted)
*   Arduino IDE (for ESP32 development)
*   ESP32 board
*   Ultrasonic sensor (HC-SR04 or similar)

### Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/amantebriwal4321/greenchain-conserve.git
    cd greenchain-conserve
    ```

2.  **Backend Setup:**

    ```bash
    cd backend
    npm install
    ```

    Create a `.env` file in the `backend` directory and add your MongoDB URI:

    ```
    MONGO_URI=your_mongodb_connection_string
    PORT=5000
    ```

    To start the backend server:

    ```bash
    npm start
    ```

3.  **Frontend Setup (Processor Portal example):**

    ```bash
    cd ../frontend/Processor-Portal
    npm install
    npm run dev
    ```

    The frontend application will typically run on `http://localhost:5173` (or another port specified by Vite).

4.  **ESP32 Firmware Setup:**

    *   Open `sketch_feb1a.ino` in the Arduino IDE.
    *   Update `ssid`, `password`, and `serverUrl` variables with your Wi-Fi credentials and the IP address/port of your backend server.
    *   Upload the sketch to your ESP32 board.

## Usage

Once all components are set up:

*   The ESP32 smart bin will detect waste events and send data to the backend.
*   The backend will store this data in MongoDB.
*   The Processor Portal will display real-time metrics and allow for interaction with the waste data.

## Contributing

Contributions are welcome! Please feel free to fork the repository, create a new branch, and submit pull requests.

## License

This project is licensed under the ISC License.

## Contact

For any questions or inquiries, please contact [amantebriwal4321](https://github.com/amantebriwal4321).
