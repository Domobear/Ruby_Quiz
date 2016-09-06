1. 請用簡單的方式敘述以下每一行程式碼：
  ```ruby 
  a = 1              #指定1給區域變數(local variable)a
  @a = 2             #指定2給實例變數(instance variable)a
  @@a = 5            #指定5給類別變數(class variable)a
  user = User.new    #創建一個User類別的物件並指定給user變數
  user.name          #呼叫user物件的name方法
  user.name = "Joe"  #指定"Joe"給user物件的實例變數name
  ```
  
2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?
  > module為方法與常數的集合，讓class可以透過include來使用。
  ```ruby
  module ShowTip
  	def ShowJoined(iName)
  		puts "#{@name} is joined."
  	end
  end
  class AI
  	include ShowTip
  	def initialize(iName)
  		@name = iName
  		ShowJoined(@name)
  	end
  end
  ai = AI.new
  ai = AI.ShowJoined("Neo")
  ```

3. 請說明 class variable 和 instance variable 之間的差別
  > class variable屬於class本身，直接透過class來存取。
  > 
  > instance variable則屬於被new出來的物件，同個class的不同物件其instance varible可以為不同值。

4. 請說明 class method 和 instance method 之間的差別
  > class method直接透過class來呼叫，屬於該class的物件也無法呼叫class method。
  > 
  > instance method透過被new出來的物件來呼叫。

5. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是:
  ```ruby
  User.new("Bob", "male", "Engineer")
  ```
請寫出 User class 的 initialize method
  > 
  ```ruby
  class User
    attr_accessor :name, :gender, :job
    def initialize(name, gender, job)
      @name = name
      @gender = gender
      @job = job
    end
  end
  ```

6. 在：
  A.  一個 class 裡，method 外面
  B.  一個 class 裡，instance method 裡
  self 分別是指向什麼?
  > A:class本身。
  > 
  > B:物件本身

7. attr_accessor 的功能是什麼，它和 attr_reader、attr_writer 之間的差別是什麼？
  > attr_accessor會自動建立instance variable的存取方法 。
  
  > attr_reader只建立讀取方法。
  
  > attr_writer只建立寫入方法。

8. 請說明 public 和 private method 之間的不同
  > public method:可以在物件內部呼叫，也可以從外部透過物件呼叫
  > 
  > private method:只能在物件內部呼叫，無法透過物件呼叫。

9. 請說明 Inheritance 和 Module 之間的差別，它們分別是用於哪些情況？ 請舉例說明
  > Inheritance主要是用在同種類型的class之間，讓繼承的class都能擁有基底的變數跟方法。
  > 
  > Module本身不能被實例化，概念上偏向於組合的方式，讓其他class選擇是否需要這個模組的功能。

10. 若今天有一個 class 有 include 一個 module，他的 parent class 和 sub class 是否可以使用該 module 裡的 method?
  > parent class不行，sub class可以。

11. 請間單說明什麼是 Relational Database，什麼是 SQL
  > Relational Database 關聯式資料庫
  > 
  > 是建立在關聯模型基礎上的資料庫，藉助於集合代數等數學概念和方法來處理資料庫中的資料。基本上會將資料間的關係以資料庫表的形式加以表達。
  >
  > SQL 結構化查詢語言
  > 
  > 基於關聯式資料庫的一種查詢語言，用來對資料庫中的資料進行操作。
  