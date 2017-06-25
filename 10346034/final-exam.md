Ruby 題
1.Q:試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
  A: 在 Ruby裡常數不需要特別宣告它是常數，但在 Ruby 對常數有特別的命名規定，就是「常數必須要是大寫英文字母開頭」，在 Ruby裡使用變數，不需要特別宣告或是指定型態，直接拿來用就可以了。在變數命名規則上，常見會使用英文字母、數字或底線的組合。或是想要用非英文字也可以。
2.Q:請問 hash[:key] 跟 hash["hash"] 有什麼差別?
 A: 如果想要取得Hash 的內容，還是得用 Symbol 來存取，使用puts hash[:key]可以傳出key的內容，但puts hash["hash"]無法傳出內容。
3.Q:如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
  A:p (1..100).to_a.shuffle.first(5)
4.Q:試說明在 Ruby 裡 public、protected 與 private method 的差別。  
  A: public就是所有的人都可以直接存取，private是只有在類別內部才可以存取；而protected就介於public跟private中間，沒private嚴謹，但又沒有public那麼自由，protected在同一個類別內或是同一個package，或是繼承它的子類別可以自由取用，但如果不是的話則不可存取。
 
Rails 題
1.Q:請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
  A:要安裝套件超簡單的
    gem "rails", "5.0.1"
    快速安裝且可確立版本
    gem 'uglifier', '>= 1.3.0' 
    安裝大於或等於 1.3.0 版本
    gem 'coffee-rails', '~> 4.1.0' 
    是指會選用 4.1.0 以上，但 4.2 以下（不含括 4.2）的最新版本
2.Q:請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
  A:這兩種方式都可以找到編號是 1 號。差別是 find_by 方法如果找不到指定 id 的資料，僅會回傳 nil 物件，但 find 方法會直接產生 ActiveRecord::RecordNotFound 的例外訊息。

3.Q:Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
  A:是指會選用 4.0.3 以上，但 4.1 以下（不含括 4.2）的最新版本
4.Q:請簡述什麼是 N+1 問題? 又該怎麼解決它?
  A:假設User有10筆，這程式會產生出11筆Queries，一筆是查User，另外10筆是一筆一筆去查Car，嚴重拖慢效能。
    加上includes
 
Git 題
1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?

2.在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?

