# 期末考

## 簡答題(40 分，每題 4 分)

### Ruby 題

1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。


常數和變數類似，數值可以變，但開頭大寫的變數就是常數

2. 請問 `hash[:key]` 跟 `hash["hash"]` 有什麼差別?

`hash[:key]` :key是symbol，因為不能改變，加上找和比較的速度比字串還快，很適合用來當 Hash 的 Key。

`hash["hash"]` "hash"是字串，但是單純要輸出"內容"，選字串又比較快速，畢竟symbol還是要轉成字串輸出。

3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
```ruby
puts [*1..100].shuffle.first(5)

先shuffle，再用first取前5個數字
```
4. 試說明在 Ruby 裡 `public`、`protected` 與 `private` method 的差別。

`public`是預設的，任何地方都可以使用，沒有限制。

`protected`比`private`寬鬆一點，只能在自己的類別(或是他的子類別)使用，但與他相較就是也能在instance method被使用(class method不能)。

`private`不能指定接收者，也就是是說只能在自己的類別(或是他的子類別)使用。



### Rails 題

1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
2. 請問 `User.find_by(id: 1)` 跟 `User.find(1)` 這兩個寫法有什麼差別?
3. Gemfile 裡 `gem 'sass-rails', '~> 4.0.3'` ，後面的 `"~> 4.0.3"` 是代表什麼意思?
4. 請簡述什麼是 N+1 問題? 又該怎麼解決它?

### Git 題

1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
2. 在 Rails 專案中，`/config/database.yml` 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
