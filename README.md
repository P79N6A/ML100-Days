# ML100-Days
機器學習百日馬拉松

Day 1: 當我們遇到一個問題時，不見得要馬上跳進去玩耍；
	
	我們要先思考問題，知道目的，如果有資料，還可以概略看一下資料，盤算能夠作出甚麼有趣有用的結果。
	如果沒有資料，就問題的思考後，才去採集資料，相對可以節省很多時間。
	
	之後我們才會盤算一個策略去進行行動，比如快速完成一個方案，一個最小可行方案(Minimum Visiable Product 的概念)，後續進行優化改善。
	
	HW: 除了第一天的簡易練習 編寫 Y=wX+b，plot(X,Y) 定義 mse, mae 還有一個很重要的工作，作業2：如果你今天經營一個台灣大車隊，你要如何透過數據分析來提升業績? 思考一下，我們除了需要工程師也需要資料分析師與科學家。


Day 2: 第一次資料探勘

	好我們前十六天都將進行資料數據前處理的工作，練習的問題會是 Kaggle 上的題目 
	https://www.kaggle.com/c/home-credit-default-risk/data 
	
	會用到的應該是 application_train.csv 與 application_test.csv 
	最後要上傳時會用到 submission.csv 
	但是請不要忘了研讀 HomeCredit_columns_description.csv 
	
	HW:
	第二天我們開始讀取資料，對於這個被整理好的 Dataframe 進行最初步的探勘，比如說知道有多少筆資料，有多少 "欄" 的特徵，如何將特徵項目組成一個 list， 又或者我們該如何呈現截取部分資料等。總之，我們還沒有跳進去觀察個別特徵，個別資料前，我們所採取的動作在今天試著作一輪。
	第二天還有一個有趣的參考作業，讀一讀吳老師的資料探勘講義，其中為何要研究杜河的魚類又如何進行都是很有意義的練習，川普的故事也趣味十足。
	
Day 3: 關於 DataFrame
	
	我們在作資料清理，在處理機器學習的問題時，常常都要熟練 DataFrame 的操作，DataFrame 就像是 EXCEL 的 Spreadsheet 一樣，第一列存著的是所有欄位名稱，就是我們未來要處理的特徵。第二列起就是一筆一筆的資料。
	
	HW: 第三天的練習會比 pandas 的 DataFrame 多一點不同格式的東西，大家好好努力!
	
Day 4: EDA 資料類型介紹

	我們在第二天開始進行了 EDA 資料探勘的動作，當時是看整個資料的外型，有多少特徵有多少筆資料，今天起我們要開始一步一步的觀察特徵資料。
	
	跳進特徵研究的第一個小動作就是要知道，每一個特徵的格式，也就是資料的類別；基本的類別有 float64, int64, object。
	
	要留意 object是我們的機器無法直接處理的資料類型，所以今天是介紹為這類資料作編碼，編碼完後才會送進機器模型運算。
	
	HW: 請研讀參考資料 https://medium.com/@contactsunny/label-encoder-vs-one-hot-encoder-in-machine-learning-3fc273365621
	，同時完成第四天的程式。
	
Day 5: EDA之資料分布

	EDA 當然沒有固定的程序進行，但是對於新手而言，對於十個出頭的特徵的經典題目 Titanic 都已經是不知道如何下手了，更何況今天的題目有百餘個特徵。所以如果有一個按部就班的程序可以遵循，在新手時期是十分珍貴的。
	
	今天算是第三天的 EDA，Day 2時是第一次看資料框架(有多少資料，是寬的胖的高的瘦的)，Day 4 時是觀察這些特徵的資料類型，今天我們要來看看特徵資料的統計特性，
	計算集中趨勢
		•平均值 Mean
		•中位數 Median
		•眾數 Mode 
	計算資料分散程度
		•最⼩值 Min
		•最⼤值 Max
		•範圍 Range
		•四分位差 Quartiles
		•變異數 Variance
		•標準差 Standard deviation
		
	HW: 今天的作業是挑三個有興趣的特徵來看它們的統計特性，挑選的方式可以是在 Day 2時的 HomeCredit_columns_description.csv 研讀時對於特徵了解而挑選，如果挑很多個，最後也可以用 sns.heatmap(corr()matric) 的關係來挑選。
	今天要學會 DataFrame.describe() 來看基本統計資料。也要學會畫直方圖 (histogram) by plt.hist
	
