# 🚀 Koreabot Setup

## 📦 ติดตั้ง YOLO
```bash
sudo apt install -y python3-pip python3-venv python3-opencv libgomp1
pip install ultralytics
pip install onnxruntime
```

---

## 🔧 แก้ไขให้รัน YOLO ได้
```bash
echo 'export LD_PRELOAD=/usr/lib/aarch64-linux-gnu/libgomp.so.1' >> ~/.bashrc
source ~/.bashrc
```

---

## 🐢 Clone this repository
```bash
cd ~/catkin_ws/src
git clone https://github.com/serversuck/koreabot.git
cd ~/catkin_ws
catkin_make
```

---

