# Mobile on-Device Generative Language Model Inference

The repo provides the _main_ binary file generated with [FastLLM](https://github.com/ztxz16/fastllm) (`https://github.com/ztxz16/fastllm.git`) for the latest mainstream **ARMv8-based Android mobile devices** (i.e. smartphones and tablets). The file has been tested compatible to _Qualcomm Snapdragon 8+ Gen 1_, _8 Gen 2_, and _MediaTek Dimensity 8100_ platform devices.

## Step 1
Install [Termux](https://github.com/termux/termux-app/releases) application on your Android device. Make sure your device has more than 6GB of RAM. 

## Step 2
Download a supported model file from [HuggingFace](https://huggingface.co/huangyuyang). You only need to download the model file suffixed with ".flm". It is better downloaded directly with your target Android device.

## Step 3
Download the [_main_](https://github.com/henryyantq/mobile-on-device-GLM-inference/raw/main/main) binary file. Copy or move the _main_ file and the model file to a storage path of your target device, e.g. `downloads`.

## Step 4
Open _Termux_, and execute the command: `termux-setup-storage`.

## Step 5
Execute the command: `mv storage/downloads/<model_filename>.flm . && mv storage/downloads/main . && chmod 777 main`. Replace the `<model_filename>.flm` with the filename of your model, e.g. `chatglm2-6b-int4.flm`. (Notice that the example command works for you ONLY if you put the aforementioned 2 files under the `downloads` directory, which is STRONGLY recommended for common users!)

## Step 6
Run the streamlined inference of the language model with the command: `./main -p <model_filename>.flm`. 

**You're ready for the mobile on-device inference with the latest GLM(s)!**

## Hints:
- If you encounter error like `FORTIFY: read: count XXXXXXXX > SSIZE_MAX`, you can try adding ` -l` at the end of the command for _low memory mode_ inference. For instance, it is observed that the **Qwen-7B-Chat-int4.flm** model cannot run without low memory mode on devices with **≤12GB RAM**.
