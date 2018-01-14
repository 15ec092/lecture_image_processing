# 課題２レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG=imread('momiji.png'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img2.png?raw=true)  
図1 原画像

以下のプログラムによって輝度値が128より高い画素を１（白），それ以外の画素を０（黒）とした２階調の画像が生成される．

IMG = ORG>128;

生成された２階調の画像を図２に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai2_1.png?raw=true)  
図2 ２階調の画像

以下のプログラムによって輝度値が192より高い画素を3（白），128より高い画素を2，64より高い画素を1，それ以外の画素を０（黒）とした４階調の画像が生成される．

IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;

生成された４階調の画像を図３に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai2_2.png?raw=true)  
図3 ４階調の画像

以下のプログラムによって輝度値が224より高い画素を7（白），192より高い画素を6，160より高い画素を5，128より高い画素を4，96より高い画素を3，64より高い画素を2，32より高い画素を1，それ以外の画素を０（黒）とした８階調の画像が生成される．

IMG0 = ORG>32;
IMG1 = ORG>64;
IMG2 = ORG>96;
IMG3 = ORG>128;
IMG4 = ORG>160;
IMG5 = ORG>192;
IMG6 = ORG>224;
IMG = IMG0 + IMG1 + IMG2 + IMG3 + IMG4 + IMG5 + IMG6;

生成された８階調の画像を図４に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai2_3.png?raw=true)  
図4 1/8サンプリング

このように階調数が多いほど濃度変化の表現力が上がり，量子化間隔が細かいほど階調表現が滑らかになる．
