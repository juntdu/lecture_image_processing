# 課題9レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG = imread('mandrill.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai9/kadai9_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、画像にノイズを添付する。
```
ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
ノイズを添付した画像を図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai9/kadai9_2.png)  
図2 ノイズ添付画像

以下のプログラムを実行して、平滑化フィルタによる雑音除去を行う。
```
IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
平滑化フィルタで雑音除去した画像を図3に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai9/kadai9_3.png)  
図3 平滑化フィルタによる雑音除去画像

以下のプログラムを実行して、メディアンフィルタによる雑音除去を行う。
```
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
メディアンフィルタで雑音除去した画像を図4に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai9/kadai9_4.png)  
図4 メディアンフィルタによる雑音除去画像

以下のプログラムを実行して、フィルタを設計し適用する。
```
f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計
IMG = filter2(f,IMG,'same'); % フィルタの適用
imagesc(IMG); colormap(gray); colorbar; % 画像の表示
pause;
```
設計したフィルタを適用した画像を図5に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai9/kadai9_5.png)  
図5 設計したフィルタの適用画像

以上の結果より、平滑化フィルタは、周囲の濃度値の平均をとるためノイズを完全には除去できていない。また、画像もぼやけているのが確認できる。一方、メディアンフィルタによる雑音除去は周囲の濃度値の中央値をとるためノイズをほとんど完璧に除去できている。また設計したフィルタは高域強調フィルタと呼ばれるものであり、画素の濃度値の変化を強調して表現することができる。図5より明るい部分と暗い部分が分かりやすいようになっていることが確認できる。
