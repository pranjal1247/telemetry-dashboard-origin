# Nationwide Telemetry Grid Dashboard

A real-time telemetry dashboard built with [Next.js](https://nextjs.org) and React. This application visualizes live sensor data coming from distributed telemetry nodes across the country. 

## Features

- **Live MQTT Integration**: Connects to a public HiveMQ broker via WebSockets to ingest real-time data streams.
- **AES-128 Decryption**: Ensures data integrity and security by decrypting AES-128 (ECB mode) encrypted payloads on the fly.
- **Interactive Map Visualization**: Maps telemetry nodes onto a geographical grid (India) based on their latitude and longitude coordinates.
- **Real-Time Node Metrics**: Displays node statistics including:
  - Precise GPS or static location
  - Temperature & Humidity readings
  - Node IP address
  - Last sync timestamps
- **RF Channel Crowd Analysis**: Provides a detailed histogram visualization of Radio Frequency (RF) channel noise levels across 126 channels (2.4 GHz to 2.52 GHz), aiding in wireless spectrum analysis.
- **Responsive UI**: Built with Tailwind CSS, featuring an intuitive, dark-themed, and responsive interface with micro-animations.

## Technology Stack

- **Framework**: Next.js (React)
- **Styling**: Tailwind CSS
- **Messaging**: MQTT (`mqtt` library)
- **Cryptography**: `crypto-js` for AES decryption
- **TypeScript**: Typed structures for robust data handling

## Getting Started

### Prerequisites

- Node.js (v18 or higher recommended)
- npm, yarn, pnpm, or bun

### Installation

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run the development server:
   ```bash
   npm run dev
   ```

3. Open [http://localhost:3000](http://localhost:3000) with your browser to see the live dashboard.

## How it works

The dashboard subscribes to the MQTT topic `Pbtx/Grp_4/#` on the HiveMQ public broker. It receives AES-encrypted JSON payloads, decrypts them using a predefined shared key, and dynamically updates the React state to reflect the nodes' status and RF metrics on the geographical UI.
 
