# 課題６レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai6.m
ORG=imread('image\tomica.png'); % 原画像の入力
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```

によって、原画像を読み込み、グレースケールに変換し表示した結果を図１に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai6_1.bmp)  
図1 グレースケール画像


```matlab:kadai6.m
IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```
によって閾値を128としたときの2値化画像を図２に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai6_2.bmp)  
図2 閾値を128としたときの2値化画像



```matlab:kadai6.m
IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```
によってディザ法を用いて2値化した画像を図３に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai6_3.bmp)  
図2 ディザ法による2値化画像

このようにディザ法を用いて画像を2値化することで2値の濃度値のみで多階調画像を表現した疑似濃淡画像を表示することができる。