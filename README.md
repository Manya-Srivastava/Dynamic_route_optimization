# Dynamic_route_optimization

## Overview
Dynamic Route Optimization is an AI-driven system designed to enhance urban public transport efficiency by predicting bus delays and optimizing routes in real-time. The project utilizes real-time traffic, weather, and GPS data to minimize congestion, reduce delays, and improve commuter experience.

## Features
- **Bus Delay Prediction**: Predicts delays using historical and real-time traffic, weather, and GPS data.
- **Real-time Route Optimization**: (Planned) Adjusts bus routes dynamically based on traffic and road conditions.
- **Data Integration**: Utilizes Open Transit API, OpenWeather API, and Google Maps API.
- **Visualization Dashboard**: Displays bus locations, traffic conditions, and optimization results.

## Model
The system is based on AI-driven predictive modeling and optimization techniques, leveraging historical and real-time data to enhance urban transportation efficiency. The model integrates:
- **Gradient Boosting** for delay predictions.
- **A\* Algorithm** for route optimization.

## Tech Stack
- **Programming Languages**: Python, JavaScript
- **Databases**: PostgreSQL
- **APIs**: Open Transit API, OpenWeather API, Google Maps API
- **Libraries & Frameworks**: Flask, NumPy, Pandas, TensorFlow, Matplotlib, Seaborn
- **Frontend**: HTML, CSS, JavaScript

## Database Schema
### Tables:
1. **busdata** (Static Data)
   - `bus_id`, `route_id`, `latitude`, `longitude`, `timestamp`, `destination`
2. **weatherdata** (Static Data)
   - `location`, `temperature`, `precipitation`, `wind_speed`, `timestamp`
3. **trafficdata** (Static Data)
   - `route_id`, `traffic_level`, `travel_time`, `timestamp`
4. **merged_dynamic_data** ( then, Processed Dynamic Data for Optimization)
   - Merges data from `busdata`, `weatherdata`, and `trafficdata` to provide optimized routes.

## Setup Instructions
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/dynamic-route-optimization.git
   cd dynamic-route-optimization
   ```
2. Set up a virtual environment (optional but recommended):
   ```bash
   python -m venv env
   source env/bin/activate   # On Windows: env\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up PostgreSQL database and configure credentials in `.env`.
5. Run the application:
   ```bash
   python app.py
   ```

## How to Access the Application
1. **Locally**: Once the application is running, open your browser and navigate to:
   ```
   http://localhost:5000
   ```
2. **Remotely**: If deployed on a cloud server (e.g., AWS, Heroku, or Render), use the provided URL:
   ```
   https://your-deployed-url.com
   ```

## Scheduling the Task
To automate route optimization and data fetching at regular intervals, use a task scheduler like **cron (Linux/macOS)** or **Task Scheduler (Windows)**.

### Using Cron (Linux/macOS)
1. Open the crontab editor:
   ```bash
   crontab -e
   ```
2. Add the following line to run the script every 10 minutes:
   ```
   */10 * * * * /usr/bin/python3 /path/to/script.py
   ```

### Using Task Scheduler (Windows)
1. Open Task Scheduler and create a new task.
2. Set the trigger to run every 10 minutes.
3. In the actions tab, choose "Start a Program" and set the path to `python.exe`.
4. In "Add Arguments," enter the script path: `C:\path\to\script.py`.

## Future Enhancements
- Implement **real-time route optimization**.
- Integrate **machine learning models** for enhanced prediction accuracy.
- Develop a **mobile-friendly interface** for better accessibility.

## License
This project is licensed under the MIT License.

