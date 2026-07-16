# Fingerprint Gender Classifier 

Welcome to the **Fingerprint Gender Classifier** project! This is an AI-powered program designed to look at a fingerprint image and predict whether it belongs to a male or a female. 

This repository contains the code and steps for **Milestone 1** (downloading, cleaning, and preparing raw fingerprint images for machine learning).

---

## ⚙️ How the Data was Prepared

Raw images cannot go straight into a machine learning model, so we cleaned them using Python:

1. **Found the Labels:** We read the gender (Male or Female) directly from the names of the image files (for example, finding "M" or "F" in `1__M_Left_index.BMP`). We changed these to numbers: **0 for Male and 1 for Female**.
2. **Fixed Color and Size:** We turned all images into black-and-white (grayscale) and resized them to **96x96 pixels** so they are all exactly the same size.
3. **Scaled the Numbers:** We divided all pixel values by 255.0 to scale them between **0.0 and 1.0**. This helps the AI model learn much faster.
4. **Split the Data:** We kept **80% of the data for training** the model and saved **20% for testing** it later. This keeps our testing fair.
5. **Saved the Output:** We saved the finished, clean data into a compressed file called `socofing_gender_preprocessed.npz`.

---

## Part 1: Setting up the Dataset (Our "Database")

This project does not require a complex SQL database. Instead, it uses the **SOCOFing (Sokoto Coventry Fingerprint)** dataset containing 6,000 images. 

You have two simple ways to set it up:

### Option A: Automatic Setup (Recommended)
Our Python code has a library called `kagglehub` built right into it. When you run the notebook, it will **automatically download and configure** the dataset folder for you behind the scenes!

### Option B: Manual Setup (If running completely offline)
1. Download the dataset files manually from [Kaggle — SOCOFing](https://www.kaggle.com/datasets/ruizgara/socofing).
2. Extract the downloaded ZIP file.
3. Place the `SOCOFing` folder directly inside your project directory like this:
   ```text
   fingerprint-gender-classification/
   ├── SOCOFing/
   │   └── Real/  <-- This contains your 6,000 .BMP images
   └── fingerprint_gender_classification.ipynb