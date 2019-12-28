# 課題2レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である.

```matlab:kadai2.m
ORG=imread('image\tomica.png'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示
```

によって、原画像を読み込みトゥルーカラーイメージをグレースケールイメージに変換し、表示した結果を図１に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai2_1.bmp)
図１ グレースケールイメージ

2階調画像を生成し、表示させる。
グレースケールイメージの輝度値が128より大きい配列要素が1となり白として表示され、128以下の要素が0となり黒として表示される。

```matlab:kadai2.m
IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;
```
2階調画像の結果を図２に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai2_2.bmp)
図2 2階調画像

4階調画像を作成する。配列の要素を64、128、192で比較しその結果を加えることで、輝度値が64以下の要素は0、64より大きい要素は1、128より大きい要素は2、192より大きい要素は3となり4階調画像が作成される。値が4の画素は白となり値が小さくなる毎に黒に近づいていき、0の要素は黒として表示される。

```matlab:kadai2.m
IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;
```

4階調画像を図３に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai2_3.bmp)
図3　4階調画像

8階調画像を作製するには、同様に32、64、96、128、160、192、224を比較し、足し合わせれよい。

```matlab:kadai2.m
IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>160;
IMG5 = ORG>192;
IMG6 = ORG>224;
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;
imagesc(IMG); colormap(gray); colorbar;  axis image;
```

8階調画像を図4に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai2_4.bmp)
図4　8階調画像

このように階調を増やすことで画像を滑らかに表現することができる。