# #include<study_cpp.h>


---

## 목차
### c++ 학습
- [입출력](#입출력)
  - [출력 std::cout](#입력-std::cout)
  - [입력 std::cin](#출력-std::cin)
  - [문자열 입출력](#문자열-입출력)
- [함수](#함수)
  - [함수 오버로딩](#함수-오버로딩)
  - [매개변수 디폴트 값](#매개변수-디폴트-값)
  - [인라인 함수](#인라인-함수)
 
    
### 예제
- [에제 1]()


### Q&A
- [배열을 인수&반환값으로 사용하는 법]()






---
# C++ 학습
- ## 입출력
- ### 출력 std::cout
`std::cout << '출력대상';` 출력하기
>
`std::endl` `\n` 개행
```cpp
#include<iostream>

int main(void) {
	std::cout << "Hello World" << std::endl;
	std::cout << "Hello World\n";
	std::cout << "가나다" << std::endl;
	return 0;
}
```
- ### 입력 std::cin
`std::cin >> '변수';` 입력하기 
```cpp
#include<iostream>

int main(void) {  //정수형 입출력
	int val1;
	std::cout << "첫 번째 숫자입력: ";
	std::cin >> val1;

	int val2;  //cpp에서는 지역변수 선언의 위치가 자유로움
	std::cout << "두 번째 숫자입력: ";
	std::cin >> val2;
	int result = val1 + val2;
	std::cout << "덧셈결과: " << result << std::endl;
	return 0;
}
```
- ### 문자열 입출력
`char 변수[크기];` 배열 문자열 선언
```cpp
#include<iostream>

int main(void) {  //문자열 입출력
	char str[100];
	std::cin >> str;
	std::cout << str << std::endl;
	return 0;
}
```
---
- ## 함수
- ### 함수 오버로딩
- ### 매개변수 디폴트 값
- ### 인라인 함수

