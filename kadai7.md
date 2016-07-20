# 課題7レポート

標準画像「Pepper」を原画像とする．この画像は縦256画素，横256画素による正方形のディジタルカラー画像である．

> ORG=imread('image/Pepper.bmp');  
> ORG= rgb2gray(ORG);  
> imagesc(ORG); colormap(gray); colorbar;

によって，原画像を読み込み，モノクロ化して表示した結果を図1に示す．

![モノクロ化した原画像](https://github.com/Shalter774/lecture_image_processing/blob/master/work07_res/0_mono.png)  

図1 モノクロ化した原画像

次に、図1で表示した画像のヒストグラムを

> imhist(ORG);

によって表示した結果を図2として示す。


![hist](https://github.com/Shalter774/lecture_image_processing/blob/master/work07_res/1_hist.png)

図2 モノクロ化した原画像のヒストグラム

このヒストグラムの最小値と最大値を

> mn = min(ORG(:));   
> mx = max(ORG(:)); 

によって求めると,mn(最小値)は2,mx(最大値)は227という値になった．

次に

> ORG = (ORG-mn)/(mx-mn)*255;

によって各画素がもつ値を0から255までの間までのレンジに拡大する.  
この時点で,最小値2であった画素は0になり,最大値227であった画素は255になる.  
それ以外の画素は0から255の間の実数をもつ.  
レンジを拡大した後の画像を図3として示す.

![hist](https://github.com/Shalter774/lecture_image_processing/blob/master/work07_res/2_mono-ranged.png)

図3 レンジ拡大後のモノクロ画像

次に

> ORG = uint8(ORG);

によってそれぞれの画素が保持している実数を整数にマッピングする.  
uint8関数の値の範囲は0から2^8-1であるので,レンジを拡大し,最小値が0,最大値が255であるこのヒストグラムにおいては,  
整数値には影響を与えず,実数値を直近の整数値に変換する動作となる.  
変換後のヒストグラムを図4として示す.

![hist](https://github.com/Shalter774/lecture_image_processing/blob/master/work07_res/3_hist-ranged.png)

図4 整数マッピング後のヒストグラム

図2と比較すると,出現頻度のバランスは変わらないが,0から255まで拡大しているのが分かる  
また,再度このヒストグラムの最小値と最大値を

> mn2 = min(ORG(:));  
> mx2 = max(ORG(:));

によって求めると,mn2(最小値)は0,mx2(最大値)は255という値になった．

