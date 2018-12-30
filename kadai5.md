# 課題5レポート

標準画像「mandrill」を原画像とする．この画像は縦512画像，横512画素による正方形のディジタルカラー画像である．
```
ORG=imread('mandrill.jpg'); % 原画像の入力
ORG=rgb2gray(ORG); % カラー画像を白黒濃淡画像へ変換
imagesc(ORG); colormap(gray); colorbar;
pause;
```
によって，原画像を読み込み，白黒画像に変換して表示した結果を図１に示す．

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai5/kadai5_1.png)  
図1 原画像(白黒)

以下のプログラムを実行して、判別分析法による画像の2値化を行う。
```
H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納
myu_T = mean(H);
max_val = 0;
max_thres = 1;
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

IMG = ORG > max_thres;
imagesc(IMG); colormap(gray); colorbar;
pause;
```
このプログラムは、閾値を1～254まで設定し、その閾値によってヒストグラムを2つのクラスに分け、クラス内分散とクラス間分散の値を計算し、クラス間分散/クラス内分散が最大になる閾値を求めている。判別分析法によって2値化された画像を図2に示す。

![原画像](https://github.com/juntdu/lecture_image_processing/blob/master/image/kadai5/kadai5_2.png)
図2 判別分析法による2値化画像
