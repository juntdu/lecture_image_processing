# 課題8レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG = imread('mandrill.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai8/kadai8_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、閾値128で画像を2値化する。
```
IMG = ORG > 128; % 閾値128で二値化
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
2値化画像を図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai8/kadai8_2.png)  
図2 2値化画像

以下のプログラムを実行して、2値化された画像の連結成分にラベルをつける。
```
IMG = bwlabeln(IMG);
imagesc(IMG); colormap(jet); colorbar; % 画像の表示
pause;
```
ラベルをつけた画像を図3に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai8/kadai8_3.png)  
図3 ラベルをつけた画像

図3より、「mandrill」の体毛は青色の連結成分でつながっていて顔の輪郭が分かるようになっている。
