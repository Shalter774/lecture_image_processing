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

図3と図4を比べると,図3ではノイズが残っているだけでなく,全体がぼやけた印象の画像となっているが,図4ではノイズが残っておらず,また図3にあるようなぼやけた印象はない.  
これは,平滑化フィルタでは,着目画素の濃度値をその周辺の画素の平均とするのに対し,メディアンフィルタでは着目画素とその近傍画素の濃度の中央値としているためである.
