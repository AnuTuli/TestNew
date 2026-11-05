# YOLO Detector - Android TFLite Application

This repository contains the complete Android application for running your TensorFlow Lite (`YOLO Detector`) model on mobile devices with hardware acceleration (GPU / NNAPI / XNNPACK CPU).

---

## ⚡ Option 1: Instant APK via GitHub (Zero Setup Required)

1. Push this folder to a GitHub repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit of YOLO Detector"
   git remote add origin https://github.com/YOUR_USERNAME/yolo-detector.git
   git push -u origin main
   ```
2. Navigate to your repository on GitHub and click the **Actions** tab.
3. The **"Build Android APK"** workflow will start automatically.
4. Once completed (~2 minutes), click on the workflow run and download **app-debug-apk** under the **Artifacts** section!
5. Transfer the `.apk` to your Android phone and install.

---

## 💻 Option 2: Build with Android Studio

1. Open **Android Studio** (Hedgehog 2023.1 or newer recommended).
2. Choose **File > Open** and select this project directory.
3. Wait for Gradle Sync to complete.
4. Connect an Android phone (with USB Debugging enabled) or start an Emulator.
5. Click the green **Run (▶)** button, or go to **Build > Build Bundle(s) / APK(s) > Build APK(s)**.

---

## 🛠 Option 3: Build from Command Line

Ensure you have **JDK 17** installed:
```bash
chmod +x gradlew
./gradlew assembleDebug
```
The generated APK will be located at:
`app/build/outputs/apk/debug/app-debug.apk`

---

## 📂 Model Architecture Configuration

- **Model File**: `app/src/main/assets/model.tflite`
- **Labels File**: `app/src/main/assets/labels.txt` (80 classes configured)
- **Input Dimensions**: 640 x 640 x 3 (FLOAT32)
- **Normalization**: zero_to_one
- **Hardware Delegate**: GPU (4 threads)
