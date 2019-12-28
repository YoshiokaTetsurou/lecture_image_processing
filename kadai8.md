# 課題8レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai8.m
ORG = imread('image\tomica.png'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```

によって，原画像を読み込み，グレースケールに変換し表示した結果を図１に示す．


![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai8_1.bmp)  
図1 グレースケール画像

```matlab:kadai8.m
IMG = ORG > 128; % 閾値128で二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```

によって、閾値128で2値化した画像を図２に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai8_2.bmp)  
図2 2値化画像

bwlabeln関数を用いて、2値化画像の連結成分にラベルをつけ、その画像を表示した結果を図３に示す。。

```matlab:kadai8.m
IMG = bwlabeln(IMG);
imagesc(IMG); colormap(jet); colorbar; % 画像の表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai8_3.bmp)  
図3 連結成分にラベルを付けた画像

bwlabeln関数の既定の連結性は8連結であるため着目画素とその8近傍画素の画素を調べ、それに同一のラベルを割り当てる。