# 문자와 문자열 관련 함수  

## 스트림과 데이터의 이동  
데이터의 입력과 출력은 프로그램의 흐름. 프로그램 안으로 데이터가 흘러 들어오는 것이 입력, 프로그램 밖으로 데이터가 흘러 나가는 것이 출력.  

`printf`함수와 `scanf`함수로 데이터를 입출력할 수 있는 이유는 스트림(stream)이라는 다리 역할이 있기 때문이다. 스트림은 운영체제에서 제공하는 소프트웨어적인(소프트웨어로 구현되어 있는) 가상의 다리이다. 운영체제는 외부장치와 프로그램과의 데이터 송수신의 도구가 되는 스트림을 제공하고 있다.  

### 스트림의 생성과 소멸  

콘솔(일반적으로 키보드와 모니터) 입출력을 위한 '입력 스트림'과 '출력 스트림'은 프로그램이 실행되면 자동으로 생성되고, 프로그램이 종료되면 자동으로 소멸되는 스트림이다. 이 둘은 기본적으로 제공되는 '표준 스트림(standard stream)'이다. 그리고 표준 스트림에는 '에러 스트림'도 존재한다.  
- stdin: 표준 입력 스트림, 키보드 대상으로 입력  
- stdout: 표준 출력 스트림, 모니터 대상으로 출력  
- stderr: 표준 에러 스트림, 모니터 대상으로 출력  

> 스트림(stream)  
 스트림은 '한 방향으로 흐르는 데이터의 흐름'을 뜻한다. 즉 스트림이란 단어에는 단 방향으로만 데이터 전송이 이뤄진다는 뜻이 담겨있다. 실제로 입출력 스트림도 입력 스트림과 출력 스트림이 구분되어서 한 방향으로만 데이터의 흐름을 유지하고 있다.  


## 문자 단위 입출력 함수  

### 문자 출력 함수: putchar, fputc  
모니터로 하나의 문자를 출력할 때 일반적으로 사용하는 두 함수는 다음과 같다.  

```c
#include <stdio.h>
int putchar(int c);
int fputc(int c, FILE * stream);
```
→ 함수 호출 성공 시 쓰여진 문자 정보가, 실패 시 EOF 반환  

- `putchar` 함수는 인자로 전달된 문자정보를 stdout으로 표현되는 표준 출력 스트림으로 전송하는 함수. 인자로 전달된 문자를 모니터로 출력하는 함수라 할 수 있다.  
- `fputc`함수는 문자를 전송할 스트림을 지정할 수 있다. 즉 stdout뿐만 아니라 파일을 대상으로도 전송이 가능하다. `fputc`함수의 두 번째 매개변수 stream은 문자를 출력할 스트림의 지정에 사용된다. 이 인자에 표준 출력 스트림을 의미하는 stdout을 전달하면 `putchar`함수와 동일한 함수가 된다.  

> fputc함수의 두 번째 인자  
 `fputc`함수의 두 번째 인자로 파일의 스트림 정보를 전달하면, 해당 파일로 문자가 전달된다(해당 파일에 문자가 저장된다).  

### 문자 입력 함수: getchar, fgetc  
키보드로부터 하나의 문자를 입력 받을 때 일반적으로 사용하는 두 함수는 다음과 같다.  
```c
#include <stdio.h>
int getchar(void);
int fgetc(FILE * stream);
```
→ 파일의 끝에 도달하거나 함수호출 실패 시 EOF 반환  

- `getchar`: stdin으로 표현되는 표준 입력 스트림으로부터 하나의 문자를 입력 받아서 반환, 키보드로부터 하나의 문자를 입력 받는 함수.  
- `fgetc`: 하나의 문자를 입력 받는다. 입력 받을 스트림을 지정할 수 있음. `putchar`, `fputc` 함수의 관계와 동일  

### 예제  

```c
#include <stdio.h>

int main(void)
{
    int ch1, ch2;

    ch1 = getchar();    // 문자 입력
    ch2 = fgetc(stdin); // 엔터 키 입력

    putchar(ch1);       // 문자 출력
    fputc(ch2, stdout); // 엔터 키 출력
    return 0;
}
```
```
p
p
```
두 번째로 입력한 문자가 '엔터 키'이기 때문에 문자가 하나씩만 입력되고 출력된 것처럼 보인다.  

### 문자 입출력에서의 EOF  

EOP는 End Of File의 약자로, 파일의 끝을 표현하기 위해서 정의해 놓은 함수이다. 파일을 대상으로 `fgetc`함수가 호출되고 그 결과로 EOF가 반환되면, 이는 '파일의 끝에 도달해서 더 이상 읽을 내용이 없다.'는 뜻이 된다. 키보드를 대상으로 하는 `fgetc`함수와 `getchar`함수는 다음 두 가지 경우 중 하나가 만족되었을 때 EOF를 반환한다.  
- 함수 호출의 실패  
- Windows에서 <kbd>CTRL</kbd>+<kbd>Z</kbd> 키, Linux에서 <kbd>CTRL</kbd>+<kbd>D</kbd>키가 입력되는 경우   
키보드의 입력에 '반환의 끝'이라는 것이 없기 때문에 EOF의 반환시기를 키 입력으로 별도로 약속해 놓은 것이다.  

```c
#include <stdio.h>

int main(void)
{
    int ch;

    while(1)
    {
        ch = getchar();
        if(ch == EOF)
            break;
        putchar(ch);
    }
    return 0;
}
```
```
Hi~
Hi~
I like C lang.
I like C lang.
^D
```
`getchar`함수가 호출된다고 해서 하나의 문자만 입력하지 않아도 된다. 문자가 아닌 공백을 포함하는 문장을 입력할 수 있다. 문장이 입력되면 문장을 구성하는 문자의 수만큼 `getchar`함수가 호출되면서 모든 문자를 읽어 들인다.  

### 반환형이 int이고, int형 변수에 문자를 담는 이유는?  

```c
int getchar(void)
int fgetc(FILE * stream);
```
반환되는 것은 1바이트 크기의 문자인데, 반환형이 int이다. **EOF는 -1로 정의된 상수**인데, 반환형이 char형 이라면, 그리고 char를 unsigned char로 처리하는 컴파일러에 의해 컴파일되어버리면 엉뚱한 양의 정수로 형 변환이 되어버리고 만다. 그래서 어떠한 상황에서도 -1을 인식할 수 있는 int형으로 반환형을 정의해 놓은 것이다.   

> 문자 단위 입출력 함수의 존재 이유  
 `printf`와 `scanf`함수는 본래 서식지정을 통해 새로운 입출력의 형태를 구성하는 함수라서 화려한 기능을 제공하지만 그에 대가로 메모리 공간도 크고, 해야 할 연산의 양도 많아서 상대적으로 속도가 느리다. 뿐만 아니라 별도의 서식지정을 해야 하니 문장을 구성하는 것도 번거로운 편이다. 따라서 단순히 문자 하나를 입출력 하는 것이 목적이라면 `printf`, `scanf`의 사용 보다 문자 단위 입출력 함수를 사용하는 것이 낫다.  
