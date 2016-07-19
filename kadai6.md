# 課題6レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work03_res/0_mono.png)  

図1 モノクロ化した原画像

次に、図1で表示した画像を

> IMG = ORG > 128;

によって輝度値が128を超える画素を1(白),そうでない画素を0(黒)として2値化した画像を図2に示す.

![2値化画像(128)](https://github.com/Shalter774/lecture_image_processing/blob/master/work06_res/1_128.png)

図2 輝度128をしきい値として2値化した画像

次に,MATLABのdither関数を用いて2値化した画像を図3として示す.

![2値化画像(ディザ)](https://github.com/Shalter774/lecture_image_processing/blob/master/work06_res/2_dither.png)

図3 ディザ法により2値化した画像

図2と図3を比較すると,固定のしきい値で2値化した図2よりも,  
ディザ法による2値化を行った図3の方が図1のモノクロ画像を忠実に再現していることがわかる.

