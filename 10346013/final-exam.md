*Ruby 題
  1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
    A：開頭大寫的變數就是constant；variable又分為三種，為全域($)、實體(@)、區域(小寫字母開頭的名字)、類別變數(@@)。  
  
  2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?
      A：:key是一個符號，"hash"是一個字串。hash = {name: "123"}`,如果想取得name，打hash["hash"]會得到nil，要打hash[:key]才能得到值。  
  
  3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
      A：puts [*1..100].sample(5)。  
  
  4.試說明在 Ruby 裡 public、protected 與 private method 的差別。
      A：方法裡預設是publilc，除了initialize方法，initialize方法永遠是private，呼叫private方法的時候，不能明確的指定recevier，
         protected要指定或不指定recevier都可以。
      

*Rails 題
  1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
      A：
  
  
  2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
      A：User.find_by(id: 1) 跟 User.find(1)這兩種方式都可以找到編號 1，兩者的差別是如果find_by方法找不到指定id，
         只會回傳nil物件，但是find方法會直接產生例外訊息。
  
  
  3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
      A：會選用4.0.3以上的版本，但4.1以下（不含括4.1）的最新版本。
  
  
  4.請簡述什麼是 N+1 問題? 又該怎麼解決它?
      A：會導致很多小查詢的執行，而不是一個單一的大查詢。解決方法：一次把資料取出。
      
*Git 題

  1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
      A：git commit -m " "在commit的時候打在""裡。
  
  
  2.在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
      A：用vi編輯。
