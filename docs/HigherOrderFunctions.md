#関数を引数として受け取る/関数を返す

関数を引数として受け取ったり、戻り値として返す関数を高階関数といいます。
関数を受け渡しすることで、関数の振る舞いを外から変えたり、振る舞いを受け取ることができます。

##関数を引数として受け取る

関数の引数の型に、関数型を指定します。

    fun example(callee: (Int, Int) -> Int, val1: Int, val2: Int): String {
      val result = callee(val1, val2)
      return "Result : $result";
    }

この例では、第一引数に関数を受け取るように定義しています。
この例で受け取る関数は、第一、第二引数、戻り値ともにInt型を指定しています。

これを呼ぶ場合には、既存の関数を渡すことも、関数リテラル/関数式でその場で定義することもできます。

###既存の関数を渡す場合
    fun calc(value1: Int, value2: Int): Int {
      return value1 + value2
    }
    
    print(example(::calc, 1, 1)) // Result : 2

###関数リテラルで指定する場合
    println(example({x, y -> x * y}, 2, 2)) // Result : 4

###関数式で指定する場合
    println(example(fun(x, y) = x / y, 6, 2)) // Result : 3

##関数を返す

関数の戻り値に、関数型を指定します。

    fun example2(val1: Int): (Int, Int) -> Int {
        return {x, y -> (x + y) % val1};
    }

関数型には引数で受け取る場合と同じ型を指定しています。

返す関数は関数リテラルで、クロージャーを使用して引数として渡された値を、返す関数内で使用しています。

###返された関数を呼ぶ
    println("result : ${example2(2)(2, 1)}")
