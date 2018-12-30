# 課題7レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG = imread('mandrill.jpg'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai7/kadai7_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、濃度ヒストグラムを作成し表示する。。
```
imhist(ORG); % 濃度ヒストグラムを生成、表示
pause;
```
原画像の濃度ヒストグラムを図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai7/kadai7_2.png)  
図2 原画像の濃度ヒストグラム

以下のプログラムを実行して、ダイナミックレンジを0から255に拡大する。
```
ORG = double(ORG);
mn = min(ORG(:)); % 濃度値の最小値を算出
mx = max(ORG(:)); % 濃度値の最大値を算出
ORG = (ORG-mn)/(mx-mn)*255;
imagesc(ORG); colormap(gray); colorbar; % 画像の表示
pause;
```
ダイナミックレンジを拡大した画像を図3に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai7/kadai7_3.png)  
図3 ダイナミックレンジを拡大した画像

以下のプログラムを実行して、ダイナミックレンジを拡大した画像の濃度ヒストグラムを作成し表示する。
```
ORG = uint8(ORG);
imhist(ORG); % 濃度ヒストグラムを生成、表示
```
ここで、uint8関数は引数を8ビット符号なし整数に変換している。8ビットということは10進数の0～255を表現することができ、ダイナミックレンジの拡大で行った処理により0～255の範囲外となってしまった数を最も近い端点(0または255)に変換している。原画像の濃度ヒストグラムの濃度値が0～255であるのでそれに合わせてレンジが拡大されているか確認しやすくするためにこの処理が必要であると考えられる。
ダイナミックレンジを拡大した画像の濃度ヒストグラムを図4に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai7/kadai7_4.png)  
図4 ダイナミックレンジを拡大した画像の濃度ヒストグラム

図1、3を比較すると大きな差は感じられずほとんど変化していないようにも思われるが、図2、4を比較すると濃度値が高い部分のレンジが広がっていることが確認できる。
