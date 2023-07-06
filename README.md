# #include<study.c>

>해당 내용들은 c언어를 공부하며 정리&필요한 내용들을 정리해놓은 곳입니다.
>
>참고도서:[윤성우의 열혈 C 프로그래밍](http://www.orentec.co.kr/booklist/C_BASIC_2/book_sub1_list.php),  [스튜어트 미분적분학-9e](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=309558529&start=slayer), [초보자를 위한 C언어300제 2판](http://www.infopub.co.kr/new/include/detail.asp?sku=06000237)
>
>*주의 !:* c언어 학습 내용을 정리해둔 곳으로 부정확한 내용이 있을 수 있습니다.
>

---

## 목차

### c언어 학습
- [문자형](#문자형)
  - [문자형 변수](#문자형-변수)
  - [문자열형 변수](#문자열형-변수)
  - [문자형 상수](#문자형-상수)
  - [문자열형 상수](#문자열형-상수)
- [연산자](#연산자)
  - [논리 연산자](#논리-연산자)
  - [조건(삼항) 연산자](#조건삼항-연산자)
  - [쉼표 연산자](#쉼표-연산자)
  - [캐스트 연산자(형 변환)](#캐스트-연산자-형-변환)
- [함수](#함수)
- [포인터](#포인터)


 ### 미분적분학 (내용 추가 예정)
- [1. 함수와 극한]()
- [2. 도함수]()
- [3. 미분법의 응용]()
- [4. 적분]()
- [5. 적분의 응용]()
- [6. 역함수: 지수함수, 로그함수, 역삼각함수]()
- [7. 적분방법]()
- [8. 적분법의 다양한 응용]()
- [9. 매개변수방정식과 극좌표]()
- [10. 수열과 금수 그리고 거듭제곱급수]()
- [11. 벡터와 공간기하학]()
- [12. 벡터함수]()
- [13. 편도함수]()
- [14. 다중적분]()
- [15. 벡터해석]()

  
### 예제 풀이
- [에제 1]()


### Q&A
- [배열을 인수&반환값으로 사용하는 법]()






---
## c언어 학습!
- ## 문자형
`' '` 싱글 퀘테이션: 문자를 나타낼 때
>
`" "` 더블 퀘테이션: 문자열을 나타낼 때

- ### 문자형 변수
```c
#include<stdio.h>

int main(void){
    char ch=200;
    unsigned char c=200;
    char d='a';
    
    printf("문자형 변수 ch의 값은 %d\n",ch);   // -56
    printf("문자형 변수 c의 값은 %d\n",c);     // 200
    printf("문자형 변수 ch의 값은 %d\n",d);    // 97
}
```
 `char 변수명` -128 ~ +127 
 >
 `unsigned char 변수명` 0 ~ +255


- ### 문자열형 변수
```c
#include<stdio.h>

int main(void){
    char str[]="안녕하세요!";
    char *j= "Hello, World!";

    printf("문자열형 변수 str의 값은 %s\n",str);  //안녕하세요!
    printf("문자열형 변수 j의 값은 %s\n",j);      //Hello, World!
}
```
`char 배열명[]` 배열로 문자열 변수 사용
>
`char *j` 포인터로 문자열 상수 사용


- ### 문자형 상수
```c
#include<stdio.h>

#define HUNDRED 100

const char n=10;

int main(void){
    //HUNDRED =200; // 에러 발생
    //n=200;        // 에러 발생
    printf("문자형 상수 HUNDRED의 값은 %d\n",HUNDRED);  // 100
    printf("문자형 상수 n의 값은 %d\n",n);              // 10
}
```
`#define 상수명 값` 상수명은 대문자로 권장, 세미콜론(;)이 붙지않음(선언 후 수정 불가능)
>
`const 형지정 = 값` const char n에서 n은 문자형 상수(선언 후 수정 불가능)


- ### 문자열형 상수
```c
#include<stdio.h>

#define TREE   "나무"
#define BOOK    "C study"

const char* PLAYER="32분 접속";

int main(void){
    printf("문자열형 상수 TREE의 값은 %s\n",TREE);     // 나무
    printf("문자열형 상수 BOOK의 값은 %s\n",BOOK);     // C study
    printf("문자열형 상수 PLAYER의 값은 %s\n",PLAYER); // 32분 접속
}
```
`#define char 문자열` define 문자열형 상수
>
`const char* = "문자열"` 포인터 문자열형 상수






---
- ## 논리 연산자
- ### 논리 연산자
```c
#include<stdio.h>

int main(void){
    int x = 5;
    int y = 3;

    if(x > 0 && x < 10){
        printf("둘다 참\n");
    }
    if(x < 0 || y == 3){
        printf("둘중 하나 이상이 참\n");
    }
    if(!(x<y)){
        printf("수식이 거짓\n");
    }
}
```
`&&` 두 수식이 모두 참
>
`||` 두 수식중 하나 이상이 참
>
`! ` 수식이 거짓일때 참


- ### 조건(삼항) 연산자
```c
#include<stdio.h>

int main(void){
    int x = 5;
    int y = 3;

    int n = x > y ? x : y;
    printf("%d",n);  // 5
}
```
`수식 ? 참일 때 반환값 : 거짓일 때 반환값` if문 대체로 사용 가능 


- ### 쉼표 연산자
```c
#include<stdio.h>

int main(void){
    int j;
    for(int i=0, j=10; i<j; i++,j--){
        printf("*");   // *****
    }
}
```
`,` for문 내부에서도 사용 가능


- ### 캐스트 연산자(형 변환)
```c
#include<stdio.h>

int main(void){
    int x = 5, y = 2;
    printf("%d\n",x/y);            //2
    printf("%.2f\n",(double)x/y);  //2.50
}
```
`(변환할 형)변수`









- ## 함수
  - [ ] 1
  내용 추가 예정
  - [ ] 2
   내용 추가 예정

- ## 포인터
  - [ ] 1
   내용 추가 예정
  - [ ] 2
   내용 추가 예정

---
## 미분적분학

