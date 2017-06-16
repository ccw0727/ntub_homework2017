## Ruby 題

1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。  
    答案：命名慣例上有所不同，變數是小寫開頭，常數是大寫開頭
    
2. 請問 hash[:key] 跟 hash["hash"] 有什麼差別?  
    答案：hash[:key] 會得到 key 對應的值，hash["hash"] 會得到 nil
    
3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？  
    答案：
    ```ruby
    puts [*1..100].sample(5)
    ```
    
4. 試說明在 Ruby 裡 public、protected 與 private method 的差別。  
    答案：
    - public: 公開的大家都可以呼叫
    - protected: 只有類別自己或者繼承他的子類別可以呼叫
    - private: 只有類別本身可以呼叫

## Rails 題

1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。  
    答案：我會採用的套件有
    1. faker: 利用這個套件可以快速的產生測試資料不需要自己輸入讓開發更輕鬆快速
    2. devise: 利用這個套件可以快速的建立會員管理的機制
    3. simple_form: 讓表單的建立更加簡單 (打更少的字) 而且還可以搭配 Bootstrap 很方便
    
2. 請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?  
    答案：利用 find 尋找如果找不到會引發 `ActiveRecord::RecordNotFound` 例外，但利用 find_by 尋找時如果找不到會回傳 `nil`
    
3. Gemfile 裡 `gem 'sass-rails'`, `'~> 4.0.3'` ，後面的 `"~> 4.0.3"` 是代表什麼意思?  
    答案：使用 4.0.3 版本以上，但 4.1 版本以下的最新版
    
4. 請簡述什麼是 N+1 問題? 又該怎麼解決它?  
    答案：N+1 問題是指當有 10 筆資料時需要撈 DB 11 次。 比如說要列出所有 User 的購物紀錄，先從 User 資料表撈出所有 User 再跟據 User 去撈出所有的購物紀錄。 在 Rails 中如果要解決可以使用 includes() 的語法

## Git 題

1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?  
    答案：在資料夾中加入 `.gitkeep` 檔案
2. 在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?  
    答案：使用 `.gitignore` 將檔案排除再版本控制之外，同時提供 `database.example.yml` 當作檔案內容的參考讓其他共同開法者能方便的使用
