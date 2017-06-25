#Ruby 題

1. 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
  → 常數的命名規定必須要是大寫英文字母開頭，變數則沒有特別規定。
2. 請問 hash[:key] 跟 hash["hash"] 有什麼差別?
  → hash中他的key必須是符號([:key]/[:hash])而非字串("key"/"hash")，將符號放成字串會找不到資料。
3. 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
  → puts [*1..100].sample(5) 4 試說明在 Ruby 裡 public、protected 與 private method 的差別。
  → public、protected以及private這三個在Ruby裡並不是關鍵字，它也只是Ruby裡的方法而已。
  → public(預設)：以被外部存取。 → protected：不可以被外部存取，但子類別可呼叫父類別。
  → private：不可以被外部存取，只要沒有明確的指出recevier、self的話就都可以呼叫。
  
  
#Rails 題

1. 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
  → 1. "gem install rails"，可以快速建立rails的環境。
  → 2. "gem 'devise'"，使用者認證能篩選登入近系統的user。
  → 3. "gem install faker"，快速的產生很多種的看起來像真的「假資料」。
2. 請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
  → User.find_by(id: 1)如果找不到id:1資料，僅會回傳 nil 物件。User.find(1)則會回傳例外訊息ActiveRecord::RecordNotFound。
3. Gemfile 裡 gem 'sass-rails', '> 4.0.3" 是代表什麼意思?
  → 版本
4. 請簡述什麼是 N+1 問題? 又該怎麼解決它?
  → N+1問題：1次查詢+N次的關連資料查詢(對資料庫來說很浪費)。利用Rails裡可使用includes方法解決(把Controller def index裡面all改成includes)。
  
  
#Git 題

1. 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
  → 空目錄中新增一個檔案(README.md)。
2. 在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
  → /config/database.yml 包含伺服器位置、管理員帳號以及密碼等等的重要資訊，所以是不能放進版本控制系統中。因此，要移除 database.yml，或者改製成樣板，或停止追蹤檔案。
