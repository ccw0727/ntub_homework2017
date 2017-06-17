Ruby 題


 1.	試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。

        在Ruby中常數的開頭要大寫，而變數是小寫


 2.	請問 hash[:key] 跟 hash["hash"] 有什麼差別?


 3.	如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？

        puts [*1..100].sample(5)


 4.	試說明在 Ruby 裡 public、protected 與 private method 的差別。

        public 是公開的意思，示方法可以被任何人呼叫。。
        private 只有 self 可以當成 private 方法的接受者。
        protected 可以被一個類別或衍生類別的實例呼叫，也可以讓另一個相同類別的實例來當做接受者。 


Rails 題


 1.	請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。

        devise，因為它直接把註冊、登入與登出的功能寫好了

        cancancan：權限管理

        koala：臉書快速API



 2.	請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?

        User.find(1)要尋找主鍵(id)等於1的資料

        User.find_by(id: 1)找id這個欄位等於1的資料


 3.	Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?

        是指會選用 4.0.3 以上，但 4.0.4 以下的最新版本。


 4.	請簡述什麼是 N+1 問題? 又該怎麼解決它?

        N+1 query問題，意思是我們在迴圈當中大量查詢N筆資料，再加上開頭查詢的那1筆，稱為N+1。
        為了避免在幾千筆資料查詢時大量消耗不必要的記憶體，
        Rails提供joins和include方法可以在第一次查詢時將所有我們需要的資料一次查完。



Git 題


 1.	空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?

        在資料夾底下建立一個隱藏檔


 2.	在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?

        把 config/settings.yml 複製成 config/settings.yml.backup （裡面的資料要清空），
        並把 config/settings.yml 增加到 .gitignore 內，以後 deploy / dev 環境建立時複製一份即可，
        這樣做就可以讓機敏資料不上 git
