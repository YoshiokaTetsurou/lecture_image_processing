# 課題５レポート
imageフォルダ内の「tomica.png」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```matlab:kadai5.m
ORG=imread('image\tomica.png'); % 原画像の入力
ORG = rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
```
によって、原画像を読み込み、グレースケールに変換し表示した結果を図１に示す。

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai5_1.bmp)  
図1 グレースケール画像

分析判別法を用いて画像を２値化する。濃度ヒストグラムを作成し、全画素の濃度の平均値、を計算する。

```matlab:kadai5.m
H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
myu_T = mean(H);
```
1から255の濃度iでクラスを分けたとき、対象物と背景との違いが最も際立つように、クラス内分散に対しクラス間分散が最大となるような閾値を決める。

```matlab:kadai5.m
for i=1:255
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける
C2 = H(i+1:256);
n1 = sum(C1); %画素数の算出
n2 = sum(C2);
myu1 = mean(C1); %平均値の算出
myu2 = mean(C2);
sigma1 = var(C1); %分散の算出
sigma2 = var(C2);
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出
if max_val<sigma_B/sigma_w
max_val = sigma_B/sigma_w;
max_thres =i;
end;
end;
```

以上で求めた閾値により2値化した画像を図２に示す。
```matlab:kadai5.m
IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;
```

![原画像](https://raw.githubusercontent.com/YoshiokaTetsurou/lecture_image_processing/master/image/kadai5_2.bmp)  
図2　判別分析法を用いた2値化画像

クラス間分散が大きいと背景と対象物がよく分離され、クラス内分散が小さいと背景と対象物がそれぞれ一つにまとまっていることを意味している。