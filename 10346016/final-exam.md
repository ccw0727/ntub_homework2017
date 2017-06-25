# Ruby

1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
```ruby
NAME = "NAME" # 常數是以大寫英文開頭,盡量不要去改變他的值
name = "name" # 變數是以小寫英文開頭,可以改變他的值
```

2. 請問 hash[:key] 跟 hash["hash"] 有什麼差別?
```ruby
data = {"name":"john","age":18}
data[:name] # john
data["name"] # nil
```
3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
```ruby
(1..100).to_a.sample(5)
```

4. 試說明在 Ruby 裡 public、protected 與 private method 的差別。
```
public : 任何人都能夠存取
protected : 
```
# Rails

1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
```
只需要貼上要使用的套件就會幫我們匯入
```

2. 請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
```
前面一個是會回傳符合條件式"集合"
後面則是只會回傳一筆
```

3. Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
```
能夠使用大於4.0.3的安定版本(如果有的話),不然就使用4.0.3
```

# Git

1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
```
在該資料夾加入.gitkeep
```

2. 在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
```
在.gitignore檔案中加入"/config/database.yml",這樣git就不會追蹤他了,缺點就是從另外一台clone下來時,這個檔案要另外給(因為沒有被push上去)
```