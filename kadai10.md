# 課題10レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work10_res/0_mono.png)  

図1 モノクロ化した原画像

次に、図1で表示した画像をプレウィット法・ソベル法・キャニー法によってそれぞれエッジ抽出を行う。  
プレウィット法を図2,ソベル法を図3,キャニー法を図4として示す

![プレウィット法](https://github.com/Shalter774/lecture_image_processing/blob/master/work10_res/1_edge-prewitt.png)  

図2 プレウィット法によるエッジ抽出

![ソベル法](https://github.com/Shalter774/lecture_image_processing/blob/master/work10_res/2_edge-sobel.png)  

図3 ソベル法によるエッジ抽出

![キャニー法](https://github.com/Shalter774/lecture_image_processing/blob/master/work10_res/3_edge-canny.png)  

図4 キャニー法によるエッジ抽出

