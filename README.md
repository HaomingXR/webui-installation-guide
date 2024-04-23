<h2 align="center">Stable Diffusion<br>Automatic1111 Webui<br>部署教學</h2>

<p align="center"><b>by. Haoming</b><br><i>Last Update: 2024/04/23</i></p>

## 安裝

1. 點擊此[連結](https://github.com/lllyasviel/stable-diffusion-webui-forge/releases/download/latest/webui_forge_cu121_torch21.7z)進行下載
3. 將所有內容解壓縮至安裝資料夾
4. 執行 **`update.bat`**
5. 右鍵編輯 `webui` 資料夾中的 **`webui-user.bat`** 檔案
6. 在 `set COMMANDLINE_ARGS=` 後面加上 `--xformers --api --port 8888`

## 下載模型

1. 下載 [Realistic Vision](https://civitai.com/api/download/models/130072?type=Model&format=SafeTensor&size=pruned&fp=fp16) *(2 GB)*
    - 或是前往 [CivitAI](https://civitai.com/models)下載其它 **`Checkpoint`**
2. 將下載的 `.safetensors` 模型放入 `webui\models\Stable-diffusion` 資料夾內

## 執行

1. 執行 **`run.bat`**
2. 第一次執行時會開始下載一些需要的內容 *(需要數分鐘)*
3. 當在 Console 中看到如下的 localhost 連結時便表示下載完成
    > Running on local URL:  http://127.0.0.1:8888
4. 在瀏覽器中開啟上述的連結

## ReActor 換臉

0. 先關閉 Webui
1. 下載 [insightface](https://github.com/Gourieff/Assets/raw/main/Insightface/insightface-0.7.3-cp310-cp310-win_amd64.whl)
2. 於安裝資料夾，點選路徑，輸入 `cmd` 以開啟 Console
3. 執行
    ```bash
    system\python\python.exe -m pip install insightface-0.7.3-cp310-cp310-win_amd64.whl
    ```
4. 執行 **`run.bat`**
5. 在介面中打開 **Extensions** 的頁面
6. 點選 `Install from URL`
7. 在 `URL for extension's git repository` 輸入 `https://github.com/Gourieff/sd-webui-reactor` 接著按 `Install`
8. 安裝需數分鐘
9. `Install` 下方出現安裝完成即可

## ADetailer 臉部微調

1. 在介面中打開 **Extensions** 的頁面
2. 點選 `Install from URL`
3. 在 `URL for extension's git repository` 輸入 `https://github.com/Bing-su/adetailer` 接著按 `Install`
4. `Install` 下方出現安裝完成即可
