# Autonomous-Car
Develop Autonomous Car with RaspberryPi

# 1. RaspberryPi4 Set up

# 2. Detecting Road Lane

## Road Detecting Process
|No.|Content|
|------|---|
|1.|Read Img [Video]|
|2.|Set GrayScale|
|3.|Set GaussianBlur|
|4.|Lane Detecting Using Canny Algorithm|
|5.|Lane Detecting with Hough Transform|
|6.|Apply ROI(Region Of Interest)|



## 2.1 Read Road Lane IMG
```python
lane = cv.imread('lane.jpg')
```

<img width="480" alt="canny" src="https://github.com/hyunsoi/Autonomoun-Car/assets/102220333/d99d7ebf-d6d8-4427-9a42-38ffe4c37403">

## 2.2 Set IMG GrayScale
```python
gray = cv.cvtColor(lane, cv.COLOR_BGR2GRAY)
```
<img width="752" alt="lane_gray" src="https://github.com/hyunsoi/Autonomoun-Car/assets/102220333/3c9a22dd-7352-4b36-a49d-19bc46b9c4bf">



## 2.3 Set IMG GaussianBlur
```python
blur = cv.GaussianBlur(gray, (9, 9), 0)
```
<img width="752" alt="lane_blur" src="https://github.com/hyunsoi/Autonomoun-Car/assets/102220333/0037589a-78a1-40ab-a098-03685b9cbfe4">


## 2.4 Lane Detecting Using Canny Algorithm
```python
edge = cv.Canny(blur, 50, 200, None, 3)
```
<img width="1263" alt="canny" src="https://github.com/hyunsoi/Autonomoun-Car/assets/102220333/78fbcda2-e0bf-4988-a1b9-10533944db95">


# 3. 

# 4. 

# 5. 
