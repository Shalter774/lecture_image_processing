# 課題9レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work09_res/0_mono.png)  

図1 モノクロ化した原画像

図1で表示した画像に対して

> ORG = imnoise(ORG,'salt & pepper',0.02);

によってノイズを添付した画像を図2,図2に対して平滑化フィルタでノイズ除去した画像を図3,メディアンフィルタでノイズ除去した画像を図4として示す。

![ノイズ添付](https://github.com/Shalter774/lecture_image_processing/blob/master/work09_res/1_noise.png)  

図2 ノイズを添付した画像

![平滑化](https://github.com/Shalter774/lecture_image_processing/blob/master/work09_res/2_filter1.png)  

図3 平滑化フィルタでノイズ除去した画像

![メディアンフィルタ](https://github.com/Shalter774/lecture_image_processing/blob/master/work09_res/3_filter2.png)  

図4 メディアンフィルタでノイズ除去した画像























> IMG = ORG > 64;

によって輝度値が64を超える画素を1(白),そうでない画素を0(黒)として2値化した画像を図2に示す.

![2値化画像(64)](https://github.com/Shalter774/lecture_image_processing/blob/master/work03_res/1_64.png)

図2 輝度64をしきい値として2値化した画像

同様に、輝度が96,128,192をしきい値する場合にもそれぞれ

> IMG = ORG > 96;

> IMG = ORG > 128;

> IMG = ORG > 192;

として表すことが出来る。しきい値が96のものを図3,128のものを図4,192のものを図5として示す.

![2値化画像(96)](https://github.com/Shalter774/lecture_image_processing/blob/master/work03_res/2_96.png)

図3 輝度96をしきい値として2値化した画像

![2値化画像(128)](https://github.com/Shalter774/lecture_image_processing/blob/master/work03_res/3_128.png)

図4 輝度128をしきい値として2値化した画像

![2値化画像(192)](https://github.com/Shalter774/lecture_image_processing/blob/master/work03_res/4_192.png)

図5 輝度196をしきい値として2値化した画像

このように、しきい値とする輝度値が高いほど2値化した後の画像には黒い画素が増えることが分かる.

