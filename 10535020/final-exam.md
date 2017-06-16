Ruby 題

1.
變數不需要特別宣告或是指定型態，直接就可以使用。變數命名規則上，常見會使用英文字母、數字或底線的組合。

Ruby有特別規定，常數在宣告時，需要用大寫英文字母來命名

在變數或是常數命名時，盡量選有意義的名稱，在使用時比較好做辨識

2.
若輸入hash["hash"]，來取得Hash裡面hash的資料時，會出現空值，撈不到資料。

那輸入hash[:key]，就可以取得Hash裡面key的資料，索引直是:key,不是字串形式的"key"

:key這樣的寫法又叫做symbol，symbol的命名規則和變數差不多，是用英文和數字組合命名。又可以稱它為[帶有名字的變數]

3.
puts[*1..100].sample(5)

4.
public 是任何人都能存取

prodected 介於兩者之間，不需要特別指定recevier

private 是只有此類別方法裡面才可以做存取，除非有特別指出recevier，否則皆可以呼叫，再深入一點，以繼承方式做說明，private類別自己內部可以存取，它的子類別也可以

Rails 題

1.

(1).rails

(2).bootstrap 

(3).devise

我覺得他們厲害的地方就是老師在課堂上說的，他們是黑魔法！！！

可以快速地把自己網站所要的物件建立起來

它們幫助我可以建立網站、美化網站上的空間和在網站上進行會員的認證

2.
User.find_by(id: 1) 指的是直接透過id去尋一個id叫1的資料，範圍較小，搜尋速度較User.find(1)要快

User.find(1)也是去尋找資料，不過它沒有特別指定以哪種欄位去搜尋，搜尋速度會慢上許多

3.
gem適用rails 4.0.3 以上，但 4.0.4 以下（不含括 4.0.4）的最新版本。

4.
N+1是資料庫的頭號問題。因為ActiveRecord的Association功能很方便，譬如說我們要找資料庫其中一筆資料，用user.student.name去搜尋

可是這樣就會產生N+1的問題，如果有5筆student資料，這樣會產生6個Queries，一筆查User，其他筆找student，這樣嚴重影響到效率。

解決方法，加上includes。

Git 題

1.
可以在底下建立一個隱藏檔，例如 .gitkeep：

cd log

tocuh .gitkeep

在跟「.git」同一層的目錄中，可以建立一個 .gitignore 檔案。

.gitignore 用來設定「不希望被 Git 控管的檔案與資料夾」。

2.
設定 GitHub 專案的權限控管 - 組織帳號

* Pull Only (唯讀)

* Push & Pull (可讀可寫)

* Push, Pull & Administrative (可讀可寫以及專案管理權限)
