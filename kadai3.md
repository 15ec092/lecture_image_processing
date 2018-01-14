# 課題３レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG = imread('momiji.png'); % 画像の読み込み
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img3.png?raw=true)  
図1 原画像

以下のプログラムによって輝度値が64より高い画素が１（白），それ以外の画素が０（黒）に変換される．

IMG = ORG>64;

閾値処理された画像を図２に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai3_1.png?raw=true)  
図2 閾値処理結果（64）

同様のプログラムで閾値を96，128，192とし，それぞれの場合の閾値処理された画像を以下に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai3_2.png?raw=true)  
図3 閾値処理結果（96）

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai3_3.png?raw=true)  
図4 閾値処理結果（128）

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai3_4.png?raw=true)  
図5 閾値処理結果（192）

このように閾値を高く設定するほど０と判定される画素数が増えるため、画像に黒い部分が多くなる．
