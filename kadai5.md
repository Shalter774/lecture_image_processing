# 課題5レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work04_res/0_mono.png)  

図1 モノクロ化した原画像

図1の画像を判別分析法により背景と対象物に分類する.

まず、

> H = imhist(ORG);

により、ヒストグラムを列ベクトルに格納する

> C1 = H(1:i);  
> C2 = H(i+1:256);

により,ヒストグラムを2つのクラスに分ける.  
出来上がった2つのクラスそれぞれに対して

> n1 = sum(C1);  
> n2 = sum(C2);  
> myu1 = mean(C1);  
> myu2 = mean(C2);  
> sigma1 = var(C1);  
> sigma2 = var(C2);

により、画素数の算出、平均値の算出、分散の算出を行う。  
これらから、

> sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2);  
クラス内分散

> sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2);  
クラス間分散

をそれぞれ求める.求めた分散を用い，

> if max_val<sigma_B/sigma_w 
> max_val = sigma_B/sigma_w;
> max_thres =i;
> end;

により，クラス間分散/クラス内分散を最大とするようにしきい値を定める.  
定めたしきい値を元に2値化した画像を図2に示す。

![判別分析法](https://github.com/Shalter774/lecture_image_processing/blob/master/work05_res/1.png)  

図2 判別分析法により2値化した画像

