# Ruby 題
1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
### Ans:常數第一個單字大寫，變數第一個單字小寫
2. 請問 hash[:key] 跟 hash["hash"] 有什麼差別?
### Ans:hash[:key]是內建的，hash["hash"]是Rails加了ActiveSupport::HashWithIndifferentAccess的類別幫Ruby擴充的。
3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？

### Ans:
``` ruby
    print((1..100).to_a.sample(5))
    # [55,33,23,54,87]
```
4. 試說明在 Ruby 裡 public、protected 與 private method 的差別。
### Ans: public可以被外部存取，protected不能被外部存取，但是如果繼承也會被繼承下去，private就完全不能被外部存取。
## ex:
``` ruby
class dog
    def a
      # method
    end

    private
    def b
    # method
    end
end

dog.a # success
dog.b # fail 找不到b方法
```
# Rails 題
1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。

### Ans: gem devies, gem cancancan, gem simple_form
### devies會直接幫我們寫好一整套使用者的登入註冊的功能，cancancan就已經建立好使用者權限管控，simple_form就是表格畫面很快就做好，會想用他是因為，只要gem他們，在bundle install，這些功能就很快地被建立起來了，且都是常用功能。

2. 請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?

### Ans: User.find(1)就等於先撈User Model的全部資料在抓第一個，User.find_by(id: 1)就只是select id是1的

3. Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?

### Ans: 版本號，指定使用4.0.3以上但是4.1以下。

4. 請簡述什麼是 N+1 問題? 又該怎麼解決它?

### Ans: 一般來說都用include去解決這個問題。
### ex:

### comments = Comment.includes(:post)

### Comment.each do |comment|

### comment.post.title

### end



# Git 題
1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?

### Ans: 在空目錄中直接新增一個新檔案，看要新增什麼檔案，這樣資料夾也就一併 commit 到 repository。


2. 在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?

### Ans: Ignore掉她 
## ex : .gitignore
``` git
# ignore main settings file
/config/database.yml
```
