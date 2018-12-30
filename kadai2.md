# 課題2レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．

ORG=imread('mandrill.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示
pause; % 一時停止

によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai2/kadai2_1.png)  
図1 原画像(白黒)

2階調画像を生成するために以下のプログラムを実行する。

IMG = ORG>128;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;

2階調画像を生成した結果を図２に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai2/kadai2_2.png)  
図2 2階調画像

4階調画像を生成するために以下のプログラムを実行する。

IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;

4階調画像を生成した結果を図３に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai2/kadai2_3.png)  
図3 4階調画像

8階調画像を生成するために以下のプログラムを実行する。

IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>160;
IMG5 = ORG>192;
IMG6 = ORG>224;
IMG = IMG0+IMG1+IMG2+IMG3+IMG4+IMG5+IMG6;
imagesc(IMG); colormap(gray); colorbar; axis image;

8階調画像を生成した結果を図4に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai2/kadai2_4.png)  
図4 8階調画像

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
