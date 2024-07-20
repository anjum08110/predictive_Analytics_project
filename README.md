
# Predictive Analysis Final Project

This guide helps convert Labelstudio export and video data into YOLO training data, train a YOLO model, and validate it using uploaded videos.

---

## System Requirements

### Windows Setup (similar for Linux, without WSL addition)

1. *Install Visual Studio Code*
   - Download from [Visual Studio Code](https://code.visualstudio.com/Download)

2. *Install WSL and Upgrade to Version 2*
   - Follow [WSL Installation Guide](https://learn.microsoft.com/de-de/windows/wsl/install)

3. *Install FFmpeg on Windows*
   - Instructions available [here](https://www.geeksforgeeks.org/how-to-install-ffmpeg-on-windows/)

4. *Install WSL Extension in Visual Studio Code*
   - Follow the [VS Code WSL Extension Guide](https://code.visualstudio.com/docs/remote/wsl)

5. *Open Ubuntu Console*
   - Open via PowerShell dropdown or type ubuntu in console

   
6. *Install FFmpeg on Linux*
   
   sudo apt install ffmpeg

7. *Clone the project* 
   git clone https://github.com/anjum08110/predictive_Analytics_project.git

8. *Create and Activate Virtual Environment*
   - Follow the [Virtual Environments Guide](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)
   python3 -m venv .venv
   source .venv/bin/activate
   

9. *Upgrade pip*
    python3 -m pip install --upgrade pip
    python3 -m pip --version
   

10. *Install Requirements*
    
    pip install -r requirements.txt
    

11. *Open Project in VS Code*
    code .
    

---

## Creating YOLO Data Yourself

1. *Delete Current YOLO Model if Exists*
   - Remove files like yolov8n.pt

2. *Create New Folder for Framed Data*
   - Name it something like frames

3. *Run Script to Create YOLO Dataset*
   - python 1_frames.py -l <Path-of-1A_anjum_data.json> -v <Path-of-anjum_video> -o <Path-of-the-framed-output-folder> 
   

4. *Edit Dataset Path in Ultralytics Configuration*
   - Open settings.yaml in /home/.config/Ultralytics
   - Reference your newly created folder based on settings.yaml
   - Change your 2A_data.yaml according to your data

5. *Train YOLO Model*
   - python 2_train_yolo.py
   

6. *Validate YOLO Model*
   - python3 3_yolo_inference.py <Path-of-the-anjum_vedio> -m n -t detect -p
   
7. *Access the Video*
  - Navigate to the file "anjum_video_output.mp4" 
  - Open the file "anjum_video_output.mp4" in VLC Player
  - You can see the labeled data in the video


8. *The link to the output Video*
   - https://label.aitools.starwit-infra.de/projects/9/data?tab=10



By following this detailed guide, you can set up your environment, create and train YOLO datasets, and validate the model using your videos. Make sure to adjust file paths and names as needed for your specific setup.
