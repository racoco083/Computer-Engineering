## 소스 파일에서 실행 파일이 되는 과정

![image](https://user-images.githubusercontent.com/21019088/56419919-f259b700-62d6-11e9-92e4-e509e833228a.png)

처음의 소스 파일은 우리가 작성하는 ".c"파일이다. 실행파일을 만들기 위해 가장 먼저 실행 되는 것은 전처리기(Preprocessor)이다. 전처리기를 총해 ".i"파일이 생성되고, 컴파일러에서 하드웨어 종속적인 어셈블리코드(".s")를 생성하게 된다. 이후 어셈블러(Assembler)에 의하여 어셈블리어가 오브젝트 파일을 생성하고, 이 오브젝트 파일들이 링킹(Lingking)과 재배치(Relocation)과정을 거쳐 실행 파일이 생성된다.

1. 소스코드( .c ) - 사용자에 의해 c언어로 작성된 소스 코드로 확장자가 c이다.

2. 전처리 (Preprocessing)

3. 전처리 후 소스( .i ) - 전처리가 끝이 나면 i 확장자를 가진 파일이 생성된다. 

4. C 컴파일 (Compile) - ".i"파일을 ".s"파일로 만든다. 이 때 Symbol Table을 만든다.

* Symbol Table 예제

T_BIT라는 변수의 타입(자료형)은 a이고 주소는 00000020인 것을 알 수 있다.

![image](https://user-images.githubusercontent.com/21019088/56420974-48c8f480-62db-11e9-868d-8a8881406712.png)


5. 어셈블리소스 ( .s ) - 기계어와 가장 유사한 상태인 어셈블리어로 변환 된 s 확장자를 가진 
파일이 생성된다.

* 어셈블리 소스 예제) mov ax @data, add ds ax

6. 어셈블리 (Assembly) 컴파일

7. 오브젝트 파일( .o ) - 2진수로 이루어진 기계어로 된 파일이 생성된다. 확장자는 o이다. 여러 변수들의 상대 주소 정보 등등...이 저장되어 있는 Symbol Table이 있다.

8. 링크 (Link) - 모든 오브젝트 파일들을 하나의 오브젝트 파일로 합친다. 컴퓨터가 발전하고 작성하는 소스 코드의 양이 늘어남에 따라, 한 파일에 모든 소스 코드를 작성하는 방식이 불편하다는 것을 깨닫게 되었다. 사람들은 소스 코드를 다른 파일에 분리하는 방법을 생각해냈다. 원래 하나였던 파일을 분리했으므로, 프로그램을 완성하려면 분리했던 파일은 모두 연결해야 한다. 이렇듯 분리된 파일을 모아 하나의 실행 가능한 파일을 만들면 이를 두고 파일들을 링크(link)했다고 하고, 이때 사용되는 프로그램을 링커(linker)라고 한다.

9. 실행파일 ( .exe ) - 링크에 의해 실행 할 수 있는 파일을 생성한다.

10. 로더 (Loader) - exe file을 읽는다. 메인 메모리에 오브젝트 파일에 있는 내용들을 올려 프로그램을 수행시킬 수 있도록 만든다. os의 한 부분이다. 

## Reference
http://yimoyimo.tk/Linker-and-Loader/