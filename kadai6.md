# 課題6レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG=imread('mandrill.jpg'); % 原画像の入力
ORG = rgb2gray(ORG);
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause; % 一時停止
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai6/kadai6_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、閾値128による2値化を行う。
```
IMG = ORG>128; % 128による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
閾値128による2値化画像を図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai6/kadai6_2.png)  
図2 閾値128による2値化画像

以下のプログラムを実行して、ディザ法による2値化を行う。
```
IMG = dither(ORG); % ディザ法による二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
```
ディザ法による2値化画像を図3に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai6/kadai6_2.png)  
図3 ディザ法による2値化画像
