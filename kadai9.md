# 課題９レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai9.m
ORG = imread('image\tomica.png'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```

によって，原画像を読み込み，グレースケールに変換し表示した結果を図１に示す．

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai9_1.bmp)  
図1 グレースケール画像

imnoise関数を用いて画像にノイズを添付した画像を表示する。
```matlab:kadai9.m
ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai9_2.bmp)  
図2 ノイズ添付画像

```matlab:kadai9.m
IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```
によって平滑化フィルタで雑音除去した画像を図3に表示する。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai9_3.bmp)  
図3 平滑化フィルタでノイズ除去した画像

画素ごとの濃度の変化を滑らかにすることでノイズを除去していることが解る。

次にメディアンフィルタを用いてノイズ除去を行った画像を図３に示す

```matlab:kadai9.m
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai9_4.bmp)  
図4 メディアンフィルタでノイズ除去した画像

画像からノイズは除去されているが、文字などの細かい濃度の変化がある箇所でも画像がぼけてしまっていることが解る。

次に[0,-1,0;-1,5,-1;0,-1,0]のフィルタを用いてノイズ除去を行い、その結果を図４に示す。

```matlab:kadai9.m
f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai9_5.bmp)  
図5 メディアンフィルタでノイズ除去した画像

画像からノイズは除去されているが、全体の画像の濃度差が小さくなっている。