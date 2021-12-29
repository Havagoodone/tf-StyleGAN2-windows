# [StyleGAN2 by NVIDIA](https://github.com/NVlabs/stylegan2)
Basic Setting and Informations For StyleGAN2 by NVIDIA with tensorflow 
* Paper: http://arxiv.org/abs/1912.04958

If you need more details, visit [StyleGAN2](https://github.com/NVlabs/stylegan2)

# Test Environment 
* OS : Windows
* Anaconda (Not essenstial, but helpful for several development env)
* RTX 3090
* python 3.6 
* tensorflow 1.14 
* cudatoolkit 11.2 
* cudnn 8.2.0 

# If you have these errors
* No module, requests 
 
-> install requests ( Like pip install requests / conda install requests )

* No moudle, PIL 
 
-> install pillow ( Like pip install pillow / conda install pillow ) ("Install PIL" doesn't work)

* RuntimeError: Could not find MSVC/GCC/CLANG installation on this computer.
 
-> Follow Requirments Guide on [NVlabs](https://github.com/NVlabs/stylegan2)

**If it doesn't work too, then follow below.**
1. Download Visual Studio Community (In my case, VS 2017 Community), and then dowload Desktop development with C++.(You can see MSVC or CLANG in description.)

2. Open custom_ops.py file in dnnlib.tflib.ops, and then edit 'complier_bindir_search_path'.
 
 **Ex) Change Original Path to Yours**
  
 **OG)**
  'C:/Program Files (x86)/Microsoft Visual Studio/2017/Community/VC/Tools/MSVC/14.14.26428/bin/Hostx64/x64'
  
 **Changed)**
  'C:/Program Files (x86)/Microsoft Visual Studio/**2017**/Community/VC/Tools/MSVC/**14.16.27023**/bin/Hostx64/x64'
   
  (I'm using visual studio **2017, 14.16.27023**)
  
  * nvcc fatal   : Value 'sm_86' is not defined for option 'gpu-architecture'

-> Upgrade cudatoolkit version or make a new env with upgraded cudatoolkit version. It could happen because you had a recent version of GPU.

# Code For Running
 
**Test 1)**
python run_generator.py generate-images --network=gdrive:networks/stylegan2-ffhq-config-f.pkl --seeds=6600-6625 --truncation-psi=0.5

**Test 2)**
python run_generator.py generate-images --network=gdrive:networks/stylegan2-ffhq-config-e.pkl --seeds=6600-6625 --truncation-psi=0.5

# Results
**TEST 1 ) total elapsed time : 19 min 23 sec**

**One of Test 1 Results**
![Result 1](https://user-images.githubusercontent.com/96462185/147219811-9713d3b2-6337-4b66-8270-ab14b86c6047.png)

**TEST 2 ) total elapsed time : 18 min 8 sec**

**One of Test 2 Results**
![Reuslt 2](https://user-images.githubusercontent.com/96462185/147219816-dd9ac8e2-7b9d-4eed-ae44-d878e5a45f4a.png)

