# <p> Ruby 題</p>
### 1.試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。
 <p> A:</p>
  變數不需要宣告或指定型態就可以使用。在變數命名規則上，通常會使用英文字母、數字或底線的組合，或是非英文字也可以，如日文。
  例如：
  student_id = "10536006"

   <p> 常數也不需要宣告或指定型態，但在命名上有規定，常數必須要是大寫英文字母開頭。</p>
  例如：
  Student = "Alysia"


### 2.請問 hash[:key] 跟 hash["hash"] 有什麼差別?
 <p> A:</p>
字串的內容可以變，但 Symbol 不行。
    **修改字串，kitty第一個字母，換改成 m**
    <p><code>>> "kitty"[0] = "m"    
    => "m"
    
    >> :kitty[0] = "m"  // 但在 Symbol 上卻行不通，會發生錯誤（因為 Symbol 類別並沒有 []= 這個方法）
    NoMethodError: undefined method `[]=' for :hello:Symbol'`
    可以把 Symbol 看做是一種「不可變（immutable）的字串」

### 3.如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？
 <p> A:</p>
  puts [*1..100].sample(5)

### 4.試說明在 Ruby 裡 public、protected 與 private method 的差別。
 <p> A: </p>
  public方法是公開的，沒有限定，可以自由存取。
  protected方法在public跟private之間，你要指定或不指定recevier都可以
  
  private方法在Ruby裡比較特別，只要沒有明確的指出recevier的話就都可以呼叫。如：
  
  <p><code>
  father = Father.new
  father.method_c
  </code></p>
  
  <p><code>
  class Son < Father
    def son_method_c
        method_c
    end
  end
  </code></p>
  <p><code>
  son = Son.new
  son.son_method_c  # I am METHOD C in Son
  </code></p>
  
  
 # <p> Rails 題</p> 
 
### 1.請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。
<p> A:</p>
      *** 'bootstrap-sass' ***
      超級好用的boostrap套件，裡面有非常多套件可以運用，隨便選都可以讓元件或介面變漂亮，超迅速且美麗！如最常用的是button。
      *** 'simple_form' ***
      套用這個gem可以快速地在做完scaffold後，啟動server就有個令人舒服的簡單排版，是要做form表單的使用者必備元素，方便又快速。
      *** 'cancancan' ***
      這個是用在需要設定權限的地方，github上都有它的教學，指令清楚明瞭，在使用上可讀性很高，非常方便使用於管理權限設定。
      

### 2.請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?
<p> A:</p>
    find： 根据id查找，返回一个对象
    如：
    </code></p> Candidate.find_by(id: 123)   </code></p>
    如果id不存在的话，会抛出異常。find 方法會直接產生 ActiveRecord::RecordNotFound 的例外訊息。

    find_by 方法如果找不到指定 id 的資料，僅會回傳 nil 物件
    如：
    </code></p> Candidate.find_by(id: 123)   </code></p>
    => nil
    
### 3.Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?
<p> A:</p>
    這是指會選用 4.0.3 以上，但 4.1 以下(不含括 4.1)的最新版本。
    4、0、3 這三個數字分別代表主要版號(Major)、次要版號(Minor)以及修訂版號(Patch)，分別表示：

    主要版號：功能大改，公開的 API 做了不少修正，通常沒辦法向下不相容
    次要版號：加了某些新功能，但不影響其它功能，向下相容
    修訂版號：對現有的功能做了小幅度的修正，可向下相容
    
### 4.請簡述什麼是 N+1 問題? 又該怎麼解決它?
<p> A:</p>
    假設我們有兩個ActiveRecord：Customer、Order 且 Customer has_many :orders 、 Order belong_to :customer 。

一般我們獲取所有Customer的方法是：
</code></p> customers = Customer.all  </code></p>
如果我們後面緊跟著
</code></p> customers.each { |customer| puts customer.orders.amount }  </code></p>
這樣就會產生N+1問題。
因為在獲取所有Customer的時候，是沒有去取orders的。然後在後面each的時候，就會取每一個order，這就構成了rails中的N+1問題。

解決：
</code></p> customers = Customers.includes(:orders)  </code></p>
這樣就在讀取customers的時候也一次性的把orders都取出了。


  # <p> Git 題</p> 
### 1.空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?
<p> A:</p>
    在資料夾底下建立一個隱藏檔，例如 .gitkeep：
    cd log
    tocuh .gitkeep
    
### 2.在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?
<p> A:</p>
  除了要從版本控制系統中移除 database.yml，或者改製成樣板，也要告訴 git 停止追蹤檔案