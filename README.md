# Social-Distancing
Social distance application that detects people and measures the distance between them. If this distance is less than a value previously provided by the user, then an alert is triggered.

## Pre Requisites
1. Intel OpenVino
2. Python
3. Cmake
4. Visual Studio

### Installation Instructions

Kindly refer to https://docs.openvinotoolkit.org/latest/openvino_docs_install_guides_installing_openvino_windows.html

### Getting Started

1. Navigate to <Installation Directory>\Intel\openvino_2021.4.582\bin using command prompt (CMD) and initialise the environment variables.
2. Enter the following in the CMD
  
   cd C:\Program Files (x86)\Intel\openvino_2021.4.582\inference_engine\demos
  
   and run build_demos_msvc.bat file.

3. cd <Installation Directory>\Intel\openvino_2021.4.582\deployment_tools\tools\model_downloader
4. Download the two models using the following commands
  
    python downloader.py --name person-detection-retail-0013 -o (specify the output path.)
  
    python downloader.py --name person-reidentification-retail-0288 -o (specify the output path.)
  
5. cd C:\Users\<username>\Documents\Intel\OpenVINO\omz_demos_build\intel64\Release
  
  Copy the downloaded models from FP 32 into the release folder.s
  Copy the test video file into the release folder as well
  ![image](https://user-images.githubusercontent.com/80956623/133461793-585f2b74-8603-4744-95ea-de91bef1cb98.png)

6. Finally enter the following command
  
  social_distance_demo.exe -i sample.mp4 -m_det person-detection-retail-0013.xml -m_reid person-reidentification-retail-0288.xml
## Output sample

  ![image](https://user-images.githubusercontent.com/80956623/133463374-76543ef7-f835-4084-a915-a5bfadc607ff.png)
### Note
1. Use
  
    social_distance_demo.exe -h
  
  for usage instructions.
  
2. If CMD is closed the varibles are lost and have setupvars.bat is needed to ran again.

3. Use 
  
    social_distance_demo.exe -i 0 -m_det person-detection-retail-0013.xml -m_reid person-reidentification-retail-0288.xml
  
    to use webcam feed as the input for this program.
4. 
