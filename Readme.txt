20201029電子書收藏

	C/C++語言常用標準庫
		<asset.h>
		<ctype.h>
			nt isalpha(c) c是字母字符
			int isdigit(c) c是數字字符
			int isalnum(c) c是字母或數字字符
			int isspace(c) c是空格、製表符、換行符
			int isupper(c) c是大寫字母
			int islower(c) c是小寫字母
			int iscntrl(c) c是控製字符
			int isprint(c) c是可打印字符，包括空格
			int isgraph(c) c是可打印字符，不包括空格
			int isxdigit(c) c是十六進制數字字符
			int ispunct(c) c是標點符號
			int tolower(int c) 當c是大寫字母時返回對應小寫字母，否則返回c本身
			int toupper(int c) 當c是小寫字母時返回對應大寫字母，否則返回c本身	
		<errno.h>

		<float.h>
		<limits.h>
		<locale.h>
		<math.h>
			三角函數
			sin
			cos
			tan
			反三角函數
			asin
			acos
			atan
			雙曲函數
			sinh
			cosh
			tanh
			以e為底的指數函數exp
			自然對數函數log
			以10為底的對數函數log10
			平方根sqrt
			絕對值fabs
			乘冪，第一個參數作為底，第二個是指數double pow(double, double)
			實數的餘數，兩個參數分別是被除數和除數double fmod(double, double)

		<setjmp.h>
		<signal.h>
		<stdarg.h>
		<stddef.h>
			類型size_t（sizeof運算符的結果類型，是某個無符號整型）；
			類型ptrdiff_t（兩個指針相減運算的結果類型，是某個有符號整型）；
			類型wchar_t（寬字符類型，是一個整型，其中足以存放本系統所支持的所有本地環境中的字符集的所有編碼值。這裡還保證空字符的編碼值為0）；
			符號常量NULL（空指針值）；
		<stdlib.h>
			int rand(void) 生成一個0到RAND_MAX的隨機整數[取亂數]
			void srand(unsigned seed) 用seed為隨後的隨機數生成設置種子值
			void *calloc(size_t n, size_t size) 分配一塊存儲，其中足以存放n個大小為size的對象，並將所有字節用0字符填充。返回該存儲塊的地址。不能滿足時返回NULL
			void *malloc(size_t size) 分配一塊足以存放大小為size的存儲，返回該存儲塊的地址，不能滿足時返回NULL
			void *realloc(void *p, size_t size) 將p所指存儲塊調整為大小size，返回新塊的地址。如能滿足要求，新塊的內容與原塊一致；不能滿足要求時返回NULL，此時原塊不變
			void free(void *p) 釋放以前分配的動態存儲塊 [動態配置記憶體]
			int abs(int n) 求整數的絕對值
			long labs(long n) 求長整數的絕對值
			div_t div(int n, int m) 求n/m，商和余數分別存放到結果結構的對應成員裡
			ldiv_t ldiv(long n, long m) 同上，參數為長整數
			double atof(const char *s) 由串s構造一個雙精度值[字串轉數值(數字)]
			int atoi(const char *s) 由串s構造一個整數值
			long atol(const char *s) 由串s構造一個長整數值
			非正常終止函數abort
			正常終止函數exit
			正常終止註冊函數atexit
			向執行環境傳送命令的函數system
			訪問執行環境的函數getenv
			二分法查找函數bsearch[(二元搜尋樹)(Binary Search Tree)]
			快速排序函數qsort
		<stdio.h>
		<string.h>
			size_t strlen(cs) 求出cs的長度
			char *strcpy(s,ct) 把ct字串複製到s。要求s指定足夠大的字符數組
			char *strncpy(s,ct,n) 把ct裡的至多n個字符複製到s。要求s指定一個足夠大的字符數組。如果ct裡的字符不夠n個，就在s裡填充空字符。
			char *strcat(s,ct) 把ct裡的字符複製到s裡已有的字符串之後。s應指定一個保存著字符串，而且足夠大的字符數組。[字串串接]
			char *strncat(s,ct,n) 把ct裡的至多n個字符複製到s裡已有的字符串之後。s應指定一個保存著字符串，而且足夠大的字符數組。
			int strcmp(cs,ct) 比較字符串cs和ct的大小，在cs大於、等於、小於ct時分別返回正值、0、負值。[字串比較]
			int strncmp(cs,ct,n) 比較字符串cs和ct的大小，至多比較n個字符。在cs大於、等於、小於ct時分別返回正值、0、負值。
			char *strchr(cs,c) 在cs中查尋c並返回c第一個出現的位置，用指向這個位置的指針表示。當cs裡沒有c時返回值NULL[字串搜尋]
			char *strrchr(cs,c) 在cs中查尋c並返回c最後一個出現的位置，沒有時返回NULL
			size_t strspn(cs,ct) 由cs起確定一段全由ct裡的字符組成的序列，返回其長度
			size_t strcspn(cs,ct) 由cs起確定一段全由非ct裡的字符組成的序列，返回其長度
			char *strpbrk(cs,ct) 在cs裡查尋ct裡的字符，返回第一個滿足條件的字符出現的位置，沒有時返回NULL
			char *strstr(cs,ct) 在cs中查尋串ct（查詢子串），返回ct作為cs的子串的第一個出現的位置，ct未出現在cs裡時返回NULL
			char *strerror(n) 返回與錯誤編號n相關的錯誤信息串（指向該錯誤信息串的指針）
			char *strtok(s,ct) 在s中查尋由ct中的字符作為分隔符而形成的單詞[字串切割/分割/切斷/分段]
			void *memcpy(s,ct,n) 從ct處複製n個字符到s處，返回s[記憶體初始化]
			void *memmove(s,ct,n) 從ct處複製n個字符到s處，返回s，這裡的兩個段允許重疊
			int memcmp(cs,ct,n) 比較由cs和ct開始的n個字符，返回值定義同strcmp
			void *memchr(cs,c,n) 在n個字符的範圍內查尋c在cs中的第一次出現，如果找到，返回該位置的指針值，否則返回NULL
			void *memset(s,c,n) 將s的前n個字符設置為c，返回s	
		<time.h>

	人工神經網絡(ANN)背後的數學原理基礎
		一、梯度下降到底在幹什麼
			1.1 求極值：傳統的方法不香嗎？
			1.2 什麼是梯度？
		二、人工神经网络（ANN）
			2.1 神經元的數學模型
			2.2 ANN是如何煉成的？
			
	機器人學
		數學基礎
		機器人運動學
		機器人動力學
		機器人控制
		
	圖解6 種「樹」[樹的資料結構 教學]

	Linux 運維必備的40 個命令總結
		01、刪除0字節文件
		02、查看進程~按內存(記憶體用量)從大到小排列
		03、查看進程~按CPU使用率從大到小排列
		04、打印cache 裡的URL
		05、查看http 的並發請求數及其TCP 連接狀態
		06、sed 在這個文裡Root 的一行，匹配Root 一行，將no 替換成yes
		07、如何殺掉MySQL 進程
		08、顯示運行3 級別開啟的服務
		09、如何在編寫SHELL 顯示多個信息，用EOF
		10、for 的巧用（如給MySQL 建軟鏈接）
		11、取IP 地址
		12、內存(記憶體)的大小:
		14、查看Apache 的並發請求數及其TCP 連接狀態
		15、因為同事要統計一下服務器下面所有的jpg 的文件的大小，寫了個SHELL 給他來統計。原來用xargs 實現，但他一次處理一部分。搞的有多個總和……，下面的命令就能解決。
		16、CPU負載
		21、磁盤I/O 負載[硬碟]
		22、網絡負載
		23、網絡錯誤
		24、網絡連接數目
		25、進程(目前程式)總數
		35、殺掉80端口相關的進程
		36、清除僵死進程
		37、tcpdump 抓包，用來防止80端口被人攻擊時可以分析數據
		39、查看有多少個活動的php-cgi 進程
		40、查看系統自啟動的服務