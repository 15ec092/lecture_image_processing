# 課題６レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG = imread('momiji.png'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img6.png?raw=true)  
図1 原画像

まず、閾値を128として二値化した画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai6_1.png?raw=true)  
図2 128で二値化

コマンド「dither」で画像をディザ法で二値化できる．

IMG = dither(ORG); % ディザ法による二値化

ディザ法による二値化の結果を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai6_2.png?raw=true)  
図3 ディザ法で二値化

ディザ法により二値化された画像は黒い点の密集具合で擬似的に濃淡が表現されていることがわかる．