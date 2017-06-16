Ruby 題

(1)試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。

  常數及變數最明顯的差異在於命名規則上，常數的開大寫字母，而變數則是小寫字母。變數有不同範圍的差異，如果要求的變數不在可獲取的範圍內，
  那會產生錯誤並回報給開發者。

(2)請問 hash[:key] 跟 hash["hash"] 有什麼差別?

  hash[:key] 使用 symbol 來抓取key及value，而hash["hash"]則是使用字串來抓取，但字串抓取是 rails 為 hash 做的擴充功能。
  所以在ruby檔案中用字串抓取會抓到nil，而在rails裡則會得到正確的數值。

(3)如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？

int number[5]
	for(i=0, i<5,i++){
	  x=(rand() % 100) +1
	  for(n=0,n<5,n++){
	    if(number[n] != x){
		number[i]=x;
		};
	  };
	};
print number;  

(4)試說明在 Ruby 裡 public、protected 與 private method 的差別。

    public在ruby裡是不會被特別標註的，所以方法只要沒有被限制都會是public，當然也有例外就是initialize方法，它永遠是private的，只會被new方法呼叫。
	而public是所有的人都能提取。
    protected 則是將方法保護在A類別或同一package或繼承A類別的B類別之中。
    private 僅將方法保存在A類別之中，不做額外的分享。而在Ruby裡的private方法，只要沒有明確的指出recevier的話就都可以呼叫。
	所以在上面例子裡的Son類別，即使是呼叫父類別的private方法，只要不要有recevier，它就不會有錯誤產生。

Rails 題

(5)請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。

    rails，它支援的我們開發一個專案所需要的各種指令，能讓我們更快速地推進專案進度。
    bootstrap-sass，它提供了我們多樣的前端框架，能讓畫面變得更加美觀。
    sqlite3，它在提供了DB給ruby，讓我們開發程式時能同時將DB的表單建置完畢。

(6)請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?

    find是通過id來進行查詢，如果查詢結果為無，那會顯示錯誤訊息。而find_by則是用已知的欄位及儲存值來進行查詢，如果查詢不到則顯示nil。

(7)Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?

    選用4.0.3版本以上的sass-rails。

(8)請簡述什麼是 N+1 問題? 又該怎麼解決它?

    N+1問題 是當資料查詢總次數高時，資料庫效能較低，EX:查詢6次已加入會員姓名時，必須先查詢已加入會員，再逐次查詢對應姓名。
	通常使用includes方法，將查詢次數降低。

Git 題

(9)空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?

    使用git init

(10)在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?

  於編輯完畢後修改檔案修改權限。
