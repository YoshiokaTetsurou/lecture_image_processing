# 課題３レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai3.m
ORG=imread('image\tomica.png'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```

によって，原画像を読み込み，グレースケールに変換して表示した結果を図１に示す．

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai3_1.bmp)  
図1 グレースケール画像

```matlab:kadai3.m
IMG = ORG > 64; 
imagesc(IMG); colormap(gray); colorbar;
```
により輝度値が64以上の画素を1（白），その他を0（黒）に変換した画像を図２に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai3_2.bmp)  
図2 閾値が64の2階調画像

同様に輝度値の閾値を96、128、192とした画像を図3から5に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai3_3.bmp)  
図3 閾値が96の2階調画像

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai3_4.bmp)  
図4 閾値が128の2階調画像

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai3_5.bmp)  
図5 閾値が192の2階調画像

このように閾値が適切でないとき対象物が正確に認識できなくなる。