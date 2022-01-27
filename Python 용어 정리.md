`len(a)` : 문자열 길이

print(x, `end=""`) : 문자열 결과값을 나란히 표시

###  <리스트 관련 함수들>
>요소 인덱싱,연산,수정 가능 
>
>a = [요소1, 요소2, 요소3...]

`del a[리스트 요소값]` : 요소삭제

`a.append()` :요소추가

`a.short()` : 리스트 정렬 - 숫자 순서, 알파벳 순서 정렬

`a.reverse()` : 리스트 뒤집기 - 숫자 역순, 알파벳 역순 정렬

`a.index(요소)` : 위치 반환 - 요소값의 인데스

`a.insert(요소)` : 리스트에 요소 삽입

`a.remove(요쇼)` : 리스트에 요소 삭제

`a.pop()` : 리스트내 뒤에 요소부터 끄집어낸다. 

`a.pop(요소)` : 리스트 요소 끄집어낸다.

`a.count(요소)` : 리스트에 포함된 요소의 개수 세기

`a.extend(요소)` : 리스트 확장 / 리스트 + 리스트

### **<딕셔너리 관련 함수들>**

> a = {'key1':''values1', 'key2:'values2''key3:'values3'...}

`a.keys()` : dict_keys([리스트]) 형태로 만들기

`a.values()` : dict_values([리스트]) 형태로 만들기

```python
for k in a.keys():
    print(k)
```

>  key 요소 for문으로 뽑기

`list(a.keys())` : 리스트 형태로 만들기

`a.items()` : dict_items([('key1:'values1)', 'key2:'values2)']) 형태로 만들기

`a.clear()` : key: value 쌍 모두 지우기

`a.get(key1)` : key로 value 얻기

`'key요소' in a` : 해당 key가 딕셔너리 안에 있는지 조사하기 / 결과값 True or Flase

### **<집합 관련 함수들>**

> 교집합, 합집합, 차집합 / 추가,제거 가능
>
> s1 = set([요소1,요소2,요소3...])

`s1.add(요소)` : 요소값 추가

`s1.update(요소값들)` : 요소 값 여러개 추가하기

`s1.remove(요소)` : 특정 요소 제거하기

---

### <흐름제어>

`input` : a=input("값을 입력하세요:") / b=int(input("정수를 입력하세요:"))

​               c=float(input("실수를 입력하세요:")) 형태 /a,b,c 입력값을 이용

1.`if문` : **and, or, not** / x **in** s, x **not in** s

````python
pocket = ['paper','cellphone']
money = 2000
card = True
if 'cellphone' in pocket:
    print("택시를 타고 가라")
elif money >=3000 or card:
    print("택시를 타고 가라")
else:
    print("걸어가라")
>택시를 타고가라
````

2.`for문`

```python
for 변수 in 리스트(튜플,문자열):
    실행 문장 1
    실행 문장 2
```

```python
a = [33,44,88,99]
for x in a:
    if x =< 60:"
        continue
    else:
        print("%d점으로 합격입니다." % x)
>88점으로 합격입니다.
 99점으로 합격입니다.    
```

`continue` : for문의 조건에 해당되면 그냥 진행한다.

```python
sum = 0 # 변수를 설정한다. 조건문의 변수가 없을경우 오류가 발생한다.
for x in range(10): # 0부터 9까지 x값
	sum += x # 변수 x값을 계속 더해준다.  
	print(sum)
```

```python
a = [4,5,6,3]
for x in range(len(a)): #len(a)의 인덱스길이 = 4, range(4)
    if a[x] <=5: #만약 a[x]값이 5보다 같거나 작으면
        continue #계속 for문을 진행한다
    print("%d 값으로 psss"% (a[x]))
> 6 값으로 pass
```

```python
a = [1,2,3,4]
result = [] #None 리스트명 result
for num in a:            # result = [num*3 for num in a]
    result.append(num*3) # 위에와 같은 내용
    #append 요소추가함수, num x 3의 요소값 추가
result2 = [num*3 for num in a if num%2==0]
print(result)
print(result2)
> [3,6,9,12]
> [6,12]
```

3.`while문`

```python
while <조건문>:   #조건문이 참인 동안에 while문 아래의 문장을 반복수행한다.
    <수행할 문장1> #조건문이 거짓일 경우 while문을 빠져나간다.
    <수행할 문장2>...
```

``` python
a = 0   #변수를 설정한다.
while a < 10:  #a가 10보다 잡을경우 계속 실행된다. 0,1,2,3,4,5,6,7,8,9
    a = a + 1   #변수의 결과값 변수 a에 1을 더해준다.
    if a % 2 == 0: continue #만약 a가 짝수라면 print(a)로 이동하지 
                            #않고 while문의 맨처음 조건문으로 돌아간다.
    print(a)    # a값은 홀수값만 나오게 된다.
>1 3 5 7 9 (아래로)
```

`break` : break문이 호출되면 while문을 빠져나올 수 있다.

```python
while True:
    수행할 문장1
    수행할 문장2
```

```python
import random
for x in range(5):
    print(random.random())   #0~1미만의 실수를 난수로 생성
    print(random.uniform(1,100)) #특정 범위의 실수를 난수로 생성
    print(random.randint(1,100)) #특정 범위의 정수를 난수로 생성
    print(random.randrange(1,100,10)) #특정 범위의 정수를 step을 더해서 생성
```

---

### <함수>

```python
def add(a,b):  #변수 a,b를 가진 함수 add를 생성한다.
    result = a + b # add라는 함수의 사용법
    return result  #return 결과값을 받을 변수(오직 return명령어로만 가능), 함수는 return문을 만나는 순간 결괏값을 돌려준 다음 함수를 빠져나간다. 함수의 반환 값은 오로지 return문에 의해서만 생성
a = add(3,4) #결과값을 받을 변수 = 함수이름(입력인수1,입력인수2)
print(a)
>7
```

```python
def add_mul(choice, *args): #함수 add_mul의 매개변수 choice,args/*args:임의의 매개변수 args앞에 *를 붙이면 입력값을 전부 모아서 튜플로 만들어준다.
    if choice == "add": #매개변수 choice 가 add라면
        result = 0 # 결과값 변수를 0으로 설정한다
        for i in args: #변수 args중의 하나의 변수 i
            result += i #결과값의 함수 내용
    elif choice == "mul": #매개변수 choice가 mul라면
        result = 1 #결과값 변수를 1로 설정한다. 함수내용이 곱하기라서
        for i in args:
            result *= i
        return result # 결과값을 받을 변수를 설정한다.
result = add_mul("add",1,2,3,4,5)
print(result)
>15
result1 = add_mul("mul",1,2,3,4,5)
print(result1)
>120
```

`def print_kwargs(**kwargs)` : `**kwargs` 처럼 매개변수 이름앞에 `**`을 붙이면 매개변수 kwargs는 딕셔너리 형태로 되고 모든 `key=valus` 형태의 결과값이 딕셔너리에 저장된다. ex) print_kwargs(age=19, name='john') >>{'age':19, 'name':'john'}  

