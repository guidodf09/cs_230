# CS230 Fall 2024 Project: Transformer-based Surrogate Model for Subsurface Flow Simulation

This repository contains the code for the CS230 Fall 2024 project, focused on developing a deep learning-based surrogate model using transformers to predict subsurface fluid flow, specifically for water remediation from a non-aqueous phase liquid (NAPL) contaminant. The goal is to replace computationally expensive simulators with a surrogate model to speed up forecasting and decision-making in subsurface flow simulation.

## Problem Overview
The project involves using a simulation dataset created with the ADGPRS simulator, which predicts the flow of fluids through porous rock in subsurface environments. Given a series of geological parameters and historical well rates, the task is to predict the future rate of NAPL at production wells.

The dataset consists of simulation results with various geological properties, historical water rates, and well bottom-hole pressures (BHPs). The model uses these inputs to forecast future NAPL production at wells.

## Model Architecture
The deep learning model leverages the **Temporal Fusion Transformer (TFT)**, a state-of-the-art architecture for time series forecasting. The model is designed to handle both time series and high-dimensional static inputs (such as rock type maps and geological properties).

### Key Features:
- Combines static features (rock type maps, geological properties) and dynamic time series (historical well rates).
- Uses attention mechanisms to capture long-term dependencies and interactions between features.
- Probabilistic multi-horizon forecasting for better uncertainty estimation.

## Data
- **Inputs:** 
  - Rock type maps (2D grid of geological properties)
  - Historical well rates (time series)
  - Bottom-hole pressures (BHPs) for injection wells
- **Output:**
  - Future NAPL rates at production wells (time series)

The dataset consists of 3000 simulation results, each with 125 days of data split into 25 time steps (5-day increments).

You can download the dataset from the following folder:
[**Download Dataset**]([https://your-dataset-url.com](https://drive.google.com/drive/folders/1D-YGRyxuYXCYkTJBPbrxDju0t4iOdLRP?usp=sharing))

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/guidodf09/cs_230.git
   cd cs_230
