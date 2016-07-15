# 課題2レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

ORG=imread('image/Pepper.bmp');  
ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，グレースケール化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work02_res/0_mono.png)  

図1 モノクロ化した原画像

次に、図1で表示した画像を

> IMG = ORG>128;

によって2階調化する。2階調化した画像を図2として示す。

![2階調化したモノクロ画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work02_res/1.png)

図2 2階調化したモノクロ画像

同様に、4階調は

> IMG0 = ORG>64;  
> IMG1 = ORG>128;  
> IMG2 = ORG>192;  
> IMG = IMG0 + IMG1 + IMG2;

8階調は

> IMG0 = ORG>32;  
> IMG1 = ORG>64;  
> IMG2 = ORG>96;  
> IMG3 = ORG>128;  
> IMG4 = ORG>160;  
> IMG5 = ORG>192;  
> IMG6 = ORG>224;  
> IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;

として表すことが出来る。4階調化したものを図3、8階調化したものを図4として示す。

![4階調化したモノクロ画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work02_res/2.png)

図2 4階調化したモノクロ画像

![8階調化したモノクロ画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work02_res/3.png)

図2 8階調化したモノクロ画像




IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

![原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work01_res/1.png)  
図2 1/2サンプリング

同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．すなわち，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

とする．1/4サンプリングの結果を図３に示す．

![原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work01_res/2.png)  
図3 1/4サンプリング

1/8から1/32サンプリングは，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

を繰り返す．サンプリングの結果を図４～６に示す．

![原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work01_res/3.png)  
図4 1/8サンプリング

![原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work01_res/4.png)  
図5 1/16サンプリング

![原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work01_res/5.png)  
図6 1/32サンプリング

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
