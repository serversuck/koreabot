# 🚀 Koreabot Setup
## Train yolo model
https://colab.research.google.com/drive/1F87RuXaNlBXETBa7l-aNEfY9zCkSnZZv?usp=sharing

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
## 🐢 ตั้งค่าตรวจจับ lane
```bash
roslaunch koreabot detect_lane.launch mode:=calibration
```

---
## ทดสอบการวิ่งตาม lane
```bash
roslaunch koreabot mission.launch
rostopic pub -1 /mission ... 1
```
## Command สำคัญ
```bash
$ rostopic pub -1 /reset std_msgs/Empty  #reset odom
$rosrun rqt_reconfigure rqt_reconfigure  #setting parameter
$rostopic pub -1 /detect/white_toggle std_msgs/Bool "data: True"  # ติดตามเส้นสีขาว
$rostopic pub -1 /detect/yellow_toggle std_msgs/Bool "data: True"  # ติดตามเส้นสีเหลือง
$rostopic pub -1 /detect/lane_toggle std_msgs/Bool "data: True"  # ติดตามเลน / false หยุดติดตามเลน



```
