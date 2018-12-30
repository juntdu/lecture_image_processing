# 課題3レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG=imread('mandrill.jpg'); % 原画像の入力
ORG= rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換

imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai3/kadai3_1.png)  
図1 原画像(白黒)

閾値を64に設定する。この場合、輝度値が64以上の画素を1に、その他を0に変換する。
```
IMG = ORG > 64; % 輝度値が64以上の画素を1，その他を0に変換
imagesc(IMG); colormap(gray); colorbar;
pause;
```
閾値を64に設定し、閾値処理をした画像を図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai3/kadai3_2.png)  
図2 閾値が64の場合の画像

次に閾値を96に設定する。この場合、輝度値が96以上の画素を1に、その他を0に変換する。
```
IMG = ORG > 96;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
閾値を96に設定し、閾値処理をした画像を図3に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai3/kadai3_3.png)  
図3 閾値が96の場合の画像

次に閾値を128に設定する。この場合、輝度値が128以上の画素を1に、その他を0に変換する。
```
IMG = ORG > 128;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
閾値を128に設定し、閾値処理をした画像を図4に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai3/kadai3_4.png)  
図4 閾値が128の場合の画像

最後に閾値を192に設定する。この場合、輝度値が192以上の画素を1に、その他を0に変換する。

```
IMG = ORG > 192;
imagesc(IMG); colormap(gray); colorbar;
```
閾値を192に設定し、閾値処理をした画像を図5に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai3/kadai3_5.png)  
図5 閾値が192の場合の画像
