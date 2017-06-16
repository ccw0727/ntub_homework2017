Ruby 題
1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
A: 在Ruby中有五種變數，以小寫字母開頭為區域變數，以\$開頭為全域變數，以@開頭為實例變數，以@@開頭的類別變數與常數。常數的開頭為大寫，對常數做第二次修改的話，會提示警告。
2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?
A:產生新的hash表，使用hash[:key]時，參數的個數必須是偶數，奇數位元參數是索引，偶數位元參數是元素值，使用hash["hash"]時，將產生並回傳一個與指定hash表相同且全新的hash表，新的hash表預設值為nil。
3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
A: puts [*1..100].shuffle.first(5)，將一百個數字打亂順序之後取出前面五個數字。
4.試說明在 Ruby 裡 public、protected 與 private method 的差別。
A: public方法是公開的，全部人都可以存取，protected方法是類別內部以及它的子類別可以存取，Private 方法是使用在類別內部。
Rails 題
1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
A: find_by方法是如果找不到指定的id，會回傳 nil 物件，但是 find方法會產生 ActiveRecord::RecordNotFound 的例外訊息。
3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
A:~>代表差不多，會選擇 4.0.3 以上，且4.1 以下(不含括 4.1)的最新版本。
4.請簡述什麼是 N+1 問題? 又該怎麼解決它?
A:N+1問題會拖慢資料庫的效能，如果有一程式是讀取user.car.name的值，假設User有10筆，程式會產生出11筆查詢指令，一筆是查User，另外10筆是逐一去查Car，這樣的程式會導致N+1問題。解決方法，就是加上includes，@users = User.includes(:car).page(params[:page])，這樣SQL查詢語言只有兩筆，一筆查詢User，一筆查詢所有Car資料。
Git 題
1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
A:在資料夾中新增一個說明檔，類似於Readme.txt，在將資料夾推至GitHub上。
2.在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案 ?