Day 6: EDA 與 outlier檢查  

	面對異常值 outlier 我們要思考，為什麼會有 outlier?  該如何判斷是異常值 outlier? 還有要如何處理異常值 outlier? 
	要解決一個問題，是不能閃躲與心存僥倖的，資料科學家與工程師花了無數時間處理的案子，如果我們只想要在短短的三個小時到四個小時作完，同時期待卓越成果，這樣的期待是有些夢幻的，不切實際的。所以 Day 5 我們挑三個特徵觀察，那真的只是前菜，開胃菜，熟悉溫度氣味而已。
	對決是要通盤面對，所以今天要深入每一個數值資料特徵項目，畫出 boxplot 然後通通都去看，有沒有奇怪的離群索居的資料遠遠的孤傲站著? 
	我們要找出他們思考他們的合理性否，判斷時候要作修正要如何修正。
	HW: 完成今天的程式。
	
Day 7: 常⽤數值取代：中位數與分位數 連續數值標準化 
	
	第七天要來看遇到缺失值或異常值要作的補值方式。請大家 google 中位數、分位數、眾數與平均值的定義與計算，同時今天的作業中有計算 Normalize function (to -1 ~ 1)，這樣的處理是要讓所有特徵立於平等地位，不會有些特徵單位大，有些特徵單位小，然後產生不對等的影響。
	
	HW；完成今天的程式，了解中位數、分位數、眾數與平均值與標準化。
	
Day 8: 常⽤的 DataFrame 操作 

	第八天不算是 EDA，是對 pandas的認識與 DataFrame 操作的練習日。就請大家作完作業，也上網找一些 DataFrame 的介紹。
	除非偷懶只走深度學習，不然不熟悉 DataFrame是會讓人十分辛苦了。
	
Day 9: 今天沒有作業，在介紹相關係數。

	相關係數是⼀個介於 -1～1 之間的值，負值代表負相關，正值代表。
	有請大家自己上網估勾一下。第十天會練習。
	
Day 10: 相關係數實作

	延續第九天的介紹，開始進行相關係數的應用。
	這兩天似乎作不多，內容也輕鬆，所以我們剛好喘一口氣來回顧至今的 EDA，避開學習中的見樹不見林，
	• Day 2: 我們第一天進行 EDA，是從資料的筆數、欄位多寡開始認識我們手中有多少東西。當然不要忘了我們也閱讀的欄位的描述文件。
	• Day 4: 我們開始跳進去欄位去看所有欄位的資料格式，查看是浮點數、整數或物件資料。對於類別型資料我們馬上進行編碼工作。
	• Day 5: 我們學習繼續留在欄位中觀察他們的基本統計資料。
		我們可以這麼說，
		Day 4 用 app_train.dtypes.value_counts() 與 app_train.select_dtypes(include=["object"]).apply(pd.Series.nunique, axis = 0) 來了解各種資料型態的個數與找出所有類別型資料與檢視類別型欄位各自類別的數量。
		Day 5 是用 .describe() 看欄位資料的統計特徵與用 plt.hist() 去劃出直方圖 histogram 讓我們認識欄位資料。
	• Day 6: 在經過 Day 5 的統計資訊觀察後，我們在 Day 6就要初步判斷是否有 outlier，這次有用到 boxplot 圖。
	• Day 7: 跟 Day 6 是連續動作，對於一些 outlier 的處理，同時當個別欄位資料的 outlier 都處理的，我們也不希望整體的欄位中有某幾個因為單位不依樣因為數值特別大讓我們後續模型運算時有不平衡的影響，所以就一併作了標準化。
	• Day 9, 10: 當我們基本資料觀察與修正了之後，我們就展開了所有特徵值(欄位資料)對於 目標 的相關運算。
	
	HW: 既然是實作，第十天的主要工作就是好好地進行作業，主要是把資料型態為 Object 都進行了 one hot encoding 都成為了數字，然後與 Target 作 相關性計算，我們作了 corr()，不送進 sns.heatmap 因為實在太多了特徵值了，會畫很久喔! 然後挑出最大的幾個來觀察。
	今天的觀察有把同一個特徵在目標為 1 與目標為 0 去查看一下有沒有分布上的不同，然後去思考觀察一些現象。同時也建議同學在 https://www.kaggle.com/c/home-credit-default-risk/data 的最下方 application_test.csv (5.58 MB)的表格玩一玩，可以很方便地觀察到一些資訊!
	
