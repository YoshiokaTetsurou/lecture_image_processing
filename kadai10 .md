# 課題１０レポート

imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai1.m
ORG=imread('image\tomica.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示
```

によって，原画像を読み込み，グレースケールに変換し表示した結果を図１に示す．

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai10_1.bmp)  
図1 グレースケール画像

プレウィット法をもちいてエッジ抽出を行い、表示した結果を図２に示す。
```matlab:kadai1.m
IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai10_2.bmp)  
図2 プレウィット法を用いたエッジ抽出


ソベル法をもちいてエッジ抽出を行い、表示した結果を図２に示す。
```matlab:kadai1.m
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai10_3.bmp)  
図3 ソベル法を用いたエッジ抽出

キャニー法をもちいてエッジ抽出を行い、表示した結果を図２に示す。
```matlab:kadai1.m
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai10_4.bmp)  
図4 キャニー法を用いたエッジ抽出

プレウィット法及びソベル法では対象物の輪郭のみを抽出しているのに対し、キャニー法では背景のエッジも抽出している。ここからキャニー法は他のエッジ抽出方法よりも小さい濃度値の変化も検出可能であることが解る。