> `2개의 입력 인수를 받아 연산해주는 함수 경우` : 함수의 결괏값은 언제나 하나이므로 튜플값 하나인 (결과값1,결과값2)로 돌려준다.

```python
def say_myself(name,old, man=True): #매개변수3개, man=True로 초기값이 설정된 매개변수, 초기화 시키고 싶은 매개변수는 항상 뒤쪽에 놓는다.
    print("나의 이름은 %d 입니다."% name)
    print("나이는 %d살입니다."% old)
    if man:   #man=True 로 설정된 변수값에 참이면 if 아니면 else
        print("남자입니다.")
    else:
        print("여자입니다.")
```

> 함수 안에서 새로 만든 매개 변수는 함수 안에서만 사용하는 "함수만의 변수"
>
> 즉 함수 안에서 사용하는 매개변수는 함수 밖에 변수 이름과는 전혀 상관없다.

``` python
a = 1  #외부의 매개변수 a와 함수내부의 매개변수 a는 다른 변수이다.
def vartest(a):
    a = a + 1
    return a  # return을 사용하여 함수 밖으로 빠져나간다.
a = vartest(a) # 외부 매개변수 a가 함수 결과값 vertest(a)로 치환된다.
print(a)
```

```python
a = 1  #외부의 매개변수 a와 함수내부의 매개변수 a는 다른 변수이다.
def vartest():
    global a  # global :함수 밖의 a 변수를 함수 안에서 사용하는 명령어
    a = a + 1
```

`return` : return 결과값을 받을 변수(오직 return명령어로만 가능), 함수는 return문을 만나는 순간 결괏값을 돌려준 다음 함수를 빠져나간다. 함수의 반환 값은 오로지 return문에 의해서만 생성. 여러 함수가 있는경우 필수 적용

`global` : 함수 안에서 함수 밖에 변수를 직접 사용하겠다는 명령어. **비추천**

왜냐하면 함수는 독립적으로 존재하는 것이 좋기 때문이다.

`lambda` : lambda는 함수를 생성할 때 사용하는 예약어로 def와 동일한 역할을 한다. 보통 함수를 한줄로 간결하게 만들 때 사용한다. 우리말로는 "람다"라고 읽고 def를 사용해야 할 정도로 복잡하지 않거나 def를 사용할 수 없는 곳에 주로 쓰인다.

```python
add  = lambda a,b : a+b  #lambda로 만든 함수는 return명령어가 없어도 결과값을 돌려준다.
result = add(3,4)
print(result)
>7
```

### <파일 읽고 쓰기>

`f=open("파일경로",'w')` : 쓰기모드

`f.close()` : 파일 닫기

`f.readline()` : 파일의 가장 첫 줄을 화면의 출력

### <클래스 관련 함수>

```python
class FourCal:
	def setdata(self,first,second): #매개변수 selfsms
        self.first = first
        self.second = second
a = FourCal()
a.setdata(4,2)
```

```python
class Foural:
    def setdata(self, first, second):
        self.first = first
        self.second = second
    def add(self):
        result = self.first + self.second
        return result
    def mul(self):
        result = self.first * self.second
        return result
    def sub(self):
        result = self.first - self.second
        return result
    def div(self):
        result = self.first / self.second
        return result
a = FourCal()
b = FourCal()
a.setdata(4,2)
b.setdata(3,8)
print(a.add()) > 6  print(b.add()) > 11
print(a.mul()) > 8  print(b.mul()) > 24
print(a.sub()) > 2  print(b.sub()) > -5
print(a.div()) > 2  print(b.div()) > 0.375
```

### <예외처리>

`try - except문`

