# 課題8レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work08_res/0_mono.png)  

図1 モノクロ化した原画像

次に、図1で表示した画像を

> IMG = ORG > 128;

によって輝度値が128を超える画素を1(白),そうでない画素を0(黒)として2値化した画像を図2に示す.

![2値化画像(128)](https://github.com/Shalter774/lecture_image_processing/blob/master/work08_res/1_128.png)

図2 輝度128をしきい値として2値化した画像

この2値画像を

> IMG = bwlabeln(IMG);  
> imagesc(IMG); colormap(jet); colorbar;

によってラベリングした画像を図3として示す.

![ラベリング画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work08_res/2_labeled.png)

図3 ラベリング後の画像

ラベリングとは,同じ連結成分に属する画素に同一番号を,異なる連結成分に異なる番号を与える処理である.  
図2と図3を比較すると、図2で白の画素は、図3では同じ連結であれば同じ色となっている。  
また,図2で黒の画素は背景と見なされ,連結していなくても図3では同じになっている.

> colormap(jet);

のjetを別なキーワードにすることでラベリングに使用する色の割り当てを変える事が出来る。