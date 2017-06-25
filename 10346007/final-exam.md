Ruby 題
1.變數是表示某個數字或字串，有可能會變更，但常數會保留所指派的值，並且不會再變更。
2.其實是一樣的東西，但hash["hash"]有可能抓取不到字串，所以必須先使用with_indifferent_access。
3.puts [*1..100].sample(5)
4.存取範圍的不同，public是公開，private只限於類別內部使用，protected雖然也是只限類別內部，但可以繼承給子類別使用，所以介於兩者之間。

Rails 題
1.(1)"cancancan" 聽起來就很厲害 (2)"devise" 因為感覺只需要輸入幾行就可以完成註冊、登入等等動作就覺得很神奇 (3)"paperclip" 可以上傳檔案和圖片的套件
2.User.find_by(id: 1)如果找不到id資料會回傳nil；User.find(1)則會產生ActiveRecord::RecordNotFound例外訊息。
3.是指會選則使用4.0.3以上的版本。
4.會產生過多的資料庫查詢筆數，導致消耗大量不必要的記憶體；Rails可以用include方法解決，include會先將所有資料回傳，再一次性對所有資料做查詢。

Git 題
1.
2.備份和加密
