# 期末考

## 簡答題(40 分，每題 4 分)

### Ruby 題

* 試說明在 Ruby 裡常數(constant)跟變數(variable)的差別。<br />
常數第一個字必須為大寫英文字母，類別名、模組的名稱都是使用常數。<br />
變數就沒有特別規定。<br />

* 請問 hash[:key] 跟 hash["hash"] 有什麼差別?<br />
hash["hash"] 會呈現錯誤，雖然新版的rails可以使用<br />
cat = { name: "mimi" }<br />
但其實跟原本的 cat = { :name => "mimi" }本質是一樣的<br />
所以在呼叫的時候仍須使用cat[:name]<br />

* 如果要在 1 到 100 的數字當中，任意取出 5 個不重複的亂數，你會怎麼做？<br />
 ```
 puts [*1..100].sample(5)
```
* 試說明在 Ruby 裡 public、protected 與 private method 的差別。<br />
public就是所有人都可以使用，<br />
private就是只能自己這個類別用，但是在ruby只要不指定接收者的話，<br />
子類別也還是可以呼叫父類別的private方法。<br />
protected應該就還是像一般程式語言一樣，父類別的protected方法<br />
只有子類別可以使用。<br />


### Rails 題

* 請任意舉出三個你在開發 Rails 專案時常用到的 gem，並說明你覺得這些 gem 厲害的地方或是你為什麼採用它們的原因。<br />
1. bootstrap 像我這種不太會設計的人，可以有個基本的美美版型覺得很不錯。 <br />
2. devise 這款是老師介紹的，可以速成登入註冊那些功能。<br />
3. cancancan 這款也是老師介紹的，也是很好用，可以做權限的控管。<br />
不過我覺得我們還是不要太依賴這些速成的套件。<br />

* 請問 User.find_by(id: 1) 跟 User.find(1) 這兩個寫法有什麼差別?<br />
使用find_by的話，如果找不到資料會傳回nil，<br />
若使用find，找不到資料是會出錯。<br />

* Gemfile 裡 gem 'sass-rails', '~> 4.0.3' ，後面的 "~> 4.0.3" 是代表什麼意思?<br />
該套件的版本<br />

* 請簡述什麼是 N+1 問題? 又該怎麼解決它?<br />
資料庫容易產生N+1 query問題,意思是我們在迴圈當中大量查詢N筆資料,<br />
再加上開頭查詢的那1筆,稱為N+1<br />
可以使用includes方法解決<br />

### Git 題

* 空的資料夾無法被加入 Git 版控，但這個資料夾如果又是很重要的資料夾，你會怎麼處理?<br />
在裡面先新增個readme.md<br />
* 在 Rails 專案中，/config/database.yml 這個檔案裡有資料庫的設定、帳號密碼等資訊，在使用 Git 時，你通常會怎麼處理這類型內容比較敏感的檔案?<br />
把這些敏感的檔案加密我想應該是比較理想的辦法<br />
