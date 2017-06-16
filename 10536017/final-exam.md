Ruby 題
1.	試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
變數：不需要特別宣告或是指定型態，直接拿來用就可以了。在變數命名規則上，常見會使用英文字母、數字或底線的組合。或是想要用非英文字也可以
常數：不需要特別宣告它是常數，但在 Ruby 對常數有特別的命名規定，就是「常數必須要是大寫英文字母開頭」
資料來源：http://railsbook.tw/chapters/05-ruby-basic-1.html#variable-and-constant

2.	請問 hash[:key] 跟 hash["hash"] 有什麼差別?
 hash[:key]：取得key的資料
 hash["hash"]：取不到hash的資料
資料來源：http://railsbook.tw/chapters/06-ruby-basic-2.html#hash_class

3.	如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
 puts [*1..100].sample(5)
資料來源：http://railsbook.tw/chapters/06-ruby-basic-2.html#hash_class

4.	試說明在 Ruby 裡 public、protected 與 private method 的差別。
Public：所有的人都可以直接存取
Private：只有在類別內部才可以存取
protected：在同一個類別內或是同一個package，或是繼承它的子類別可以自由取用，但如果不是的話則不可存取。
資料來源：http://kaochenlong.com/2011/07/26/public-protected-and-private-method-in-ruby/

Rails 題
1.	請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
(1)	Bootstrap：可以快速建立網頁框架
(2)	install rails：可以快速安裝rails套件
(3)	devise：可以快速設定使用者權限
資料來源：https://ihower.tw/rails/auth.html

2.	請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
兩種方式都可以找到編號1號的使用者。
差別是
User.find_by(id: 1) ：找不到指定的id資料，僅會回傳nil物件
User.find(1)：會直接產生 ActiveRecord::RecordNotFound 的例外訊息
資料來源：http://railsbook.tw/chapters/16-model-basic.html

3.	Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
會使用4.0以上，但4.1以下(不包含4.1)的最新版本
資料來源：http://railsbook.tw/chapters/09-using-gems.html

4.	請簡述什麼是 N+1 問題? 又該怎麼解決它?
N+1是指利用迴圈，查詢資料的次數，假如要查10筆聯絡人資料，則會執行10+1=11次，若是資料數量龐大，會占用記憶體，且查詢速度慢，可使用includes解決

Git 題
1.	空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
使用$ git add 指令，將資料夾內全部檔案收錄進版本控制資料庫
資料來源：http://sdlong.logdown.com/posts/171365

2.	在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
(1)使用下列指令，移除 database.yml，並停止追蹤檔案：
         $ git mv config/database.yml config/database.yml.example
         $ echo "config/database.yml" >> .gitignore
     
 (2)使用 Capistrano 自動化佈署時，就需要另外將這個檔案另外上傳到伺服器去，這裡以 EC2   
         為例，透過憑證連上伺服器，把本地檔案丟到上面去：
          $ scp -i path_to_cer.pem config/database.yml   
           user_name@my_server.com:~/path_to_rails_app/shared/config/database.yml
      
(3) 最後在 config/deploy.rb 寫一個腳本，自動用 symlink 覆蓋上去就好了，以下是個範例：
        # in RAILS_ROOT/config/deploy.rb:
after 'deploy:update_code', 'deploy:symlink_db'

namespace :deploy do
            desc "Symlinks the database.yml"
           task :symlink_db, :roles => :app do
                run "ln -nfs #{deploy_to}/shared/config/database.yml #{release_path}/config/database.yml"
           end
end

資料來源：http://blog.chh.tw/posts/rails-database-yml-management/

