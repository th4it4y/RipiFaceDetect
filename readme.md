# Project Microprocessor : Face Detection Pi
<img src="Face Recognition/result.jpg"> <img src="Face Recognition/find 1.png">
<img src="Face Recognition/result2.jpg"> <img src="Face Recognition/find 2.png">

## Details :memo:
- ตรวจจับใบหน้าด้วย บอร์ด Raspberry Pi 4 


## Setting up project: :computer:
```ruby
# Install Libary
• sudo apt-get update
• sudo apt-get upgrade
• sudo apt-get install python-picamera
• pip3 install opencv-python
• sudo apt-get install libhdf5-dev libhdf5-serial-dev libatlas-base-dev libjasper-dev  libqtgui4  libqt4-test
• sudo apt-get install libcblas-dev libhdf5-dev libhdf5-serial-dev libatlas-base-dev libjasper-dev  libqtgui4  libqt4-test
```
```ruby
# Setting Camera to Eanable
• sudoraspi-config 
• เลือก Interface option
• เลือก 'Camera' option 
• กดปุ่มEnter key เพือenable การใช้งาน 
• เลือก“Finish” 
• เลือก reboot your Raspberry Pi.

## How to run project
• cd Face Recognition
• Python3 face_detection
• ถือกล้อง ส่องหน้า เเล้วจะได้ไฟล์ที่ชื่อว่า result.jpg ออกมา พร้อม Output แสดงจำนวนใบหน้าที่พบ

