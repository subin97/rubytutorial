# Ruby (2)

### 개념/예제


1. 클래스와 인스턴스
    ```
    class Person                        # Person class 지정
        def initialize(name, age, sex)  # 생성자함수 - 인스턴스가 생성될 때마다 실행되는 함수
            puts name, age, sex
        end
    end
    
    p = Person.new('도도', 20, '남자')  # p라는 인스턴스 생성
    ```
    
2. 변수의 범위  
    ```
    class Byeonsoo
    @@class="클래스 변수"           # 클래스 변수 선언
    $global = "전역변수"            # 전역 변수 선언
        
        def function1
           local="지역변수"             # 지역 변수 선언
           @instance="인스턴스 변수"    # 인스턴스 변수 선언
           puts local
           puts @instance
           puts @@class
           puts $global
        end
        def function2
            puts local       # 오류
            puts @instance   # "인스턴스 변수"
            puts @@class     # "클래스 변수"
            puts $global     # "전역 변수"
        end
    end
    a=Byeonsoo.new
    
    a.function2
    
    # puts $global
    ```

3. 상속  
    ```
    class Person                                             # Person class 지정
        def initialize(name)
            @name = name
        end
        def drink
            puts "#{@name}이 물을 먹고 있습니다."
        end
        def run
            puts "#{@name}이 달리고 있습니다."
        end
    end
        
    class BasketBallMan < Person
        def shot
            puts "#{@name}이 슛을 쐈습니다!"
        end
        def run
            puts "#{@name}이 드리블을 하면서 달리고 있습니다."  # 상속거부
            super       # 상속받기 + 기능추가하기 / super적어준 위치에 상위클래스의 메소드 호출
        end
    end
        
    jordan=BasketBallMan.new('조던')
    jordan.run
    ```

4. Private & Public
    ```
    class Person                           # Person class 지정
        def initialize(name, age)
            @name = name
            @age = age
        end
        
        public
        def run
            puts "#{@age}살의 #{@name}가 달립니다. "
            puts your_password  # 오브젝트 안에서 접근 가능 
        end
        def check_passworld(input)
            if your_password==input
                puts "비밀번호가 맞습니다"
            else
                puts "비밀번호를 다시 입력해 주세요"
            end
        end
        private
        def your_password
            @password="123456789"
        end
    end
    
    p=Person.new('도도',20)
    p.run
    # puts p.your_password
    p.check_passworld("123456789")
    ```

5. Live Coding - 로또 추첨하기  
    1) 필요한 것들  
    - 당첨숫자 6개를 담을 배열 lottoNum
    - 내가 고른 숫자 6개를 담을 배열 myNum
    - 일치하는 숫자를 저장할 배열 matchNum
    - matchNum의 개수를 저장할 변수 count
    - 보너스숫자 bonusNum  
     
    2) 알고리즘  
    - lottoNum에 숫자 6개를 지정
    - myNum에 숫자 6개를 랜덤으로 추출하여 저장
    - lottoNum과 myNum을 비교 -> 일치하는 숫자의 개수를 센다
    - 조건문을 사용하여 등수를 출력한다.
    
    ```
    lottoNum = [2,6,11,33,41,45]
    bonusNum = 3
    matchNum = 0
    myNum=(1..45).to_a.sample(6).sort
    
    matchNum = lottoNum & myNum
    
    if(matchNum.count == 6)
        result = '1등'
    elsif((matchNum.count == 5) && myNum.include?(bonusNum))
        result = '2등'
    elsif matchNum.count == 5 
        result = '3등'
    elsif matchNum.count == 4
        result = '4등'
    elsif matchNum.count == 3
        result =  '5등'
    else
        result = '꽝'
    end
    
    puts "로또 추첨 결과, 당신은 {#result}입니다."
    ```