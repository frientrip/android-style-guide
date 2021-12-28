- [소개 💁](#소개)
- [소스 코드 구성](#소스-코드-구성)
  * [소스 파일 구성](#소스-파일-구성)
  * [클래스 레이아웃](#클래스-레이아웃)
  * [인터페이스 구현 레이아웃](#인터페이스-구현-레이아웃)
- [네이밍 규칙](#네이밍-규칙)
  * [모듈](#모듈)
  * [패키지](#패키지)
  * [소스 파일](#소스-파일)
  * [클래스](#클래스)
  * [인터페이스](#인터페이스)
  * [함수](#함수)
  * [변수](#변수)
  * [상수](#상수)
  * [enum](#enum)
  * [약어](#약어)
- [서식](#서식)
  * [최대 줄길이](#최대-줄길이)
  * [들여쓰기](#들여쓰기)
  * [가로 공백](#가로-공백)
  * [줄바꿈](#줄바꿈)
- [기타](#기타)
  * [Properties vs Functions](#properties-vs-functions)
  * [ViewModel에서 MutableLiveData/LiveData 선언 시](#ViewModel에서-MutableLiveData/LiveData-선언-시)
  * [Presentation Model을 사용하는 경우](#Presentation-Model을-사용하는-경우)


# 소개 💁
🎉 프립의 안드로이드 개발자들을 위한 `Kotlin` 스타일 가이드 문서입니다. 🎉  

해당 문서는 kotlinlang.org의 [Kotlin Style Guide](https://developer.android.com/kotlin/style-guide),  Google의 [Android Kotlin Style Guide](https://developer.android.com/kotlin/style-guide)를 기반으로 만들어 졌습니다.  

# 소스 코드 구성
> [**소스 코드는 사람이 봅니다.**](https://developer.android.com/kotlin/style-guide#top-level_declarations) 
>   
> 파일의 내용은 단일 테마에 초점을 맞춰야 합니다. 관련 없는 선언은 자체 파일로 분리해야 하며 단일 파일 내의 공개 선언은 최소화해야 합니다.
>    
> 소스 파일은 일반적으로 위에서 아래로 읽는다는 것을 의미합니다. 즉, 순서는 일반적으로 상위 선언이 하위 선언에 대한 이해를 알려준다는 것을 반영해야 합니다.

## 소스 파일 구성
* 동일한 Kotlin 소스 파일에 여러 개의 최상위 클래스/함수/속성을 배치하는 것은 지양합니다.
  * **Bad👎**
    ```kotlin
    // MyActivities.kt
    class MainActivity { } 
    class HomeActivity { } 
    class MyPageActivity { } 
    ```
  * 다만, 이러한 선언이 의미적으로 서로 밀접하게 관련되어 있고 파일 크기가 합리적으로 유지될 때는 허용합니다.

## 클래스 레이아웃
* 클래스의 내용은 다음과 같은 순서로 작성할 것을 권장합니다.
  1. Companion object
  2. 속성 선언
  3. 초기화 블록
  4. 보조 생성자
  5. 함수 선언
* 함수 선언 순서는 위에서 아래로 읽을 때 로직을 잘 파악할 수 있도록 합니다.
* Inner Class는 지양합니다.
  * 잘못된 사용으로 인해 메모리 누수를 유발할 수 있습니다.

## 인터페이스 구현 레이아웃
* 인터페이스를 구현할 때는 구현하는 구성원을 인터페이스의 구성원과 같은 순서를 유지합니다.
  * **Good👏**
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
  * **Bad👎**
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


# 네이밍 규칙
> [**좋은 이름을 생각하세요.**](https://kotlinlang.org/docs/coding-conventions.html#choose-good-names)  
>  
> 이름은 엔티티의 목적이 무엇인지 명확해야 하므로 이름에 의미 없는 단어(`Manager`, `Wrapper`, `Helper`, `Util`)를 사용하지 않는 것이 가장 좋습니다.

## 모듈
* 모듈 이름은 항상 소문자만을 사용합니다.
* 여러 단어로 된 이름을 사용할 때는 `-`를 사용하여 연결하여 씁니다.
  * **Good👏**
    ```
    example-module-name
    ```
  * **Bad👎**
    ```
    example_module_name
    // 또는
    ExampleModuleName
    ```

## 패키지
* 패키지 이름은 항상 소문자만을 사용합니다.
* 여러 단어로 된 이름을 사용하는 것은 지양하지만 여러 단어를 사용해야 하는 경우에는 소문자 그대로 붙여 씁니다.
  * **Good👏**
    ```kotlin
    package com.example.deepspace
    ```
  * **Bad👎**
    ```kotlin
    package com.example.deepSpace
    // 또는
    package com.example.deep_space
    ```

## 소스 파일
* 소스 파일에 최상위 클래스가 하나만 포함된 경우 파일 이름은 클래스의 이름과 같게 합니다.
  * **Good👏**
    ```kotlin
    // MainActivity.kt
    class MainActivity { } 
    ```
  * **Bad👎**
    ```kotlin
    // MyMainFile.kt
    class MainActivity { } 
    ```
* 소스 파일에 여러 개의 최상위 선언이 포함된 경우 파일의 내용을 설명하는 이름을 짓습니다.
  * **Good👏**
    ```kotlin
    // MapExt.kt
    fun <T, O> Set<T>.map(func: (T) -> O): List<O> = // …
    fun <T, O> List<T>.map(func: (T) -> O): List<O> = // …
    ```
  * **Bad👎**
    ```kotlin
    // SetMapExtenstion.kt
    fun <T, O> Set<T>.map(func: (T) -> O): List<O> = // …
    fun <T, O> List<T>.map(func: (T) -> O): List<O> = // …
    ```

## 클래스
* 클래스 이름은 `PascalCase`로 작성되며, 일반적으로 명사 또는 명사구를 사용합니다.
  * **Good👏**
    ```kotlin
    class FileReader { }
    ```
  * **Bad👎**
    ```kotlin
    class ReadFile { }
    ```
  * 다만, `UseCase` 클래스 작성 시에는 동사구를 허용합니다.
    ```kotlin
    class ReadFileUseCase { }
    ```
* `UseCase` 클래스를 작성할 땐 `xxxUseCase`의 형식을 맞춥니다.
* 도메인 모델의 경우 API에서 정한 이름을 사용합니다.
  * 서버 개발자와 원활한 소통을 위함 입니다.
* 도메인 모델을 맵핑한 프레젠테이션 모델의 이름은 상황에 맞게 작성합니다.
  * 마땅한 이름이 없다면 `(도메인모델명)Presentation` 형태를 사용합니다.
    * 예 => `CurriculumPresentaion`

## 인터페이스
* 인터페이스 이름은 클래스 이름과 동일한 규칙을 갖지만 때로는 형용사 또는 형용사구를 사용할 수 있습니다.
  * **Good👏**
    ```kotlin
    interface ReadableFile { }
    ```

## 함수
* 함수 이름은 `camelCase`로 작성되며, 일반적으로 동사 또는 동사구를 사용합니다.
  * **Good👏**
    ```kotlin
    fun readFile() { }
    ```
  * **Bad👎**
    ```kotlin
    fun fileRead() { }
    ```
* Activity 또는 Fragment에서 ViewModel의 LiveData를 `observe()`하는 함수의 이름은 `initObserve()`를 사용합니다.
  * **Good👏**
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

## 변수
* 변수 이름은 `camelCase`로 작성되며, 일반적으로 명사 또는 명사구를 사용합니다.
* 배열 또는 리스트와 같은 복수의 의미를 담고있는 변수라면 이름을 복수형으로 사용합니다.
* Boolean 타입의 변수는 `is` 접두사를 붙힙니다.
  * **Good👏**
    ```kotlin
    val categories: List<Category>
    val userInfo: UserInfo
    val isFinished: Boolean
    ```
  * **Bad👎**
    ```kotlin
    val categoryList: List<String>
    val finished: Boolean
    ```
* `Backing Properties`의 경우는 Mutable한 변수의 이름에 `_` 접두사를 붙힙니다.
  * **Good👏**
    ```kotlin
    private val _categories = mutableListOf<Category>()
    val categories: List<Category> get() = _categories
    ```

## 상수
* 상수 이름엔 `UPPER_SNAKE_CASE`로 작성되며, 일반적으로 명사 또는 명사구를 사용합니다.
* 배열 또는 리스트와 같은 복수의 의미를 담고있는 변수라면 이름을 복수형으로 사용합니다.
* 최상위 Primitives 속성이라면 항상 `const` 키워드를 붙힙니다.
  * **Good👏**
    ```kotlin
    const val NUMBER = 5
    val NAMES = listOf("Alice", "Bob")
    val AGES = mapOf("Alice" to 35, "Bob" to 32)
    val COMMA_JOINER = Joiner.on(',') // Joiner is immutable
    val EMPTY_ARRAY = arrayOf()
    ```

## enum
* Enum 클래스 이름은 `PascalCase`로 작성되며, 일반적으로 명사 또는 명사구를 사용합니다.
* Enum 클래스 내부의 상수 이름은 `UPPER_SNAKE_CASE`로 작성되며, 일반적으로 명사 또는 명사구를 사용합니다.
  * **Good👏**
    ```kotlin
    enum class LoadState {
        LOADING, 
        SUCCESS, 
        FAILURE
    }
    ```

## 약어
* 약어로 시작하는 경우에는 소문자를 사용합니다.
* 약어가 중간에 들어간다면 약어의 첫글자는 대문자를 사용합니다.
  * **Good👏**
    ```kotlin
    val userId: String
    val html: String
    val imageUrl: String
    ```
  * **Bad👎**
    ```kotlin
    val userID: String
    val HTML: String
    val imageURL: String
    ```

# 서식

## 최대 줄길이
* 한 줄의 최대 길이는 **100자** 입니다.

## 들여쓰기
* 들여쓰기는 **4space** 입니다.

## 가로 공백
* 단항 연산자 주위에 공백을 넣지 않습니다.
  * **Good👏**
    ```kotlin
    a++
    ```
  * **Bad👎**
    ```kotlin
    a ++
    ```
* 이항 연산자 주위에 공백을 넣습니다.
  * **Good👏**
    ```kotlin
    val sum = 20 + 20
    ```
  * **Bad👎**
    ```kotlin
    val sum = 20+20
    ```
  * 다만, 범위 연산자의 경우 공백을 넣지 않습니다.
    ```kotlin
    val randomValue = (0..10).random()
    ```
* 제어 흐름 키워드(`if`, `when`, `for`, `while` 등) 뒤에 여는 괄호 앞에 공백을 넣습니다.
  * **Good👏**
    ```kotlin
    if (a == b) { }
    ```
  * **Bad👎**
    ```kotlin
    if(a == b) { }
    ```
* 기본 생성자 선언, 메서드 선언 또는 메서드 호출에서 여는 괄호 앞에 공백을 넣지 않습니다.
  * **Good👏**
    ```kotlin
    class A(val x: Int)

    fun foo(x: Int) { }

    fun bar() {
        foo(1)
    }
    ```
  * **Bad👎**
    ```kotlin
    class A (val x: Int)

    fun foo (x: Int) { }

    fun bar() {
        foo (1)
    }
    ```
* `.` 또는 `?.` 주위에 공백을 넣지 않습니다.
  * **Good👏**
    ```kotlin
    foo.bar().filter { it > 2 }.joinToString()

    foo?.bar()
    ```
  * **Bad👎**
    ```kotlin
    foo . bar() . filter { it > 2 } . joinToString()

    foo ?. bar()
    ```
* `//` 뒤에 공백을 넣습니다.
  * **Good👏**
    ```kotlin
    // 주석 입니다.
    ```
  * **Bad👎**
    ```kotlin
    //주석 입니다.
    ```
* 유형 매개변수를 지정하는데 사용되는 꺾쇠 괄호 주위에 공백을 넣지 않습니다.
  * **Good👏**
    ```kotlin
    class Map<K, V> { }
    ```
  * **Bad👎**
    ```kotlin
    class Map < K, V > { }
    ```
* `::` 주위에 공백을 넣지 않습니다.
  * **Good👏**
    ```kotlin
    Foo::class
    ```
  * **Bad👎**
    ```kotlin
    Foo :: class
    ```
* `?` nullable 형식을 표기하는데 사용할 때 주위에 공백을 넣지 않습니다.
  * **Good👏**
    ```kotlin
    String?
    ```
  * **Bad👎**
    ```kotlin
    String ?
    ```
* `:` 기호는 대부분 뒤에만 공백을 넣습니다.
  * 다만, 다음과 같을 경우에는 앞에도 공백을 넣습니다.
    * 유형과 상위 유형을 분리하는 데 사용되는 경우
    * 슈퍼클래스 생성자나 같은 클래스의 다른 생성자에게 위임할 때
    * object키워드 뒤에
  * **Good👏**
    ```kotlin
    abstract class Foo<out T : Any> : IFoo {

        abstract fun foo(a: Int): T
    }

    class FooImpl : Foo() {

        constructor(x: String) : this(x) { }

        val x = object : IFoo { }
    }
    ```
  * **Bad👎**
    ```kotlin
    abstract class Foo<out T:Any>:IFoo {

        abstract fun foo(a : Int):T
    }

    class FooImpl: Foo() {

        constructor(x : String) : this(x) { }

        val x = object:IFoo { }
    }
    ```

## 줄바꿈
* 클래스의 이름 또는 기본 생성자 매개변수가 길 경우 줄바꿈 합니다.
  * **Good👏**
    ```kotlin
    class Person(
        val id: String,
        val name: String,
        val age: Int,
        val address: String
    ) : Human(id, name) { }
    ```
  * **Bad👎**
    ```kotlin
    class Person(val id: String, val name: String, val age: Int, val address: String) : Human(id, name) { }
    ```
* 함수의 이름 또는 매개변수가 길 경우 줄바꿈 합니다.
  * **Good👏**
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
  * **Bad👎**
    ```kotlin
    fun longFunctionName(argument: Int, argument2: Int, argument3: Int, argument4: Int): Int { }
    ```
* 변수의 이름 또는 타입명이 길 경우 줄바꿈 합니다.
  * **Good👏**
    ```kotlin
    val longNameVariable: LongStringVerySoTooMuchLongLongType = 
        LongStringVerySoTooMuchLongLongType()
    ```
  * **Bad👎**
    ```kotlin
    val longNameVariable: LongStringVerySoTooMuchLongLongType = LongStringVerySoTooMuchLongLongType()
    ```
* `class`/`object`/`interface` 본문의 첫 줄은 항상 공백으로 둡니다.
  * **Good👏**
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
  * **Bad👎**
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
* `else`, `catch`, `finally` 키워드는 앞의 닫는 괄호와 같은 줄에 둡니다.
  * **Good👏**
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
  * **Bad👎**
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
* `when` 키워드 사용 시 조건 또는 분기 본문이 짧으면 한 줄로 작성합니다.
  * **Good👏**
    ```kotlin
    when (condition) {
        true -> bar()
        false -> baz()
    }
    ```
  * **Bad👎**
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
* `when` 키워드 사용 시 조건 또는 분기 본문이 길면 괄호로 묶고 줄바꿈 합니다.
  * **Good👏**
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
  * **Bad👎**
    ```kotlin
    when (condition) {
        true -> tooooooooooooooooooooooloooooooooooooongFunctionName()
        false -> tooooooooooooooooooooooloooooooooooooongFunctionName2()
    }
    ```
* `Method chaining` 사용 시 `.` 또는 `?.` 앞에서 줄바꿈 합니다.
  * **Good👏**
    ```kotlin
    val anchor = owner
        ?.firstChild!!
        .siblings(forward = true)
        .dropWhile { it is PsiComment || it is PsiWhiteSpace }
    ```
  * **Bad👎**
    ```kotlin
    val anchor = owner?.firstChild!!.siblings(forward = true).dropWhile { it is PsiComment || it is PsiWhiteSpace }
    ```
* 단순한 읽기 전용 속성의 경우 한 줄로 표시할 수 있습니다.
  * **Good👏**
    ```kotlin
    val isEmpty: Boolean get() = size == 0
    ```
  * **Bad👎**
    ```kotlin
    val isEmpty: Boolean 
        get() = size == 0
    ```
# 기타

## Properties﻿ vs Functions 
* 어떤 경우에는 인수가 없는 함수가 읽기 전용 속성으로 교체될 수 있습니다.
* 의미는 비슷하지만 읽기 전용 속성으로 교체하려면 다음과 같은 규칙을 지켜야 합니다.
  * 예외를 던지지 않는다.
  * 계산 비용이 저렴하다.
  * 객체 상태가 변경되지 않은 경우 호출에 대해 동일한 결과를 반환한다.
  * **Good👏**
    ```kotlin
    class FooAdapter(val list: List<Int>) {

        val isEmpty: Boolean get() = list.size == 0
    } 
    ```
  * **Bad👎**
    ```kotlin
    class FooAdapter(val list: List<Int>) {

        fun getIsEmpty(): Boolean {
            return list.size == 0
        }
    } 
    ```

## ViewModel에서 MutableLiveData/LiveData 선언 시
* MutableLiveData/LiveData 변수는 모두 `Backing Properties` 형식을 사용합니다.
  * **Good👏**
    ```kotlin
    private val _categories = MutableLiveData<List<Category>>()
    val categories: LiveData<List<Category>> get() = _categories
    ```
  * 다만, `two-way binding`을 하는 경우엔 MutableLiveData를 public으로 선언할 수 있습니다.
    ```kotlin
    val nickname = MutableLiveData<String>()
    val email = MutableLiveData<String>()
    ```

## Presentation Model을 사용하는 경우
* 프레젠테이션 레이어에서만 사용할 모델이 필요한 경우
  * `LoadState` 등
* 데이터바인딩 할 때 도메인 모델을 그대로 사용하기 어려운 경우
  * 도메인 모델을 기반으로 한 프레젠테이션 모델을 정의하고 맵핑하여 사용합니다.
  * 맵핑 로직은 도메인 모델에 확장 함수를 정의하여 `ViewModel`에서 호출하여 사용합니다.