# 課題７レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai7.m
ORG = imread('image\tomica.png'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```
によって，原画像を読み込み，グレースケールに変換し表示した結果を図１に示す．

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai7_1.bmp)  
図1 原画像

```matlab:kadai7.m
imhist(ORG); % 濃度ヒストグラムを生成、表示
```
によって濃度ヒストグラムを作成し表示した結果を図２に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai7_2.bmp)  
図1 原画像の濃度ヒストグラム

画素のダイナミックレンジを拡大するには、画像に含まれる濃度値の最小値と最大値を求め、その範囲で濃度値を正規化した値に255を掛ければよい。

```matlab:kadai7.m
ORG = imread('image\tomica.png'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```
ダイナミックレンジを拡大した結果を図３に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai7_3.bmp)  
図3 ダイナミックレンジを拡大した画像

このように濃度領域のダイナミックレンジを拡大することで濃度値の変化が小さい画像の濃度変化を大きくすることができる。

ダイナミックレンジを拡大する時、要素の値はdouble型となる。
imhist関数では濃度ヒストグラムを計算するときdouble型とuint8型では倍率とオフセットの値がとは異るため拡大前のヒストグラムとの比較が難しくなる。
これを避けるため拡大後の画像のデータ型をuint8型に変換し、ヒストグラムを表示した結果を図４に示す。
```matlab:kadai7.m
ORG = uint8(ORG); % この行について考察せよ
imhist(ORG); % 濃度ヒストグラムを生成、表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai7_4.bmp)  
図4 ダイナミックレンジを拡大した画像濃度ヒストグラム

このようにダイナミックレンジを拡大することで表示濃度範囲を有効に利用することが可能となる。