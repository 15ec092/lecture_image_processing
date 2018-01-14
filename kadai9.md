# 課題９レポート

「momiji.png」を原画像とする．この画像は縦533画像，横800画素による長方形のディジタルカラー画像である．

ORG = imread('momiji.png'); % 画像の読み込み  
ORG = rgb2gray(ORG); % 白黒濃淡画像に変換  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示

によって，原画像を読み込み白黒画像にし，カラーバーと共に表示した結果を図１に示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/org_img9.png?raw=true)  
図1 原画像

imnoiseコマンドを使い，塩コショウのようなノイズを添付する．

ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付

ノイズ添付後の画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai9_1.png?raw=true)  
図2 ノイズ添付

filter2コマンドを使い，平滑化フィルタで雑音除去する．

IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去

雑音除去後の画像を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai9_2.png?raw=true)  
図3 平滑化フィルタ使用

medfilt2コマンドを使い，メディアンフィルタで雑音除去する．

IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去

雑音除去後の画像を示す．


![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai9_3.png?raw=true)  
図4 メディアンフィルタ使用

フィルタを設計し，適用する．

f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計  
IMG = filter2(f,IMG,'same'); % フィルタの適用

このフィルタの適用結果を示す．

![原画像](https://github.com/15ec092/lecture_image_processing/blob/master/image/kadai9_4.png?raw=true)  
図5 メディアンフィルタ使用

雑音の添付された画像を平滑化フィルタに通すことで白い雑音が除去されたが，フィルタに通す前よりもやや紅葉の輪郭がぼやけている．次にメディアンフィルタに通すことで黒い雑音が除去されたが，このときは輪郭部に変化はない．最後のフィルタに通すことで画像全体の色は薄くなったが輪郭部は最初と同じように鮮鋭化された．
