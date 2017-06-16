# Ruby 題

## 1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。

常數是大寫英文字母開頭，model、class的等名稱都是常數
```ruby
class Bird
  def say_hello
  puts "Hello.I'm a bird."
  end
end
```
變數是小寫英文字母開頭，或是前方加上符號，成為其他功能變數。

## 2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?

hash[:key]會使用symbol來存取，使用字串會產生空字串
```ruby
profile = { name: "Sara", age: 20}
puts profile[:name] #Sara
puts profile["name"] #nil
```

## 3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
 ```ruby
 puts [*1..100].sample(5)
 ```

## 4.試說明在 Ruby 裡 public、protected 與 private method 的差別。
 public任何人都可以呼叫
 
 protected允許相同類別的呼叫
 
 private method只有類別內部可以呼叫

# Rails 題

## 1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
gem 'devise'
gem install Faker
gem "rails", "5.0.1"
只要在Gemfile中加上 gem '套件'，並且加上套件版本，在SSH裡執行bundle install，就可以順利安裝此套件。

## 2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?

User.find_by(id: 1)可以找到id:1號使用者，若找不到該id使用者，會回傳nil
User.find(1)可以找到id:1號使用者，會產生 ActiveRecord::RecordNotFound

## 3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?

選擇 4.0.3 以上，但 4.1 以下（不含4.1）的最新版本。

## 4.請簡述什麼是 N+1 問題? 又該怎麼解決它?

假設要找出10筆使用者ID，要先執行1次搜尋出10個使用者，再執行10次取得使用者ID，總共會執行11次，
若查詢資料量大，會影響效能。 可以使用include取出所有資料再作查詢。

# Git 題
## 1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
Add a file named ".keep" in the empty folder.
And I can commit the folder.
The folder  gets into version control.

## 2.在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
使用Heroku，並加入ENV[] variable
