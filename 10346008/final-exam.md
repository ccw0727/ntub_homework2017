<h2>Ruby題</h2>
<h3>1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。</h3>
在ruby常數通常大寫英文開頭，應用在不常變動的值上，但還是可以變動，只是會警告，反之變數就是在執行時經常會變動的數。
<h3>2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?</h3>
:key 是一個符號、"hash"則是值，例如要抓取所有的key可以這樣寫 :<li>p profile.keys</li><li>p profile.values</li>
<h3>3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？</h3>

puts [*1..100].sample(5)
<h3>4.試說明在 Ruby 裡 public、protected 與 private method 的差別。</h3>
public就是所有人都可以直接使用，而protected在同一個類別內或是同一個package，或是繼承它的子類別可以自由使用，否則不可存取，而private只能在類別內使用，而且不能使用self。
<h2>Rails題</h2>
<h3>1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。</h3>
1.bootstrap-sass，這個可以簡單的就讓網頁變得有質感，而且使用方法簡單。<br>
2.devise，這個真的太強大拉，可以很快地就做完用戶權限登入的部分。<br>
目前感覺最常用就這兩個。
<h3>2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?</h3>
find_by 如果找不到指定id，只會回傳 nil 物件，find則是會產生ActiveRecord::RecordNotFound的例外訊息。
<h3>3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?</h3>
這是指會選用 4.0.3 以上的最新版本。
<h3>4.請簡述什麼是 N+1 問題? 又該怎麼解決它?</h3>
我們在迴圈當中大量查詢N筆資料，再加上開頭查詢的那1筆，稱為N+1，為了避免在幾千筆資料查詢時大量消耗不必要的記憶體，Rails提供joins和include方法可以在第一次查詢時將所有我們需要的資料一次查完。
<h2>Git題</h2>
<h3>1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?</h3>
先在目錄建.gitkeep文件，然後在該項目的.gitignore中設置不忽略.gitkeep即可提交空資料夾。
<h3>在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?</h3>
1.首先移到模板文件 <br>
git mv config/database.yml config/database.yml.example<br>
2.忽略.yml版本
cat > .gitignore<br>
config/database.yml<br>
3.安裝Where’s your database.yml, dude?<br>
script/plugin install git://github.com/technicalpickles/wheres-your-database-yml-dude<br>
4.设置 Capistrano 部署任務<br>
5.上傳database.yml的服務器版本<br>

