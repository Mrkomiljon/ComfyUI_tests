<details>
	<summary>Standalone (Portable) <a href="https://github.com/comfyanonymous/ComfyUI">ComfyUI</a> for Windows</summary>

1. Do the following:
   - Install [Visual Studio 2022](https://visualstudio.microsoft.com/downloads/) (Community version - you need this step to build Insightface)
   - OR only [VS C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/) and select "Desktop Development with C++" under "Workloads -> Desktop & Mobile"
   - OR if you don't want to install VS or VS C++ BT - follow [this steps (sec. I)](#insightfacebuild)
2. Choose between two options:
   - (ComfyUI Manager) Open ComfyUI Manager, click "Install Custom Nodes", type "ReActor" in the "Search" field and then click "Install". After ComfyUI will complete the process - please restart the Server.
   - (Manually) Go to `ComfyUI\custom_nodes`, open Console and run `git clone https://github.com/Gourieff/comfyui-reactor-node`
3. Go to `ComfyUI\custom_nodes\comfyui-reactor-node` and run `install.bat`
4. If you don't have the "face_yolov8m.pt" Ultralytics model - you can download it from the [Assets](https://huggingface.co/datasets/Gourieff/ReActor/blob/main/models/detection/bbox/face_yolov8m.pt) and put it into the "ComfyUI\models\ultralytics\bbox" directory
<br>
As well as one or both of "Sams" models from [here](https://huggingface.co/datasets/Gourieff/ReActor/tree/main/models/sams) - download (if you don't have them) and put into the "ComfyUI\models\sams" directory
5. Run ComfyUI and find there ReActor Nodes inside the menu `ReActor` or by using a search

</details>

<details>
  
<summary> Troubleshooting </summary>

<a name="insightfacebuild">

### **I. (For Windows users) If you still cannot build Insightface for some reasons or just don't want to install Visual Studio or VS C++ Build Tools - do the following:**

1. (ComfyUI Portable) From the root folder check the version of Python:<br>run CMD and type `python_embeded\python.exe -V`
2. Download prebuilt Insightface package [for Python 3.10](https://github.com/Gourieff/Assets/raw/main/Insightface/insightface-0.7.3-cp310-cp310-win_amd64.whl) or [for Python 3.11](https://github.com/Gourieff/Assets/raw/main/Insightface/insightface-0.7.3-cp311-cp311-win_amd64.whl) (if in the previous step you see 3.11) or [for Python 3.12](https://github.com/Gourieff/Assets/raw/main/Insightface/insightface-0.7.3-cp312-cp312-win_amd64.whl) (if in the previous step you see 3.12) and put into the stable-diffusion-webui (A1111 or SD.Next) root folder (where you have "webui-user.bat" file) or into ComfyUI root folder if you use ComfyUI Portable
3. From the root folder run:
   - (SD WebUI) CMD and `.\venv\Scripts\activate`
   - (ComfyUI Portable) run CMD
4. Then update your PIP:
   - (SD WebUI) `python -m pip install -U pip`
   - (ComfyUI Portable) `python_embeded\python.exe -m pip install -U pip`
5. Then install Insightface:
   - (SD WebUI) `pip install insightface-0.7.3-cp310-cp310-win_amd64.whl` (for 3.10) or `pip install insightface-0.7.3-cp311-cp311-win_amd64.whl` (for 3.11) or `pip install insightface-0.7.3-cp312-cp312-win_amd64.whl` (for 3.12)
   - (ComfyUI Portable) `python_embeded\python.exe -m pip install insightface-0.7.3-cp310-cp310-win_amd64.whl` (for 3.10) or `python_embeded\python.exe -m pip install insightface-0.7.3-cp311-cp311-win_amd64.whl` (for 3.11) or `python_embeded\python.exe -m pip install insightface-0.7.3-cp312-cp312-win_amd64.whl` (for 3.12)
6. Enjoy!
</details>
