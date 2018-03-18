# Ruby언어
## 참고자료
- [생활코딩 Python / Ruby](https://opentutorials.org/course/1750) : 꼼꼼하고 자세하게, 쉽게 설명
- [Ruby언어 정리(1)](http://kyunni22.tistory.com/9?category=518947) : 전 기수가 정리한 블로그
- [Ruby언어 정리(2)](http://seungdols.tistory.com/591) : 이것도 아마 전 기수가 정리한 블로그
- [Ruby Cheat Sheet (1)](http://www.cheat-sheets.org/saved-copy/RubyCheat.pdf) : 루비 문법이 헷갈릴 때 참고!
- [Ruby Cheat Sheet (2)](http://overapi.com/ruby/)
- [Ruby 공식 사이트](https://www.ruby-lang.org/ko/) : 한글사이트/ 번역이 어색함
- [Codecademy](https://www.codecademy.com/learn/learn-ruby) : 사전과제

### 사전과제
- Codecademy Ruby
    
### 개념
** 비전공자의 경우 매우매우 생소할 수 있으니 꼭 모든 것을 이해할 필요는 없다!  

0. irb  
    interactive ruby의 줄임말  
    한줄 한줄씩 코드를 입력하고 바로 확인할 수 있다.  
    bash창에 irb를 입력하면 irb콘솔을 사용할 수 있다.  
    종료할 때는 quit명령어 사용.

1. .rb 파일 실행하기  
    subin.rb 라는 이름의 파일을 실행하려 한다.  
    bash창(c9에서 하단에 위치)에 다음과 같은 명령어를 입력한다.      

    ```
    ruby subin.rb
    ```
    
2. 변수   
    수학에서의 변수 개념과 비슷하다.  
    어떠한 값을 담고 있는 '상자'라고 생각하면 편하다.  
    Ruby에서는 자료형을 선언해 줄 필요가 없다.  
    자료형에 대해서는 잠시 후에 알아보도록 하자.  
    전역 변수는 $로 시작하고, 인스턴스 변수는 @로 시작하며, 클래스 변수는 @@로 시작한다.  
    이것은 다음시간에 다시 자세히 설명하도록 하겠다.  
    ```
    x=4         # x라는 변수에 4라는 int(정수)값이 담겼다.
    y="hello"   # y라는 변수에 hello라는 string(문자열)값이 담겼다.
    
    ```
    
3. 자료형(Data Type)  
    자료의 형태, 즉 데이터의 타입.  
    4는 숫자(정수형), "hello"는 문자열(string) 형태이듯이 각 데이터마다 자료형이 정해져 있다.  
    앞에서 설명했듯이 루비에서는 변수를 선언할 때 자료형을 명시하지 않아도 된다.  
    (자동으로 자료형이 정해진다.)  
    따라서 루비에서는 자료형이 다른 언어만큼 중요하게 생각되지 않는다.  
    기본적인 자료형들만 알고 가도록 하자
    ```
    integer(int) : 숫자(정수형)
    float : 숫자(실수형)
    string : 문자열
    array :배열
    hash : 해쉬
    
    x=4
    x.class         # Integer (.class 라는 메소드로 자료형을 확인할 수 있다.)
    ```

4. 함수(function)  
    함수를 정의할 때는 def [함수이름] ~ end를 사용한다.  
    모든 함수는 return(반환)값이 있다.  
    return값을 명시하지 않을 경우 함수 안의 마지막 표현을 자동으로 반환한다.  

    ```
    def tell_the_truth
        puts "true"
    end
    # tell_the_truth 함수를 실행했을 때 true라는 문자열을 반환한다.
    
    tell_the_truth()        # 함수 호출 -> true값을 반환(출력)
    ```

5. 메소드  
    함수와 유사한 개념.  
    실제로 함수와 메소드라는 용어가 혼용되기 때문에 저도 헷갈립니다..  
    자주 사용되는 함수를 이미 만들어 놓았다는 개념으로 이해합시다.  
    사용방법은 [객체].[메소드]  
    - [string, array등 객체에 따라 사용되는 메소드를 잘 정리해놓은 블로그](http://jinbroing.tistory.com/31)

6. 입력  
    내가 키보드로 직접 입력한 값을 변수 등에 저장해야 할 때 사용한다.    
    gets라는 명령어를 사용한다.  
    주로 chomp라는 메소드와 함께 사용한다.  
    chomp는 문자열의 맨 뒤에 붙어 있는 엔터 키를 무시하도록 만든다.  
    ```
    name = gets.chomp       # 입력한 문자열이 name이라는 변수에 저장된다.
    ```

7. 출력  
    출력이란 화면에 보여지게 만드는 것을 뜻한다.  
    루비에서는 puts라는 명령어를 주로 사용한다.(put string의 줄임말)  
    puts는 개행문자를 포함한다. (출력하고 한 줄 enter포함)
    '' 작은 따옴표는 문자열 그대로를 의미, "" 큰 따옴표는 문자열을 해석한다.  
    (큰 차이는 없으니 어떤 것을 사용해도 보통의 경우 무방하니, 이해가 안되면 그냥 넘어가도록 하자.)    

    ```
    puts 'hello world'      # hello world 라는 문자열을 출력한다.
    
    a='world'               # world 라는 문자열을 a라는 변수에 담는다.
    puts "hello, #{a}"      # hello world 라는 문자열을 출력한다.
    ```
    
8. 배열   
    변수들의 집합이라고 생각하면 편하다.  
    여러 개의 변수를 묶어 놓은 것이라고 생각하자.
    대괄호[] 를 사용하여 선언한다.  
    index를 통해 관리(?)할 수 있다.  
    index는 배열의 원소(묶여진 변수 하나하나를 배열의 원소라고 한다.)에 붙여진 일련번호이다.   
    다음은 배열을 선언하는 몇 가지 방법들이다.
    
    ```
    animals= Array.new      # animals라는 배열을 새롭게 생성한다.(값은 아직 담기지 않았다.)
    animals[0]='lions'      # animals라는 배열에 각각 'lions', 'tigers', 'bears'라는 값을 저장한다.
    animals[1]='tigers'     # 이때, 0, 1, 2 를 배열에 index라 한다.
    animals[2]='bears'      # index는 항상 0부터 시작한다.
    
    animals=['lions','tigers','bears']      # 위의 네 줄의 코드를 다음과 같이 한 번에 쓸 수 있다.(선언과 동시에 값을 할당)
    ```

9. 해쉬  
    배열과 유사하나 배열과 달리 index값을 사용자가 정의할 수 있다.  
    해쉬에서는 index 대신 key라고 부른다.  
    즉, key-value값의 대응관계가 형성된다.(key-value가 한 쌍으로 이루어져 있다.)  
    배열은 같은 자료형을 가진 데이터만 저장할 수 있지만, 해쉬는 여러 자료형을 가진 데이터들을 같이 저장할 수 있다.  
    ```
    numbers = Hash.new                              # 배열과 마찬가지로 새롭게 생성 가능
    numbers[1]="one"                                # key가 숫자일 경우, 배열과 유사하게 사용
    numbers[2]="two"                                # 단, key는 index처럼 0부터 자동으로 생성되지 않는다(사용자가 설정)

    numbers={1=>"one", 2=>"two"}                    # 위의 세 줄을 한번에 쓴 것. numbers라는 이름의 해쉬, 1은 key, "one"은 value / 2는 key, "two"는 value
    
    hashhh={:array=>[1, 2, 3], :string=>"hello"}    # key가 숫자가 아닐 경우 : 를 사용한다. array는 key, [1,2,3]는 value / string은 key, "hello"는 value
    puts hashhh[:array]                             # 1, 2, 3이 차례로 출력된다.
    puts hashhh[:string]                            # hello가 출력된다.
    ```

10. 연산자
    - [연산자 관련 포스트](http://seungdols.tistory.com/324?category=575817)
    
11. 조건문  
    if, elsif, else, unless 등이 있다.  
    말 그대로 조건을 걸어주어야 할 때 사용.  
    if, elsif, else는 한 블록 안에 사용가능, if를 두 번 사용하거나 if와 unless를 혼용할 때는 다른 블록에서 사용해야 한다.  
    블록 구분은 end로 한다.
    ```
    x=4     # 변수 선언     
    if x==5
        puts "x=5"
    elsif x==6
        puts "x=6"
    end
    
    unless x==4         # unless는 if 와 반대되는 개념이라서 end로 끊어줘야 사용이 가능하다.
        puts "x!=4"
    else
        puts "x!=5 and x!=6"
    end
    ```
    
12. 반복문
    while, for문  
    어떠한 명령을 반복해야 할 때 사용한다.  
    ```
    i=0
    while i<5
       puts i 
       i=i+1
    end
    # 0, 1, 2, 3, 4 출력
    ```
    ```
    for i in 0...5      # 0이상 5미만
        puts i
    end
    ```
        

### 예제
1. a라는 배열에 1, 3, 4, 5, 2를 순서대로 저장하고, a라는 배열에서 3개를 랜덤으로 추출하고 오름차순으로 정렬하여라.  
    ```
    a=[1, 3, 4, 5, 2]
    a.sample(3).sort
    ```
    
2. 구구단 만들기  
    ```
    def gugudan(i)
        for j in 1..9
            puts "#{i}X#{j}=#{i*j}"
        end
    end
    ```

3. 