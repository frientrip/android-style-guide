- [μκ° π](#μκ°)
- [μμ€ μ½λ κ΅¬μ±](#μμ€-μ½λ-κ΅¬μ±)
  * [μμ€ νμΌ κ΅¬μ±](#μμ€-νμΌ-κ΅¬μ±)
  * [ν΄λμ€ λ μ΄μμ](#ν΄λμ€-λ μ΄μμ)
  * [μΈν°νμ΄μ€ κ΅¬ν λ μ΄μμ](#μΈν°νμ΄μ€-κ΅¬ν-λ μ΄μμ)
- [λ€μ΄λ° κ·μΉ](#λ€μ΄λ°-κ·μΉ)
  * [λͺ¨λ](#λͺ¨λ)
  * [ν¨ν€μ§](#ν¨ν€μ§)
  * [μμ€ νμΌ](#μμ€-νμΌ)
  * [ν΄λμ€](#ν΄λμ€)
  * [μΈν°νμ΄μ€](#μΈν°νμ΄μ€)
  * [ν¨μ](#ν¨μ)
  * [λ³μ](#λ³μ)
  * [μμ](#μμ)
  * [enum](#enum)
  * [μ½μ΄](#μ½μ΄)
- [μμ](#μμ)
  * [μ΅λ μ€κΈΈμ΄](#μ΅λ-μ€κΈΈμ΄)
  * [λ€μ¬μ°κΈ°](#λ€μ¬μ°κΈ°)
  * [κ°λ‘ κ³΅λ°±](#κ°λ‘-κ³΅λ°±)
  * [μ€λ°κΏ](#μ€λ°κΏ)
- [κΈ°ν](#κΈ°ν)
  * [Properties vs Functions](#properties-vs-functions)
  * [ViewModelμμ MutableLiveData/LiveData μ μΈ μ](#ViewModelμμ-MutableLiveData/LiveData-μ μΈ-μ)
  * [Presentation Modelμ μ¬μ©νλ κ²½μ°](#Presentation-Modelμ-μ¬μ©νλ-κ²½μ°)


# μκ° π
π νλ¦½μ μλλ‘μ΄λ κ°λ°μλ€μ μν `Kotlin` μ€νμΌ κ°μ΄λ λ¬Έμμλλ€. π  

ν΄λΉ λ¬Έμλ kotlinlang.orgμ [Kotlin Style Guide](https://developer.android.com/kotlin/style-guide),  Googleμ [Android Kotlin Style Guide](https://developer.android.com/kotlin/style-guide)λ₯Ό κΈ°λ°μΌλ‘ λ§λ€μ΄ μ‘μ΅λλ€.  

# μμ€ μ½λ κ΅¬μ±
> [**μμ€ μ½λλ μ¬λμ΄ λ΄λλ€.**](https://developer.android.com/kotlin/style-guide#top-level_declarations) 
>   
> νμΌμ λ΄μ©μ λ¨μΌ νλ§μ μ΄μ μ λ§μΆ°μΌ ν©λλ€. κ΄λ ¨ μλ μ μΈμ μμ²΄ νμΌλ‘ λΆλ¦¬ν΄μΌ νλ©° λ¨μΌ νμΌ λ΄μ κ³΅κ° μ μΈμ μ΅μνν΄μΌ ν©λλ€.
>    
> μμ€ νμΌμ μΌλ°μ μΌλ‘ μμμ μλλ‘ μ½λλ€λ κ²μ μλ―Έν©λλ€. μ¦, μμλ μΌλ°μ μΌλ‘ μμ μ μΈμ΄ νμ μ μΈμ λν μ΄ν΄λ₯Ό μλ €μ€λ€λ κ²μ λ°μν΄μΌ ν©λλ€.

## μμ€ νμΌ κ΅¬μ±
* λμΌν Kotlin μμ€ νμΌμ μ¬λ¬ κ°μ μ΅μμ ν΄λμ€/ν¨μ/μμ±μ λ°°μΉνλ κ²μ μ§μν©λλ€.
  * **Badπ**
    ```kotlin
    // MyActivities.kt
    class MainActivity { } 
    class HomeActivity { } 
    class MyPageActivity { } 
    ```
  * λ€λ§, μ΄λ¬ν μ μΈμ΄ μλ―Έμ μΌλ‘ μλ‘ λ°μ νκ² κ΄λ ¨λμ΄ μκ³  νμΌ ν¬κΈ°κ° ν©λ¦¬μ μΌλ‘ μ μ§λ  λλ νμ©ν©λλ€.

## ν΄λμ€ λ μ΄μμ
* ν΄λμ€μ λ΄μ©μ λ€μκ³Ό κ°μ μμλ‘ μμ±ν  κ²μ κΆμ₯ν©λλ€.
  1. Companion object
  2. μμ± μ μΈ
  3. μ΄κΈ°ν λΈλ‘
  4. λ³΄μ‘° μμ±μ
  5. ν¨μ μ μΈ
* ν¨μ μ μΈ μμλ μμμ μλλ‘ μ½μ λ λ‘μ§μ μ νμν  μ μλλ‘ ν©λλ€.
* Inner Classλ μ§μν©λλ€.
  * μλͺ»λ μ¬μ©μΌλ‘ μΈν΄ λ©λͺ¨λ¦¬ λμλ₯Ό μ λ°ν  μ μμ΅λλ€.

## μΈν°νμ΄μ€ κ΅¬ν λ μ΄μμ
* μΈν°νμ΄μ€λ₯Ό κ΅¬νν  λλ κ΅¬ννλ κ΅¬μ±μμ μΈν°νμ΄μ€μ κ΅¬μ±μκ³Ό κ°μ μμλ₯Ό μ μ§ν©λλ€.
  * **Goodπ**
    ```kotlin
    interface Foo {

        fun foo1() 

        fun foo2() 

        fun foo3() 
    }
    class FooImpl : Foo { 

        override fun foo1() { }

        override fun foo2() { }

        override fun foo3() { }
    } 
    ```
  * **Badπ**
    ```kotlin
    interface Foo {

        fun foo1() 

        fun foo2() 

        fun foo3() 
    }
    class FooImpl : Foo { 

        override fun foo3() { }

        override fun foo2() { }

        override fun foo1() { }
    } 
    ```


# λ€μ΄λ° κ·μΉ
> [**μ’μ μ΄λ¦μ μκ°νμΈμ.**](https://kotlinlang.org/docs/coding-conventions.html#choose-good-names)  
>  
> μ΄λ¦μ μν°ν°μ λͺ©μ μ΄ λ¬΄μμΈμ§ λͺνν΄μΌ νλ―λ‘ μ΄λ¦μ μλ―Έ μλ λ¨μ΄(`Manager`, `Wrapper`, `Helper`, `Util`)λ₯Ό μ¬μ©νμ§ μλ κ²μ΄ κ°μ₯ μ’μ΅λλ€.

## λͺ¨λ
* λͺ¨λ μ΄λ¦μ ν­μ μλ¬Έμλ§μ μ¬μ©ν©λλ€.
* μ¬λ¬ λ¨μ΄λ‘ λ μ΄λ¦μ μ¬μ©ν  λλ `-`λ₯Ό μ¬μ©νμ¬ μ°κ²°νμ¬ μλλ€.
  * **Goodπ**
    ```
    example-module-name
    ```
  * **Badπ**
    ```
    example_module_name
    // λλ
    ExampleModuleName
    ```

## ν¨ν€μ§
* ν¨ν€μ§ μ΄λ¦μ ν­μ μλ¬Έμλ§μ μ¬μ©ν©λλ€.
* μ¬λ¬ λ¨μ΄λ‘ λ μ΄λ¦μ μ¬μ©νλ κ²μ μ§μνμ§λ§ μ¬λ¬ λ¨μ΄λ₯Ό μ¬μ©ν΄μΌ νλ κ²½μ°μλ μλ¬Έμ κ·Έλλ‘ λΆμ¬ μλλ€.
  * **Goodπ**
    ```kotlin
    package com.example.deepspace
    ```
  * **Badπ**
    ```kotlin
    package com.example.deepSpace
    // λλ
    package com.example.deep_space
    ```

## μμ€ νμΌ
* μμ€ νμΌμ μ΅μμ ν΄λμ€κ° νλλ§ ν¬ν¨λ κ²½μ° νμΌ μ΄λ¦μ ν΄λμ€μ μ΄λ¦κ³Ό κ°κ² ν©λλ€.
  * **Goodπ**
    ```kotlin
    // MainActivity.kt
    class MainActivity { } 
    ```
  * **Badπ**
    ```kotlin
    // MyMainFile.kt
    class MainActivity { } 
    ```
* μμ€ νμΌμ μ¬λ¬ κ°μ μ΅μμ μ μΈμ΄ ν¬ν¨λ κ²½μ° νμΌμ λ΄μ©μ μ€λͺνλ μ΄λ¦μ μ§μ΅λλ€.
  * **Goodπ**
    ```kotlin
    // MapExt.kt
    fun <T, O> Set<T>.map(func: (T) -> O): List<O> = // β¦
    fun <T, O> List<T>.map(func: (T) -> O): List<O> = // β¦
    ```
  * **Badπ**
    ```kotlin
    // SetMapExtenstion.kt
    fun <T, O> Set<T>.map(func: (T) -> O): List<O> = // β¦
    fun <T, O> List<T>.map(func: (T) -> O): List<O> = // β¦
    ```

## ν΄λμ€
* ν΄λμ€ μ΄λ¦μ `PascalCase`λ‘ μμ±λλ©°, μΌλ°μ μΌλ‘ λͺμ¬ λλ λͺμ¬κ΅¬λ₯Ό μ¬μ©ν©λλ€.
  * **Goodπ**
    ```kotlin
    class FileReader { }
    ```
  * **Badπ**
    ```kotlin
    class ReadFile { }
    ```
  * λ€λ§, `UseCase` ν΄λμ€ μμ± μμλ λμ¬κ΅¬λ₯Ό νμ©ν©λλ€.
    ```kotlin
    class ReadFileUseCase { }
    ```
* `UseCase` ν΄λμ€λ₯Ό μμ±ν  λ `xxxUseCase`μ νμμ λ§μΆ₯λλ€.
* λλ©μΈ λͺ¨λΈμ κ²½μ° APIμμ μ ν μ΄λ¦μ μ¬μ©ν©λλ€.
  * μλ² κ°λ°μμ μνν μν΅μ μν¨ μλλ€.
* λλ©μΈ λͺ¨λΈμ λ§΅νν νλ μ  νμ΄μ λͺ¨λΈμ μ΄λ¦μ μν©μ λ§κ² μμ±ν©λλ€.
  * λ§λν μ΄λ¦μ΄ μλ€λ©΄ `(λλ©μΈλͺ¨λΈλͺ)Presentation` ννλ₯Ό μ¬μ©ν©λλ€.
    * μ => `CurriculumPresentaion`

## μΈν°νμ΄μ€
* μΈν°νμ΄μ€ μ΄λ¦μ ν΄λμ€ μ΄λ¦κ³Ό λμΌν κ·μΉμ κ°μ§λ§ λλ‘λ νμ©μ¬ λλ νμ©μ¬κ΅¬λ₯Ό μ¬μ©ν  μ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    interface ReadableFile { }
    ```

## ν¨μ
* ν¨μ μ΄λ¦μ `camelCase`λ‘ μμ±λλ©°, μΌλ°μ μΌλ‘ λμ¬ λλ λμ¬κ΅¬λ₯Ό μ¬μ©ν©λλ€.
  * **Goodπ**
    ```kotlin
    fun readFile() { }
    ```
  * **Badπ**
    ```kotlin
    fun fileRead() { }
    ```
* Activity λλ Fragmentμμ ViewModelμ LiveDataλ₯Ό `observe()`νλ ν¨μμ μ΄λ¦μ `initObserve()`λ₯Ό μ¬μ©ν©λλ€.
  * **Goodπ**
    ```kotlin
    // FooViewModel.kt
    class FooViewModel : ViewModel() {

        val foo = MutableLiveData<Foo>()
    }
    // FooActivity.kt
    @AndroidEntryPoint
    class FooActivity {

        val viewModel: FooViewModel by viewModels()
    
        fun initObserve() {
            viewModel.foo.observe(this, { })
        }
    }
    ```

## λ³μ
* λ³μ μ΄λ¦μ `camelCase`λ‘ μμ±λλ©°, μΌλ°μ μΌλ‘ λͺμ¬ λλ λͺμ¬κ΅¬λ₯Ό μ¬μ©ν©λλ€.
* λ°°μ΄ λλ λ¦¬μ€νΈμ κ°μ λ³΅μμ μλ―Έλ₯Ό λ΄κ³ μλ λ³μλΌλ©΄ μ΄λ¦μ λ³΅μνμΌλ‘ μ¬μ©ν©λλ€.
* Boolean νμμ λ³μλ `is` μ λμ¬λ₯Ό λΆνλλ€.
  * **Goodπ**
    ```kotlin
    val categories: List<Category>
    val userInfo: UserInfo
    val isFinished: Boolean
    ```
  * **Badπ**
    ```kotlin
    val categoryList: List<String>
    val finished: Boolean
    ```
* `Backing Properties`μ κ²½μ°λ Mutableν λ³μμ μ΄λ¦μ `_` μ λμ¬λ₯Ό λΆνλλ€.
  * **Goodπ**
    ```kotlin
    private val _categories = mutableListOf<Category>()
    val categories: List<Category> get() = _categories
    ```

## μμ
* μμ μ΄λ¦μ `UPPER_SNAKE_CASE`λ‘ μμ±λλ©°, μΌλ°μ μΌλ‘ λͺμ¬ λλ λͺμ¬κ΅¬λ₯Ό μ¬μ©ν©λλ€.
* λ°°μ΄ λλ λ¦¬μ€νΈμ κ°μ λ³΅μμ μλ―Έλ₯Ό λ΄κ³ μλ λ³μλΌλ©΄ μ΄λ¦μ λ³΅μνμΌλ‘ μ¬μ©ν©λλ€.
* μ΅μμ Primitives μμ±μ΄λΌλ©΄ ν­μ `const` ν€μλλ₯Ό λΆνλλ€.
  * **Goodπ**
    ```kotlin
    const val NUMBER = 5
    val NAMES = listOf("Alice", "Bob")
    val AGES = mapOf("Alice" to 35, "Bob" to 32)
    val COMMA_JOINER = Joiner.on(',') // Joiner is immutable
    val EMPTY_ARRAY = arrayOf()
    ```

## enum
* Enum ν΄λμ€ μ΄λ¦μ `PascalCase`λ‘ μμ±λλ©°, μΌλ°μ μΌλ‘ λͺμ¬ λλ λͺμ¬κ΅¬λ₯Ό μ¬μ©ν©λλ€.
* Enum ν΄λμ€ λ΄λΆμ μμ μ΄λ¦μ `UPPER_SNAKE_CASE`λ‘ μμ±λλ©°, μΌλ°μ μΌλ‘ λͺμ¬ λλ λͺμ¬κ΅¬λ₯Ό μ¬μ©ν©λλ€.
  * **Goodπ**
    ```kotlin
    enum class LoadState {
        LOADING, 
        SUCCESS, 
        FAILURE
    }
    ```

## μ½μ΄
* μ½μ΄λ‘ μμνλ κ²½μ°μλ μλ¬Έμλ₯Ό μ¬μ©ν©λλ€.
* μ½μ΄κ° μ€κ°μ λ€μ΄κ°λ€λ©΄ μ½μ΄μ μ²«κΈμλ λλ¬Έμλ₯Ό μ¬μ©ν©λλ€.
  * **Goodπ**
    ```kotlin
    val userId: String
    val html: String
    val imageUrl: String
    ```
  * **Badπ**
    ```kotlin
    val userID: String
    val HTML: String
    val imageURL: String
    ```

# μμ

## μ΅λ μ€κΈΈμ΄
* ν μ€μ μ΅λ κΈΈμ΄λ **100μ** μλλ€.

## λ€μ¬μ°κΈ°
* λ€μ¬μ°κΈ°λ **4space** μλλ€.

## κ°λ‘ κ³΅λ°±
* λ¨ν­ μ°μ°μ μ£Όμμ κ³΅λ°±μ λ£μ§ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    a++
    ```
  * **Badπ**
    ```kotlin
    a ++
    ```
* μ΄ν­ μ°μ°μ μ£Όμμ κ³΅λ°±μ λ£μ΅λλ€.
  * **Goodπ**
    ```kotlin
    val sum = 20 + 20
    ```
  * **Badπ**
    ```kotlin
    val sum = 20+20
    ```
  * λ€λ§, λ²μ μ°μ°μμ κ²½μ° κ³΅λ°±μ λ£μ§ μμ΅λλ€.
    ```kotlin
    val randomValue = (0..10).random()
    ```
* μ μ΄ νλ¦ ν€μλ(`if`, `when`, `for`, `while` λ±) λ€μ μ¬λ κ΄νΈ μμ κ³΅λ°±μ λ£μ΅λλ€.
  * **Goodπ**
    ```kotlin
    if (a == b) { }
    ```
  * **Badπ**
    ```kotlin
    if(a == b) { }
    ```
* κΈ°λ³Έ μμ±μ μ μΈ, λ©μλ μ μΈ λλ λ©μλ νΈμΆμμ μ¬λ κ΄νΈ μμ κ³΅λ°±μ λ£μ§ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    class A(val x: Int)

    fun foo(x: Int) { }

    fun bar() {
        foo(1)
    }
    ```
  * **Badπ**
    ```kotlin
    class A (val x: Int)

    fun foo (x: Int) { }

    fun bar() {
        foo (1)
    }
    ```
* `.` λλ `?.` μ£Όμμ κ³΅λ°±μ λ£μ§ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    foo.bar().filter { it > 2 }.joinToString()

    foo?.bar()
    ```
  * **Badπ**
    ```kotlin
    foo . bar() . filter { it > 2 } . joinToString()

    foo ?. bar()
    ```
* `//` λ€μ κ³΅λ°±μ λ£μ΅λλ€.
  * **Goodπ**
    ```kotlin
    // μ£Όμ μλλ€.
    ```
  * **Badπ**
    ```kotlin
    //μ£Όμ μλλ€.
    ```
* μ ν λ§€κ°λ³μλ₯Ό μ§μ νλλ° μ¬μ©λλ κΊΎμ  κ΄νΈ μ£Όμμ κ³΅λ°±μ λ£μ§ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    class Map<K, V> { }
    ```
  * **Badπ**
    ```kotlin
    class Map < K, V > { }
    ```
* `::` μ£Όμμ κ³΅λ°±μ λ£μ§ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    Foo::class
    ```
  * **Badπ**
    ```kotlin
    Foo :: class
    ```
* `?` nullable νμμ νκΈ°νλλ° μ¬μ©ν  λ μ£Όμμ κ³΅λ°±μ λ£μ§ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    String?
    ```
  * **Badπ**
    ```kotlin
    String ?
    ```
* `:` κΈ°νΈλ λλΆλΆ λ€μλ§ κ³΅λ°±μ λ£μ΅λλ€.
  * λ€λ§, λ€μκ³Ό κ°μ κ²½μ°μλ μμλ κ³΅λ°±μ λ£μ΅λλ€.
    * μ νκ³Ό μμ μ νμ λΆλ¦¬νλ λ° μ¬μ©λλ κ²½μ°
    * μνΌν΄λμ€ μμ±μλ κ°μ ν΄λμ€μ λ€λ₯Έ μμ±μμκ² μμν  λ
    * objectν€μλ λ€μ
  * **Goodπ**
    ```kotlin
    abstract class Foo<out T : Any> : IFoo {

        abstract fun foo(a: Int): T
    }

    class FooImpl : Foo() {

        constructor(x: String) : this(x) { }

        val x = object : IFoo { }
    }
    ```
  * **Badπ**
    ```kotlin
    abstract class Foo<out T:Any>:IFoo {

        abstract fun foo(a : Int):T
    }

    class FooImpl: Foo() {

        constructor(x : String) : this(x) { }

        val x = object:IFoo { }
    }
    ```

## μ€λ°κΏ
* ν΄λμ€μ μ΄λ¦ λλ κΈ°λ³Έ μμ±μ λ§€κ°λ³μκ° κΈΈ κ²½μ° μ€λ°κΏ ν©λλ€.
  * **Goodπ**
    ```kotlin
    class Person(
        val id: String,
        val name: String,
        val age: Int,
        val address: String
    ) : Human(id, name) { }
    ```
  * **Badπ**
    ```kotlin
    class Person(val id: String, val name: String, val age: Int, val address: String) : Human(id, name) { }
    ```
* ν¨μμ μ΄λ¦ λλ λ§€κ°λ³μκ° κΈΈ κ²½μ° μ€λ°κΏ ν©λλ€.
  * **Goodπ**
    ```kotlin
    fun longFunctionName(
        argument: Int,
        argument2: Int,
        argument3: Int,
        argument4: Int
    ): Int {
    // body
    }
    ```
  * **Badπ**
    ```kotlin
    fun longFunctionName(argument: Int, argument2: Int, argument3: Int, argument4: Int): Int { }
    ```
* λ³μμ μ΄λ¦ λλ νμλͺμ΄ κΈΈ κ²½μ° μ€λ°κΏ ν©λλ€.
  * **Goodπ**
    ```kotlin
    val longNameVariable: LongStringVerySoTooMuchLongLongType = 
        LongStringVerySoTooMuchLongLongType()
    ```
  * **Badπ**
    ```kotlin
    val longNameVariable: LongStringVerySoTooMuchLongLongType = LongStringVerySoTooMuchLongLongType()
    ```
* `class`/`object`/`interface` λ³Έλ¬Έμ μ²« μ€μ ν­μ κ³΅λ°±μΌλ‘ λ‘λλ€.
  * **Goodπ**
    ```kotlin
    class A {

        fun foo() { }
    }
    object A {

        fun foo() { }
    }
    interface A {

        fun foo()
    }
    ```
  * **Badπ**
    ```kotlin
    class A {
        fun foo() { }
    }
    object A {
        fun foo() { }
    }
    interface A {
        fun foo()
    }
    ```
* `else`, `catch`, `finally` ν€μλλ μμ λ«λ κ΄νΈμ κ°μ μ€μ λ‘λλ€.
  * **Goodπ**
    ```kotlin
    if (condition) {
        // body
    } else {
        // else part
    }

    try {
        // body
    } catch(e: Throwable) {
        // handling error
    } finally {
        // cleanup
    }
    ```
  * **Badπ**
    ```kotlin
    if (condition) {
        // body
    } 
    else {
        // else part
    }

    try {
        // body
    } 
    catch(e: Throwable) {
        // handling error
    } 
    finally {
        // cleanup
    }
    ```
* `when` ν€μλ μ¬μ© μ μ‘°κ±΄ λλ λΆκΈ° λ³Έλ¬Έμ΄ μ§§μΌλ©΄ ν μ€λ‘ μμ±ν©λλ€.
  * **Goodπ**
    ```kotlin
    when (condition) {
        true -> bar()
        false -> baz()
    }
    ```
  * **Badπ**
    ```kotlin
    when (condition) {
        true -> {
            bar()
        }
        false -> {
            baz()
        }
    }
    ```
* `when` ν€μλ μ¬μ© μ μ‘°κ±΄ λλ λΆκΈ° λ³Έλ¬Έμ΄ κΈΈλ©΄ κ΄νΈλ‘ λ¬Άκ³  μ€λ°κΏ ν©λλ€.
  * **Goodπ**
    ```kotlin
    when (condition) {
        true -> {
            tooooooooooooooooooooooloooooooooooooongFunctionName()
        }
        false -> {
            tooooooooooooooooooooooloooooooooooooongFunctionName2()
        }
    }
    ```
  * **Badπ**
    ```kotlin
    when (condition) {
        true -> tooooooooooooooooooooooloooooooooooooongFunctionName()
        false -> tooooooooooooooooooooooloooooooooooooongFunctionName2()
    }
    ```
* `Method chaining` μ¬μ© μ `.` λλ `?.` μμμ μ€λ°κΏ ν©λλ€.
  * **Goodπ**
    ```kotlin
    val anchor = owner
        ?.firstChild!!
        .siblings(forward = true)
        .dropWhile { it is PsiComment || it is PsiWhiteSpace }
    ```
  * **Badπ**
    ```kotlin
    val anchor = owner?.firstChild!!.siblings(forward = true).dropWhile { it is PsiComment || it is PsiWhiteSpace }
    ```
* λ¨μν μ½κΈ° μ μ© μμ±μ κ²½μ° ν μ€λ‘ νμν  μ μμ΅λλ€.
  * **Goodπ**
    ```kotlin
    val isEmpty: Boolean get() = size == 0
    ```
  * **Badπ**
    ```kotlin
    val isEmpty: Boolean 
        get() = size == 0
    ```
# κΈ°ν

## Propertiesο»Ώ vs Functions 
* μ΄λ€ κ²½μ°μλ μΈμκ° μλ ν¨μκ° μ½κΈ° μ μ© μμ±μΌλ‘ κ΅μ²΄λ  μ μμ΅λλ€.
* μλ―Έλ λΉμ·νμ§λ§ μ½κΈ° μ μ© μμ±μΌλ‘ κ΅μ²΄νλ €λ©΄ λ€μκ³Ό κ°μ κ·μΉμ μ§μΌμΌ ν©λλ€.
  * μμΈλ₯Ό λμ§μ§ μλλ€.
  * κ³μ° λΉμ©μ΄ μ λ ΄νλ€.
  * κ°μ²΄ μνκ° λ³κ²½λμ§ μμ κ²½μ° νΈμΆμ λν΄ λμΌν κ²°κ³Όλ₯Ό λ°ννλ€.
  * **Goodπ**
    ```kotlin
    class FooAdapter(val list: List<Int>) {

        val isEmpty: Boolean get() = list.size == 0
    } 
    ```
  * **Badπ**
    ```kotlin
    class FooAdapter(val list: List<Int>) {

        fun getIsEmpty(): Boolean {
            return list.size == 0
        }
    } 
    ```

## ViewModelμμ MutableLiveData/LiveData μ μΈ μ
* MutableLiveData/LiveData λ³μλ λͺ¨λ `Backing Properties` νμμ μ¬μ©ν©λλ€.
  * **Goodπ**
    ```kotlin
    private val _categories = MutableLiveData<List<Category>>()
    val categories: LiveData<List<Category>> get() = _categories
    ```
  * λ€λ§, `two-way binding`μ νλ κ²½μ°μ MutableLiveDataλ₯Ό publicμΌλ‘ μ μΈν  μ μμ΅λλ€.
    ```kotlin
    val nickname = MutableLiveData<String>()
    val email = MutableLiveData<String>()
    ```

## Presentation Modelμ μ¬μ©νλ κ²½μ°
* νλ μ  νμ΄μ λ μ΄μ΄μμλ§ μ¬μ©ν  λͺ¨λΈμ΄ νμν κ²½μ°
  * `LoadState` λ±
* λ°μ΄ν°λ°μΈλ© ν  λ λλ©μΈ λͺ¨λΈμ κ·Έλλ‘ μ¬μ©νκΈ° μ΄λ €μ΄ κ²½μ°
  * λλ©μΈ λͺ¨λΈμ κΈ°λ°μΌλ‘ ν νλ μ  νμ΄μ λͺ¨λΈμ μ μνκ³  λ§΅ννμ¬ μ¬μ©ν©λλ€.
  * λ§΅ν λ‘μ§μ λλ©μΈ λͺ¨λΈμ νμ₯ ν¨μλ₯Ό μ μνμ¬ `ViewModel`μμ νΈμΆνμ¬ μ¬μ©ν©λλ€.