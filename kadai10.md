# 課題10レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG = imread('mandrill.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); %カラーからグレイへの変換
imagesc(ORG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai10/kadai10_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、プレウィット法によるエッジ抽出を行う。
```
IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
プレウィット法によるエッジ抽出画像を図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai10/kadai10_2.png)  
図2 エッジ抽出画像(プレウィット法)

以下のプログラムを実行して、ソベル法によるエッジ抽出を行う。
```
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
ソベル法によるエッジ抽出画像を図3に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai10/kadai10_3.png)  
図3 エッジ抽出画像(ソベル法)

以下のプログラムを実行して、キャニー法によるエッジ抽出を行う。
```
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）
imagesc(IMG); colormap('gray'); colorbar;% 画像表示
pause; % 一時停止
```
キャニー法によるエッジ抽出画像を図4に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai10/kadai10_4.png)  
図4 エッジ抽出画像(キャニー法)
