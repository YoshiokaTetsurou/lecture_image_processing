# 課題4レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai1.m
ORG=imread('image\tomica.png'); % 原画像の入力
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
```

によって、原画像を読み込み、グレースケールに変換し表示した画像を図１に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai4_1.bmp)  
図1 グレースケール画像

関数imhistを使用してグレースケールのヒストグラムを作成した結果を図２に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai4_2.bmp)  
図2 ヒストグラム

ヒストグラムから画像に含まれる輝度値の画素数の分布をみることができる。