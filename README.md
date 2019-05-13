# CVFX-HW5-Multiview 3D visual effects


## 1. Take multi-view images by yourselves


### Example1. Stop motion
* 原始照片

| 順序一 | 順序二 | 順序三 |
| :--------: | :--------: | :--------: |
| 順序四     | 順序五     | 順序六     |

![](https://i.imgur.com/b8bSrcW.jpg)

### Example2. Live photo
* 連續拍攝約25張照片，記錄校園公車。
![](https://imgur.com/EMjJ1VO.jpg)

---
## 2. Show image alignment results between different images


### Example1. Stop motion
* 採用**SIFT**
* Alignment matched

| 1 | 2 |
| :--------: | :--------: |
| 2     | 3     |
| 3     | 4     |
| 4     | 5     |
| 5     | 6     |

![](https://i.imgur.com/gI5YUE3.jpg)
![](https://i.imgur.com/WBEOmS8.jpg)
![](https://i.imgur.com/Qrxl3kf.jpg)

* Alignment found

| 1_2 | 2_3 | 3_4 |
| :--------: | :--------: | :--------: |
| 4_5     | 5_6     |      |

![](https://i.imgur.com/SU0hPFU.jpg)



### Example2. Live photo
* 先Detect ORB features，然後再做Image alignment，alingment後會有黑邊，再把它們裁切掉(因為本來的照片傾斜不嚴重，所以裁切掉的不多)
![](https://imgur.com/TyuUjVR.jpg)



---
## 3. Generate the multi-view 3D visual effects

### Example1. Stop motion
* Generate GIF with original pictures without any effects

![](output.gif)

* 問題

    - 在做 alignment 後，生成的圖片會有黑邊跑出來
    - 先對黑邊做預處理，效果可能會更好

### Example2. Live photo

[![](http://img.youtube.com/vi/y1VHWk_uXmk/0.jpg)](http://www.youtube.com/watch?v=y1VHWk_uXmk "Live photo")

---
## 4. Exploit creativity to add some image processing to enhance effect


### Example1. Stop motion
* 針對第三部分的問題做優化動作，以解決黑邊問題
* 使用過去作業所做的GAN，進行補圖
> hw3 Inpainting
* GAN 補圖結果

| 1_2 | 2_3 |
| :--------: | :--------: |
| 3_4     | 4_5     |
| 5_6     |      |

![](https://i.imgur.com/R9Hwt17.jpg)
![](https://i.imgur.com/57wmpYs.png)

* Generate GIF

![](https://i.imgur.com/o0ZkB8C.gif)

* 優化效果

    - 至少沒有黑邊出現
    - 桌面、線材材質表現正常，不會讓人感覺很突兀

### Example2. Live photo
* 加上imovie裡的交疊特效，使得照片與照片之間轉換的更滑順。
[![](http://img.youtube.com/vi/c48Nf3o9jOg/0.jpg)](http://www.youtube.com/watch?v=c48Nf3o9jOg "Live photo2")



---


## Example3.Motion Parallax
### 取材
首先錄一段往右平移的影片，然後擷取其中兩個frame作為視差的兩張圖片
![](https://i.imgur.com/A1zbYv7.jpg)

### 方法
根據 https://www.adorama.com/alc/0011780/article/Wiggle-3D-How-To-Make-Animated-3D-Images 的方法來實作Motion Parallax(Wiggle Photo)
1. 使用修圖軟體(在此使用GIMP)載入兩張圖片
2. 將layer上面的圖片透明度設為50%
3. 將兩張圖片疊起來（可以使用alignment的方式，然而實際測試後，人工疊起來應該就足夠了，alignment造成的變形造成效果反而不是那麼的好）
4. 裁切掉邊邊照片沒有重疊的部分
5. 使用GIMP內建的Animation功能，然後輸出成GIF（同時設定切換週期為何）
### 成果
- 間隔60ms
![](https://i.imgur.com/fjlVnH0.gif)
- 間隔 100ms
![](https://i.imgur.com/i4BQBSS.gif)
- 間隔 500ms
![](https://i.imgur.com/hRwDkhM.gif) 

另外觀察成果後可以發現除了對齊的好壞之外，如果切換影像的速度太慢，立體感也會跟著變差。太快也會不太自然就是了
