# 課題１レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG=imread('momiji.png'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img8.png?raw=true)  
図1 原画像

まず、閾値を128として二値化した画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai8_1.png?raw=true)  
図2 128で二値化


コマンド「bwlabeln」で画像にラベリング処理を施せる．

IMG = bwlabeln(IMG);

ラベリングした画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai8_2.png?raw=true)  
図3 ラベリング

図3を見ると、図2における「黒い部分に囲まれた白い部分」に青以外の色が着けられていることがわかる．