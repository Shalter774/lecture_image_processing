# 課題4レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work04_res/0_mono.png)  

図1 モノクロ化した原画像

図1の画像のヒストグラムを

> imhist(ORG);

によって表示する.表示されたヒストグラムを図2として示す.

![ヒストグラム](https://github.com/Shalter774/lecture_image_processing/blob/master/work04_res/1_hist.png)  

図1 モノクロ化した原画像のヒストグラム
