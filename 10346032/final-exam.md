Ruby 題

1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。


   常數有命名慣例，開頭必須是大寫字母，另外與其他語言不同的是常數是可變動的。
   

2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?


hash["hash"]需要有ActiveSupport::HashWithIndifferentAccess 這個套件才能執行，但本質上他們兩個是一樣的東西。


3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？


 puts [*1..100].sample(5)
 


4.試說明在 Ruby 裡 public、protected 與 private method 的差別。


public就是所有的人都可以直接存取，private是只有在類別內部才可以存取；
而protected差不多是在這兩者之間，比private寬鬆一些，但又沒有public那麼自在，
protected在同一個類別內或是同一個package，或是繼承它的子類別可以自由取用，但如果不是的話則不可存取。(只要沒指定receiver就不會發生錯誤)


Rails 題

1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。


  a.gemfile裡面全都是gem的程式
  b.他下載東西非常方便，只需要打gem install +套件名稱
  c.使用原因:因為上課老師教學使用


2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?


 find_by 方法如果找不到指定 id 的資料，僅會回傳 nil 物件，
 find 方法會直接產生 ActiveRecord::RecordNotFound 的例外訊息，例如搜尋一個不存在的User編號 1：


3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?


這是指會選用 4.0.3以上，但 4.1.0 以下（不含括 4.1）的最新版本。

4.請簡述什麼是 N+1 問題? 又該怎麼解決它?


a.N+1問題就是一種減慢資料庫效能的問題，例如:vote裡面的這行程式@candidate = Candidate.find_by(id: params[:id])重複了很多次 
b.加上include


Git 題

1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?


先另外儲存在隨身碟，再看看可不可以用一個替代的資料夾進去

2.在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?

雜湊加密
