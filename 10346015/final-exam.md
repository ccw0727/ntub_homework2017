Ruby 題
  1.	試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。  
    一般來說變數就是會變的數，常數是不變的數，可是在ruby裡常數是能被更改的，所以常數跟變數的使用上是差不多的，但在常數的命名上必須是要英文字大寫開頭。
    
  2.	請問 hash[:key] 跟 hash["hash"] 有什麼差別?
    :name是一個符號，而"hash"是一個字串會抓不到值得到nil
    
  3.	如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
    puts [*1..100].shuffle.first 5
    
  4.	試說明在 Ruby 裡 public、protected 與 private method 的差別。
    Public是所有都能夠存取，Private只有在類別內部才能呼叫，protected是在public跟private兩者間，可以在內部呼叫，也能被相同類別或是繼承的子類別呼叫

 
Rails 題
  1.	請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
    Gem 'rails' 可以快速安裝完rails所需的指令
    Gem ‘device’ 可以快速做完帳戶所需功能，如註冊、登入、登出
    當出現cannot load such file -- bcrypt_ext的錯誤訊息時做完下列步驟重新bundle後就能解決錯誤
      gem uninstall bcrypt
      gem uninstall bcrypt-ruby
      gem install bcrypt --platform=ruby
      add "gem 'bcrypt', platforms: :ruby" to Gemfile
    
  2.	請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
    User.find(1)找到類型是User，符合所有id等於1所指向的行，User.find_by(id: 1) 是找出類型是User，符合第一個id等於1所指向的行

  3.	Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
    選用4.0.3以上，但4.1以下且不包含4.1的最新版本
    
  4.	請簡述什麼是 N+1 問題? 又該怎麼解決它?
    如果要查詢n筆資料，就必須執行n+1次select查詢語句，如此效率很慢會影響性能。解決方法：rails用includes一次撈出所有資料。
 
Git 題
  1.	空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
    在那個空資料夾新增一個檔案，讓空資料夾變成有東西的資料夾就可以被加入了
  
  2.	在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
    將 config/database.yml放到.gitignore裡面，可以忽略此檔案不被commit
    
