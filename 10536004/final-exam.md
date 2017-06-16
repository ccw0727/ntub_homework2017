# 期末考

## 簡答題(40 分，每題 4 分)

請將簡答題的答案存成檔案 `final-exam.md` 在個人資料夾中，並發 PR 至 `final-exam` 分支。

### Ruby 題

1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。

變數可以用任意字串命名，非英文亦可，常數必須要用大寫英文字母當作開頭

2. 請問 `hash[:key]` 跟 `hash["hash"]` 有什麼差別?

hash[:key] :key 是Symbol 類別的實體(物件)，得到該hash key value
hash["hash"] "hash" 是字串，得到nil

3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？

puts [*1..100].sample(5)
陣列內容為1到100，從中挑出5個元素，sample挑出來的數字不會重複，並輸出新的大小為5的陣列

4. 試說明在 Ruby 裡 `public`、`protected` 與 `private` method 的差別。

public 由類別產生的實體可以存取
protected 只能在類別內部或子類別內部存取
private 只有類別內部才可以存取

### Rails 題

1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。

simple_form 語法上比較簡潔、自動帶入css樣式、顯示上比較好看
bcrypt 密碼加密，提高帳號密碼的安全性
devise 登入套件，快速建立登入系統功能

2. 請問 `User.find_by(id: 1)` 跟 `User.find(1)` 這兩個寫法有什麼差別?

find_by 尋找要查詢的欄位，id欄位，值是1的資料，若找不到回傳nil
find 查id欄位 User.find(1) 找id是1的資料，找不到會出錯，回傳找不到

3. Gemfile 裡 `gem 'sass-rails', '~> 4.0.3'` ，後面的 `"~> 4.0.3"` 是代表什麼意思?

"~> 4.0.3"代表版本號，使用套件時選用4.0.3以上，4.1以下(不包括4.1)的最新版本

4. 請簡述什麼是 N+1 問題? 又該怎麼解決它?

n+1 queries 是指說假設有顧客和訂單的資料表，現在要查對應的訂單，在這個情況下，會先去資料庫找出所有顧客的資料(u_id)(第一次),再去   查詢n筆對應的訂單資料(o_id)，那麼就會造成n+1 query問題產生
    Rails裡可以使用include或joins的方式
        include把select查詢的指令變成兩條，第一條一樣先找出顧客id，第二條是找訂單id，查詢條件的參數包含前面找到的所有顧客id
        joins是把所有訂單資料包含顧客id的資料抓出來
        差別在於include需要顧客和訂單資料表來查詢，而join只需要訂單資料表即可

### Git 題

1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?

加入一個檔案，然後commit，上傳github
可以加入readme或是.gitignore，Git系統檔可以設定忽略什麼檔案不要上傳，確保除了.gitignore之外，其他都不會上傳

2. 在 Rails 專案中，`/config/database.yml` 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?

使用.gitignore，在專案上使用
