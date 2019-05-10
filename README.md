# CVFX-Team8-HW5-Multiview 3D visual effects


## 1. Take multi-view images by yourselves

### Example1. Motion parallax

### Example2. Stop motion
* 原始照片

| 順序一 | 順序二 | 順序三 |
| :--------: | :--------: | :--------: |
| 順序四     | 順序五     | 順序六     |

![](https://i.imgur.com/b8bSrcW.jpg)

### Example3. Live photo



---
## 2. Show image alignment results between different images

### Example1. Motion parallax

### Example2. Stop motion
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



### Example3. Live photo




---
## 3. Generate the multi-view 3D visual effects

### Example1. Motion parallax

### Example2. Stop motion
* Generate GIF with original pictures without any effects

[Imgur](https://i.imgur.com/z1nlziv.gifv)

* 問題

    - 在做 alignment 後，生成的圖片會有黑邊跑出來
    - 先對黑邊做預處理，效果可能會更好

### Example3. Live photo




---
## 4. Exploit creativity to add some image processing to enhance effect

### Example1. Motion parallax

### Example2. Stop motion
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

### Example3. Live photo




---