Day 11: 繪圖與樣式＆Kernel Density Estimation (KDE) 

	在第十天的作業中，最後一個任務，我們不只觀看一個特徵的分布以及他與目標的相關性，我們也將該特徵分拆觀察，觀看不同目標結果的特徵子集合的特性。第十一天也繼續往分拆特徵進入特徵子集合的觀察前進。
	第十一天內容分成兩個部分介紹，
	• 介紹 KDE，我有在網路上查到這個 "kernel density estimation is a way to estimate the probability density function (PDF) of a random variable in a non-parametric way" 果然，KDE 就是對 pdf 估算的方法。如果我們用 sns.kdeplot() 去看圖，會得到一條連續數值的曲線，如果用 sns.distplot() 去畫圖，就會得到該條曲線與個別值的相對機率，後者(個別值的相對機率) 長得很像直方圖，請同學思考他跟直方圖的關係！
	• 第二個內容介紹就是前面提到的將特徵分群拆成好多個子集合子群分別觀察 KDE。
	
	這些微細的觀察都是讓我們對於觀察對象及其特徵更清楚的認識與掌握。
	
	HW: 上面的描述很多都是在解釋第十一天的作業，有些我也還在努力觀察中，加油。
	
Day 12: 把連續型變數離散化 

	第十二天沒有作業，內容也簡單，就是 ptt 肥宅愛用的詞用上了: "如題" 把連續型變數離散化。
	在第十一天的作業最後一部分，採用了 barplot，觀察出 "年紀愈輕" failed to repay 的可能性愈大，當然我們也可以直接用連續數值，但是把他離散化有助於把問題簡單化，想想我們有好多特徵值，似乎問題很複雜啊！同時~~ 也可以將 outlier 解決掉，將300歲歸為最大歲數那一類(這樣對嗎?) 
	通常，我們的分群有三個方法等寬，等頻，等類。
	我們第十三天的作業會用到等寬，等頻。 等類我還沒好好研究。
	這裡提示一些好應付 Day 13，
	pd.cut(Data_feature, bins = 整數值 n ) 這就是等寬，會從最小值到最大值等分成 n 個區間。
	pd.qcut(Data_feature, bins = 整數值 n) 這就是等頻，會從最小值到最大值分成 n 個區間，每個區間沒有意外就會都有一樣的樣品數量。
	大家可以思考一下，為什麼我不是說一定數量，而是加了一句沒有意外的話。
	

Day 13: 把連續型變數離散化  
	
	在第十三天後，EDA 的學習就快要近尾聲了(但還沒尾聲啦)。第十三天就是根據第十二天的內容好好地完成作業。
	
Day 14: 把連續型變數離散化  
		
	第十四天的主要在學習另一個視覺化的技巧，讓好些個序列的圖表，相關聯的圖表有結構的排列比對，可以協助我們更好觀察。
	HW: 對於 python 不熟悉的同學，會吃力，但是也就是提供更多練習機會讓大家提升跟上同學。加油。
	
Day 15:　Heatmap & Grid-plot   

	在 Day 13 時我們說近尾聲是真的，但是第十五天的觀察真的是重要。 
	sns.heatmap(corr()) 先前就作過，但是仍然重要。
	sns.sns.PairGrid() 更是有趣的讓我們作出一個相關圖但是其相關觀察可以有我們決定。

Day 16: 模型初體驗 Logistic Regression 

	好了，我們要上 Kaggle 了，第十六天請大家作幾個任務，
	◆ 自己上網查看 sklearn Imputer 在幹嘛。
	◆ 請大家上網查看李宏毅老師(hung yi lee) 的教學影片或吳恩達老師(Andrew Nq) 的教學影片學習甚麼是 Logistic Regression。
	◆ 請大家上網查看 sklearn LogisticRegress 怎麼用
	◆ 大家互相澄清一下 Logistic Regression 到底是迴歸法(Regression) 還是分類法(Classification)?
	◆ 請大家拿出 Day 2 的 submission.csv 準備，寫完作業後比對一下格式。 
	
	HW: 就是把作業寫完，準備上 Kaggle 吧！ 
	作業產生的格式與 submission.csv 一不一樣? 這樣上傳有沒有問題? 如果有問題，怎麼辦? 
	還有Kaggle 上傳的方式，請上網 Google！
	
	
	
	
	
	
