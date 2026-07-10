# Noisy New York — On the Search for the Loudest Place

An investigative data analysis exploring New York City's 311 noise complaint patterns, focusing on vehicle noise and the distinct cultural soundscapes of Upper Manhattan.

**Live Project Link:** [https://cix77.github.io/Projekt1](https://cix77.github.io/Projekt1)

---

## How It Started & What I Learned
This project began with my very first personal impression of New York: the city is incredibly, painfully loud—louder than any other city I have ever experienced on this planet. I wanted to find out if this was just my subjective sensory overload as a newcomer, or if the actual data backed this up. 

**The main learnings:** 
* Yes, New York is objectively loud, and the official 311 complaint data confirms this feeling 100%. 
* Through this investigation, I also got to discover and learn about **Washington Heights**—a neighborhood with an incredibly vibrant, community-driven acoustic life that contrasts sharply with the city's corporate noise.

---

## Key Findings
* **Acoustic Standards:** New York City relies on maximum auditory signaling impact. For example, NYC fire truck sirens are legally permitted to hit 120 decibels—significantly higher than European urban limits like Zurich, which cap similar emergency sirens around 90 decibels.
* **The Music Factor:** According to citywide 311 data, loud music is by far the most frequent source of friction, making up roughly 45% of all registered noise complaints.
* **The Upper Manhattan Hotspot:** While major transportation hubs are inherently loud, the absolute density hotspot for residential noise complaints is located at the northern tip of Manhattan in Washington Heights and Inwood. 

---

## Design & Technical Struggles (What Didn't Work)
Being honest about the workflow, not everything went smoothly:
* **The Illustrator Trap:** I ended up spending way too much time wrestling with Adobe Illustrator trying to clean up, scale, and prep the visual assets. I easily spent way too many hours here instead of focusing on the code early on.
* **Failed Map Animation:** My original plan was to build a beautiful, fluidly animated map showing how complaints pop up over time. Unfortunately, after countless attempts and technical dead-ends, **the map animation just did not work out**. I had to pivot and accept static, clean SVG/PNG exports instead to keep the page functional and fast.

---

## Data Collection & Methodology

### 1. Data Sourcing
The primary dataset was pulled directly from the **NYC Open Data Portal** using the official 311 Service Requests API. 
* **API Endpoint Used:** `https://data.cityofnewyork.us/resource/erm2-nwe9.csv`
* **Filtering:** The queries were programmatically filtered to isolate `Complaint Type = 'Noise - Vehicle'` and general noise indicators to keep the dataset focused and manageable.

### 2. Data Analysis & Processing
The analysis was conducted using Python inside Jupyter Notebooks. The workflow involved:
* Using the `requests` library to fetch CSV streams directly from the live Socrata API.
* Utilizing `pandas` to clean missing data rows, handle empty coordinate fields (`latitude` and `longitude`), and calculate basic percentage distributions for complaint categories.
* Utilizing basic `matplotlib` functions like `plt.scatter` to plot raw coordinates to project the physical shape of NYC, and `plt.hexbin` to group coordinate clusters into localized density bins to find geographic hotspots.

---

## Technical Growth & New Skills
Despite the setbacks, this project allowed me to learn a lot of new concepts:
* **API Integration:** Learning how to structure API parameters directly within a Python script to request pre-filtered data rather than downloading multi-gigabyte raw files.
* **Programmatic Mapping:** Learning how to turn basic geographic coordinate data (lat/lon) into informative data visualizations using basic Python plot parameters.
* **Audio-Visual Web Controls:** Implementing custom, non-intrusive JavaScript triggers to allow users to manually play and mute ambient background tracks on the live article page.

---

## Repository Structure
* `/index.html` - The main web page styled with customized responsive layouts and scroll-animated charts.
* `/notebooks/projek1_sirens.ipynb` - Notebook handling the API data fetching, pandas cleaning, and basic data distributions.
* `/notebooks/02_plots_and_maps.ipynb` - Notebook containing the pure matplotlib and hexbin plotting logic used to generate the article graphics.
* `/.gitignore` - Prevents large tracking caches or local raw CSV outputs from cluttering the repository.
