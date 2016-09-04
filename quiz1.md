1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異
  > Fixnum:用來表示包含正負的整數。
  > Float:用來表示包含正負且帶有小數的數字。float的運算為非精確的運算2。

2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
  請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```
  > 第一個puts用的是字串拼接(string concatenation)。若其中一個變數不為字串則會發生錯誤;
  > 第二個puts則為字串插值(string interpolation)。會自動把變數轉為字串。
  > 一般來說使用字串插值效率較好。

3. 請解釋 array 和 hash 的不同處

  > array:為有序、整數索引的集合，透過整數索引來存取物件。其包含的元素可以為不同物件形態。
  > hash:為unique keys與其value的集合，透過每個唯一的key來存取對應的value。key與value可為任意物件形態。

4. 請用一行程式碼從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值
  > 
  ```ruby
  [1, "a string", 3.14, [1,2,3,4]].reject { |x| x.is_a? String }
  ```

5. 請用一行程式碼把一個內容為整數 1 到 100 的陣列裡所有的值加上 2
  > 
  ```ruby
  array.map! { |x| x + 2 }
```

6. 請寫出以下兩行程式碼迴傳的值，並解釋他們呼叫的方法差別為何：
  ```ruby
  [1, 2, 3, 3].uniq
  [1, 2, 3, 3].uniq!
  ```
  > uniq會移除陣列裡相同的元素，兩者回傳的結果皆為[1, 2, 3]。
  > 差異為前者會把結果輸出為新的陣列，後者則會修改原來陣列的值。


7. 請列出兩種產出亂數的方法
  > 
  ```ruby
  rand(1..5)
  [1, 2, 3, 4, 5].sample
  ```

8. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
  會執行出什麼結果？ 請試試不用 irb 算出結果

  > 原式
  > =>((false)&&(true))||(true)
  > =>(false)||ture
  > =>true
  
  9. 請問 binding.pry 是什麼？ 要如何使用它？
  > 幫助除錯的一個套件，可以在ruby裡下中斷點。
  > 
  > 安裝:
  > gem install pry
  > 
  > 使用:
  > 在rb檔最上面加上require 'pry'
  > 在要中斷的下一行中加上binding.pry

10. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

  ```ruby
  var = 5

  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```
  > 
  ```ruby
  return var >= 5 ? "var is greater than or equal to 5" : "var is less than 5"
  ```

11. 請列出兩種不同的 hash 寫法
  > 使用hashrocket
  ```ruby
  player = { :sid => 1, :name => "Neo" }
  ```
  > 簡化
  ```ruby
  player = { sid: 1, name: "Neo }
  ```