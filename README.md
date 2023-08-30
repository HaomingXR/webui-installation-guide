<h2 align="center">Stable Diffusion<br>Automatic1111 Webui<br>安裝教學</h2>

<p align="center"><b>by. Haoming</b><br><i>Last Update: 2023/08/30</i></p>

## 下載使用者介面
<details>
<summary>簡易版 (for 美術)</summary>

1. 前往[此連結](https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.0.0-pre)
2. 點擊 **`sd.webui.zip`** 進行下載
3. 將所有內容解壓縮至任意資料夾
4. 執行 **`update.bat`**
5. 完成!
</details>

<details>
<summary>詳細版 (for 技術)</summary>

1. 前往 [cuda-toolkit-archive](https://developer.nvidia.com/cuda-toolkit-archive)
2. 下載並安裝 `CUDA Toolkit 11.8` *(`12.x` **不支援**)*
3. 前往 [python.org](https://www.python.org/downloads/)
4. 下載並安裝 `Python 3.10.x` *(`3.11.x` **不支援**)*
    - 記得勾選 **`Add python.exe to PATH`**
5. 下載並安裝 [`git`](https://git-scm.com/downloads) *(全部選項預設即可)*
6. `git` `clone` https://github.com/AUTOMATIC1111/stable-diffusion-webui 至任意資料夾
7. 完成!
</details>

<details>
<summary>Apple版 </summary>

- [Installation on Apple Silicon](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon)
</details>

## 下載Stable Diffusion模型
1. 前往 [CivitAI](https://civitai.com/models?tag=base+model)
2. 下載任意 Checkpoint
    - 注意右側 `Base Model` 須為 **SD 1.5**

##### 個人推薦
- 擬真: [Realistic Vision](https://civitai.com/models/4201/realistic-vision-v51)
- 二次元: [UHD-23](https://civitai.com/models/22371/uhd-23)

3. 按下右側藍色 `Download` 鍵即可

<details>
<summary>簡易版 (for 美術)</summary>

4. 將下載的模型 *(格式為 `.safetensors`)* 移至上面安裝的路徑中，`~\webui\models\Stable-diffusion` 資料夾內
</details>

<details>
<summary>詳細版 (for 技術)</summary>

4. 將下載的模型 *(格式為 `.safetensors`)* 移至 `~\stable-diffusion-webui\models\Stable-diffusion` 資料夾內
5. 右鍵編輯 `~\stable-diffusion-webui\webui-user.bat`
6. 將 `--xformers` 以及 `--no-half-vae` 加至 `set COMMANDLINE_ARGS=` 後面 *(兩參數間須有空格)*
</details>

## 執行使用者介面
<details>
<summary>簡易版 (for 美術)</summary>

- 執行安裝的路徑中的 **`run.bat`**
</details>

<details>
<summary>詳細版 (for 技術)</summary>

- 執行安裝的路徑中的 **`webui-user.bat`**
</details>

1. 第一次執行時會開始下載需要的內容 *(需要數分鐘)*
2. 執行時會開啟一個 Console
3. 當你在 Console 中看到如下的 localhost 的連結便表示下載完成
> Running on local URL:  http://127.0.0.1:7860

4. 接著便可以在瀏覽器開啟上述的連結
5. 完成!

## ControlNet
<details>
<summary>安裝</summary>

1. 在介面中打開 **Extensions** 的頁面 *(上方，**Settings**右邊那個)*
2. 點選 `Install from URL`
3. 在 `URL for extension's git repository` 輸入 https://github.com/Mikubill/sd-webui-controlnet 後按 `Install`
4. 在 `Install` 下方出現安裝完畢的提示後，把瀏覽器分頁以及 Console 關閉，再按照前述重新開啟介面一次
5. 確認畫面下方有 `ControlNet v1.X.YYY` 介面
6. 前往 [HuggingFace](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main)
7. 下載以下等模型 *(點擊紅色`LFS`右邊的箭頭)*
    - `control_v11f1p_sd15_depth.pth`
    - `control_v11p_sd15_canny.pth`
    - `control_v11p_sd15_openpose.pth` 
    - `control_v11f1e_sd15_tile.pth`
8. 將下載的 `.pth` 模型移至 `~webui\models\ControlNet` 資料夾
9. 完成!
</details>

<details>
<summary>使用</summary>

1. 點擊下方 `ControlNet v1.X.YYY` 開啟子介面，並在 **Drop Image Here...** 區放入一張隨意參考圖片
2. 在 `Control Type` 點選 **Depth** 或 **Canny**等等，點擊下方爆炸(💥) 按鈕會產生預覽
3. 記得勾選 **Enable** 以套用
</details>
