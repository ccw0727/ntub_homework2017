Ruby題
1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
在命名規則方面，變數沒有特別的規則，英文、數字、非英文字都可以，但是對常數就有特別的規定，那就是常數必須要用大寫字母來開頭，而且所有class的名字都必需用常數命名
2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?
首先hash的key是Symbol也就是:Key，是一個帶有名字的物件，而"hash"是字串，而Symbol是不能被修改的，但字串可以修改，而且像是a = "bb"，將a指向bb這個字串，但是如果沒有bb這個物件給a指，那a就沒辦法存在，但是Symbol不用指向任何物件也可以使用
3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
puts [*1..100].sample(5)
4.試說明在 Ruby 裡 public、protected 與 private method 的差別。
public的方法是所有人都可以直接存取的，而private方法，只要沒有明確的指出recevier(例如dog.method_a的dog是recevier)的話就都可以呼叫，所以子類別可以呼叫到父類別的protected和private方法，但如果有指出recevier則不行呼叫private方法，而protected方法他則介於public和private之間，規定沒那麼嚴格，子類別可以呼叫父類別的方法，不管有沒有指定recevier都可以呼叫
Rails題
1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
第一個gem install rails，第二個gem install bundle，第三個gem install bundler，因為網路上有很多很好用的套件(gem)，如果使用現有的gem的話，就可以快速地做出我們想要做的東西，縮短開發的時間，而且網路上都會有詳細的套件說明，就不會不知道怎麼使用
2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
這兩種寫法都可以找到id是1的user，但是當找不到指定id的user時，find_by方法會回傳nil物件，而find方法則會產生ActiveRecord::RecordNotFound的例外訊息，像是找不到id=1的user
3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
後面的4.0.3是指sass-rails這個套件的版本，而~> 4.0.3的意思是我要安裝4.0.3以上，但還沒到4.1的最新版本
4.請簡述什麼是 N+1 問題? 又該怎麼解決它?
N+1問題會降低效能，例如我們要在view中顯示user.puppy.name的值，這時就會導致N+1 query問題，假設user有100筆資料，這時程式就會產生101筆query，1筆是查user，另外100筆是查puppy，而且每一筆查詢資料庫的query都很耗時間，這樣會造成效能上的降低，而解決方法可以使用include，他會在找user時，就先把他的各項內容一起載入，也就是先把需要的資料一次從model抓到controller，以此來解決N+1問題
Git題
1.空的資料夾無法被加入Git版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
可以在這個資料夾當中，新增一個gitignore檔案，裡面先打*表示要忽略這個目錄底下的所有檔案，並在打!.gitignore表示不要忽略.gitignore，這樣就可以把這個資料夾commit到repository了
2.在Rails專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用Git時，你通常會怎麼處理這類型內容比較敏感的檔案?
可以在git上面設定gitignore，就可以將這些敏感的感案排除在版本控制的範圍外
