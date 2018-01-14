# 課題４レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG = imread('momiji.png'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img4.png?raw=true)  
図1 原画像

コマンド「imhist」によって画像のヒストグラムが標示される．

imhist(ORG); % ヒストグラムの表示

ヒストグラムを図２に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai4.png?raw=true)  
図2 ヒストグラム

このヒストグラムから，使用したmomijiの画像には薄めの灰色の画素が特に多く含まれていることがわかる．
