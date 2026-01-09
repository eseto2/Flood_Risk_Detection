=====================================================================
FLOOD DETECTION SYSTEM

An AI-powered system for real-time water surface detection and water
level estimation, designed to support flood monitoring and early
warning applications.

=====================================================================

OVERVIEW
=====================================================================

This project focuses on detecting water regions and estimating water
levels from video streams using a custom-trained deep learning model.
The system combines computer vision, segmentation, and geometric
analysis to produce real-time visual outputs and saved result videos.

Typical application areas include:

• Flood risk monitoring
• Infrastructure safety analysis
• Environmental surveillance
• Smart city systems

=====================================================================
2. TECHNICAL DESCRIPTION

This project uses a YOLOv8n custom segmentation model trained on a
combination of datasets:

• Kaggle Water Segmentation Dataset:
https://www.kaggle.com/datasets/gvclsu/water-segmentation-dataset

• Additional water annotations manually labeled using Roboflow

The trained model file (best.pt) is included in this repository:

https://github.com/eseto2/Flood_Risk_Detection/blob/main/best.pt

The model performs water region detection on images and video frames.
To estimate water level, the system relies on a reference line defined
by two coordinates perpendicular to the water surface.

This reference line enables accurate calculation of the vertical
distance between the detected water surface and a known real-world
measurement.

Technical overview diagram:

https://github.com/eseto2/Flood_Risk_Detection/blob/main/media/Front_Page.jpg

=====================================================================
3. WATER LEVEL ESTIMATION INPUTS

To compute water level accurately, the following inputs are required:

• Coordinates of the two endpoints of the reference line
• Pixel-to-meter conversion ratio
• Real-world height of the reference line
• Water level threshold for warning activation

Once configured, the system provides:

• Real-time visual detection output
• Automatic saving of the processed video locally

=====================================================================
4. GETTING STARTED
4.1 SYSTEM REQUIREMENTS

• Python version: 3.11.3
• PIP version: 23.1.2

4.2 INSTALLATION

Clone the repository to your workspace directory:

git clone https://github.com/eseto2/Flood_Risk_Detection.git

Libraries used in this project:

• Tkinter
https://docs.python.org/3/library/tkinter.html

• Ultralytics and required dependencies
https://ultralytics.com/

https://github.com/ultralytics/ultralytics/blob/main/requirements.txt

• Shapely
https://shapely.readthedocs.io/en/stable/index.html

Install all required dependencies:

cd Flood-detection
pip install -r requirements.txt

=====================================================================
5. RUNNING THE PROGRAM

The program can be executed using a preferred IDE (VS Code, Jupyter
Notebook, etc.) or directly from the command line:

python main.py

A graphical user interface (GUI) will launch to guide the user through
the configuration and execution process.

=====================================================================
6. GUI INTERFACE

Once launched, the GUI will appear as shown below:

https://github.com/eseto2/Flood_Risk_Detection/blob/main/media/GUI.JPG

Usage instructions:

• Enter all parameters exactly as indicated in the interface
• Select a video file from the media folder

=====================================================================
7. OUTPUT EXAMPLE

Example output video demonstrating system performance:

https://github.com/eseto2/Flood_Risk_Detection/assets/16372230/defb4c22-a549-40b6-82e3-be5eebe6fad6

The resulting processed video is automatically saved in the
Flood-detection folder.

=====================================================================
8. FUTURE IMPROVEMENTS

The system is functional but still under active development.
Current limitations include:

• Optimal performance is achieved when only one water region
appears per frame

• Detection accuracy may decrease when multiple water areas are
present in a single image

• Intersection calculations may fail if multiple intersections
occur between the reference line and the segmentation mask

These limitations will be addressed and improved in future updates.

=====================================================================
9. AUTHOR

Name: Ovuede Eseoghene
Email: eovuede97@gmail.com

=====================================================================
10. LICENSE

This project is free to use, modify, and extend, provided that the
YOLOv8 license is respected:

https://github.com/ultralytics/ultralytics/blob/main/LICENSE
