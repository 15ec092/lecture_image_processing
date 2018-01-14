# 課題１０レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG = imread('momiji.png'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img10.png?raw=true)  
図1 原画像

edgeコマンドを使いプレウィット法でエッジ抽出する．

IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）

エッジ抽出後の画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai10_1.png?raw=true)  
図2 プレウィット法

edgeコマンドを使いソベル法でエッジ抽出する．

IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）

エッジ抽出後の画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai10_2.png?raw=true)  
図3 ソベル法

edgeコマンドを使いキャニー法でエッジ抽出する．

IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）

エッジ抽出後の画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai10_3.png?raw=true)  
図4 キャニー法

図を比較するとプレウィット法とソベル法では結果にあまり差がないが，キャニー法では前二つの処理と違い背景部でもエッジ抽出が行われていることがわかる．