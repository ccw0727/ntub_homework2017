# 期末考

## 簡答題(40 分，每題 4 分)

### Ruby 題

1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
Ruby 中的常數 會是以大寫符號開頭，修改警告；變數 前面大部分會加符號表示區域，兩個最大差別就是常數不會受到變數區域限制

2. 請問 `hash[:key]` 跟 `hash["hash"]` 有什麼差別?
在 Rails Controller 裡面 是沒有差別，一個用字串，因為Hash 有ActiveSupport::HashWithIndifferentAccess 這個類別 所以
`hash[:key]` 跟 `hash["hash"]` 都是通的，但""是字串的格式

3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
puts (1..100).to_a.sample(5)

4. 試說明在 Ruby 裡 `public`、`protected` 與 `private` method 的差別。
public 公開都可以存取
private 只有它類別裡面才可以存取
protected 同個類別、package、繼承它的子類別可以存取

### Rails 題

1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
gem 'devise', 真的太厲害可以自動弄出會員系統，不用再另外做一堆重複的雜工 
gem 'puma', 它可以幫助網頁scss給 stylesheets才會好看
gem 'sqlite3' , 主要是紀錄sqlite的資料庫

2. 請問 `User.find_by(id: 1)` 跟 `User.find(1)` 這兩個寫法有什麼差別?
功能是差不多的
User.find(1) 是透過model 來查詢id 查不到會ActiveRecord::RecordNotFound
User.find_by(id: 1) 是遞參數找 找不到就會nil

3. Gemfile 裡 `gem 'sass-rails', '~> 4.0.3'` ，後面的 `"~> 4.0.3"` 是代表什麼意思?
就是我的 sass-'rails' 指安裝到 4.0.3 版本 

4. 請簡述什麼是 N+1 問題? 又該怎麼解決它?
在資料庫查詢中迴圈大量查詢N筆資料，再加上開頭查詢的那1筆，稱為N+1。
解決方法就是用 join 和 include 搭配 where 來查詢符合條件 就不會重複上一筆大量迴圈


### Git 題

1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
我會新增一個空檔 讓它可以加入 git

2. 在 Rails 專案中，`/config/database.yml` 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
要忽略可以在 database.yml 檔案裡最後加上.gitignore 就不怕被看到 



