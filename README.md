# 🏫 Smart Campus Navigator

An intelligent campus navigation platform that combines **hierarchical A\*** pathfinding with **Machine Learning** to recommend not only the shortest route, but also the most suitable destination room based on predicted occupancy and usability.

Designed for the **FAST-NUCES Lahore Campus**, the system helps students avoid unnecessary walks to rooms that are noisy, occupied, or unsuitable for studying.

---

# ✨ Project Highlights

- 🧭 Hierarchical two-layer A* navigation
- 🤖 Machine Learning-based room usability prediction
- 📊 Timetable-driven occupancy analysis
- 📍 Interactive Streamlit web application
- 📈 Comparison between traditional and AI-assisted navigation

---

# 📖 Overview

Traditional navigation systems focus only on minimizing distance. While this finds the shortest route, it completely ignores whether the destination room is actually usable.

This project extends classical pathfinding by integrating a predictive Machine Learning model into the routing process.

The system:

- Models the FAST campus as a graph
- Calculates optimal paths using hierarchical A*
- Predicts room usability from timetable-derived features
- Adjusts route costs using ML predictions
- Recommends the best available destination instead of simply the nearest one

---

# ⚙️ System Workflow

The project follows five major stages:

### 1. Data Processing

University timetables are processed to generate structured datasets describing room schedules and occupancy.

### 2. Campus Graph Construction

Buildings, corridors, staircases, and inter-building connections are converted into weighted graphs suitable for A* search.

### 3. Machine Learning Pipeline

Multiple classification models are trained to estimate the probability that a room is suitable at a particular time.

The final implementation uses a tuned **Random Forest Classifier**.

### 4. Smart Navigation

Instead of optimizing only distance, the routing engine combines:

- Walking distance
- Predicted room usability
- Building congestion
- Nearby classroom activity

to generate intelligent recommendations.

### 5. Interactive Dashboard

A Streamlit application allows users to:

- Select source and destination
- Compare Pure A* and Smart Navigation
- View predicted room availability
- Validate predictions using timetable information

---

# 📂 Repository Structure

```text
Smart_Campus_Navigator/
│
├── Data/
├── Models/
├── Results/
├── Refrehers/
├── TimeTables/
├── Uni_diagrams/
├── University_Graph/
├── scripts/
│
├── config.py
├── EXECUTION_GUIDE.md
└── README.md
```

---

# 🚀 Getting Started

## Install dependencies

```bash
pip install pandas networkx plotly matplotlib openpyxl scikit-learn streamlit
```

## Launch the application

```bash
python -m streamlit run scripts/12_app.py
```

---

# 🧠 Machine Learning Component

The navigation engine introduces a **Smart Cost** function that combines path length with the predicted suitability of destination rooms.

Rather than directing users to the closest classroom, the algorithm prefers rooms that are expected to be quieter and available.

The prediction model considers factors such as:

- Time of day
- Day of the week
- Building congestion
- Adjacent classroom activity
- Historical timetable information

The selected Random Forest model achieved strong performance after hyperparameter tuning and was chosen over alternative baseline models.

---

# 🏛 Campus Representation

The campus is represented using a hierarchical graph structure.

- Buildings are connected through campus walkways.
- Rooms are connected by corridors.
- Floors are linked through staircases.
- Hierarchical A* combines both room-level and campus-level search to efficiently compute routes.

---

# 💻 Streamlit Application

The web interface provides:

- Interactive navigation
- AI-powered room recommendations
- Timetable validation
- Side-by-side comparison of Pure A* and Smart Navigation
- Easy visualization of predicted room availability

---

# 📚 Documentation

Additional documentation is included for understanding the implementation details, machine learning pipeline, and overall system architecture.

- `EXECUTION_GUIDE.md`
- `Refrehers/`

---

Developed for **FAST-NUCES Lahore Campus**
