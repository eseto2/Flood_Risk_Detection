Flood Detection System

An AI-powered system for real-time water surface detection and water level estimation, designed to support flood monitoring and early warning applications.

OVERVIEW

This project focuses on detecting water regions and estimating water levels from video streams using a custom-trained deep learning model. The system combines computer vision, segmentation, and geometric analysis to produce real-time visual outputs and saved result videos.

It is suitable for applications such as:

Flood risk monitoring

Infrastructure safety analysis

Environmental surveillance

Smart city systems

TECHNICAL DESCRIPTION

In this project, I trained a YOLOv8n custom segmentation model using a combination of:

The Kaggle dataset:
https://www.kaggle.com/datasets/gvclsu/water-segmentation-dataset

Additional water annotations labeled manually with Roboflow

The trained model (best.pt) is included directly in this repository:
https://github.com/eseto2/Flood_Risk_Detection/blob/main/best.pt

The model detects water regions in images or video frames. To accurately estimate water level, the system requires a reference line defined by two coordinates perpendicular to the water surface.

This reference enables the system to calculate the vertical distance between the detected water surface and a known real-world measurement.

Technical diagram:
https://github.com/eseto2/Flood_Risk_Detection/blob/main/media/Front_Page.jpg

WATER LEVEL ESTIMATION INPUTS

To compute water level accurately, the following information must be provided:

Coordinates of the two endpoints of the reference line

Pixel-to-meter conversion ratio

Real-world height of the reference line

Threshold water level for triggering a warning

Once configured, the system:

Displays detection results in real time

Saves the processed output video locally

GETTING STARTED

REQUIREMENTS

Tested on:

Python 3.11.3

PIP 23.1.2

INSTALLATION

Navigate to your workspace directory and clone the repository:

git clone https://github.com/eseto2/Flood_Risk_Detection.git

Libraries used in this project:

Tkinter
https://docs.python.org/3/library/tkinter.html

Ultralytics and its requirements
https://ultralytics.com/

https://github.com/ultralytics/ultralytics/blob/main/requirements.txt

Shapely
https://shapely.readthedocs.io/en/stable/index.html

Install all required dependencies:

cd Flood-detection
pip install -r requirements.txt

RUNNING THE PROGRAM

You can run the program using your preferred IDE (VS Code, Jupyter Notebook, etc.) or directly from the command line:

python main.py

A GUI interface will launch to guide you through the setup and execution process.

GUI EXAMPLE

Once launched, the interface will appear as shown below:

https://github.com/eseto2/Flood_Risk_Detection/blob/main/media/GUI.JPG

Follow the GUI instructions carefully:

Enter the required parameters exactly as prompted

Select a video file from the media folder

OUTPUT EXAMPLE

Example output video:

https://github.com/eseto2/Flood_Risk_Detection/assets/16372230/defb4c22-a549-40b6-82e3-be5eebe6fad6

The resulting processed video will be saved automatically in the Flood-detection folder.

FUTURE IMPROVEMENTS

While functional, the system is still under development. Current limitations include:

The model performs best when only one water region appears per frame

Multiple water areas in a single image may reduce accuracy

Intersection calculations may fail if multiple intersections occur between the reference line and the segmentation mask

These issues will be addressed and improved in future updates.

AUTHOR

Ovuede Eseoghene
Email: eovuede97@gmail.com

LICENSE

This project is free to use, modify, and extend, provided that the YOLOv8 license is respected:

https://github.com/ultralytics/ultralytics/blob/main/LICENSE
