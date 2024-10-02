# Autonomous Driving Car Project
Develop Autonomous Car with RaspberryPi

# 1. RaspberryPi4 Set up

# 2. Detecting Lane

## Lane Detecting Process
|No.|Content|
|------|---|
|1.|Read Img [Video]|
|2.|Set GrayScale|
|3.|Set GaussianBlur|
|4.|edge Detecting Using Canny Algorithm|
|5.|Apply ROI(Region Of Interest)|
|6.|Lane Detecting with Hough Transform|



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


## 2.4 edge Detecting Using Canny Algorithm
```python
edge = cv.Canny(blur, 50, 200, None, 3)
```
<img width="1263" alt="canny" src="https://github.com/hyunsoi/Autonomoun-Car/assets/102220333/78fbcda2-e0bf-4988-a1b9-10533944db95">


## 2.5 Set ROI 
```python
def ROI(img, vertices, color3=(255,255,255), color1=255): # ROI 셋팅

    mask = np.zeros_like(edge) # mask = img와 같은 크기의 빈 이미지
    
    if len(edge.shape) > 2: # Color 이미지(3채널)라면 :
        color = color3
    else: # 흑백 이미지(1채널)라면 :
        color = color1
        
    # vertices에 정한 점들로 이뤄진 다각형부분(ROI 설정부분)을 color로 채움 
    cv.fillPoly(mask, vertices, color)
    
    # 이미지와 color로 채워진 ROI를 합침
    ROI_image = cv.bitwise_and(edge, mask)
    return ROI_image
```
```python
h, w = edge.shape
print('height ', h)
print('width ', w)

height, width = edge.shape[:2]

vertices = np.array([[(50,height),(50, height/2+60), \
                      (width-50, height/2+60), (width-50,height)]], dtype=np.int32)
roi_img = ROI(edge, vertices) # vertices에 정한 점들 기준으로 ROI 이미지 생성
```
<img width="752" alt="roi_image" src="https://github.com/hyunsoi/Autonomoun-Car/assets/102220333/acc29692-f72b-45e1-9024-8b24f6ced267">

# 3. 
# 4. 

# 5. 
