# 課題4レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG=imread('mandrill.jpg'); % 原画像の入力
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
pause;
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai4/kadai4_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、画素の濃度ヒストグラムを表示させる。濃度ヒストグラムを図2に示す。
```
imhist(ORG); % ヒストグラムの表示
```

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai4/kadai4_2.png)  
図2 濃度ヒストグラム
