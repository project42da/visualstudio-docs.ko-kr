---
title: "모범 사례 및 예제(SAL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 666276fb-99c2-4dc9-8bac-d74861c203ea
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 모범 사례 및 예제(SAL)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

일부의 소스 코드 주석 언어 \(SAL\) 중 대부분을 몇 가지 일반적인 문제를 방지 합니다.  
  
## \_In\_  
 요소에 쓰는 함수를  `_Inout_`  대신  `_In_` 사용합니다.  SAL 이전 매크로에서 자동 변환 하는 경우에서에 매우 유용 합니다.  매크로 설명으로 많은 프로그래머 SAL를 전에 이름이 매크로  `IN` ,  `OUT` ,  `IN_OUT` , 또는 이러한 이름의 변형합니다.  SAL에 이러한 매크로 변환 하는 것이 좋습니다 있지만 또한에 명기 변환할 경우 원래 프로토타입 작성 하 고 기존 매크로 코드가 무엇 반영 되지 않을 수 없습니다 코드 변경 했을 수 있으므로 주의 해야 합니다.  특히  `OPTIONAL`  자주 적용 되므로 하지 올바르게 매크로 주석\-예를 들어, 쉼표의 잘못 된 쪽에서 주의하세요.  
  
```cpp  
  
// Incorrect  
void Func1(_In_ int *p1)  
{  
    if (p1 == NULL)   
        return;  
  
    *p1 = 1;  
}  
  
// Correct  
void Func2(_Inout_ PCHAR p1)  
{  
    if (p1 == NULL)   
        return;  
  
    *p1 = 1;  
}  
  
```  
  
## \_opt\_  
 Null 포인터를 전달 하는 호출자 허용 되지 않는 경우  `_In_`  또는  `_Out_`  대신  `_In_opt_`  또는  `_Out_opt_` 를 사용하세요.  이 매개 변수를 확인 하 고 안 면이 NULL 이면 오류를 반환 하는 함수에도 적용 됩니다.  예기치 못한 NULL 매개 변수를 확인 하 고 정상적으로 반환 하는 함수를 가진 방어 좋은 코딩 습관 이지만 의미 하지 않는 선택적 형식 매개 변수가 주석 수 있는지 \(\_*Xxx*\_opt\_\) 확인하세요.  
  
```cpp  
  
// Incorrect  
void Func1(_Out_opt_ int *p1)  
{  
    *p = 1;  
}  
  
// Correct  
void Func2(_Out_ int *p1)  
{  
    *p = 1;  
}  
  
```  
  
## \_Pre\_defensive\_ 및 \_Post\_defensive\_  
 함수에는 신뢰 경계가 나타나면 있는  `_Pre_defensive_`  주석을 사용하는 것이 좋습니다.  "방어" 한정자를 나타내는 호출 시 특정 주석 수정 하 고 인터페이스를 엄격 하 게 검사 해야 하지만 구현 본문에서 그는 가정 잘못 된 매개 변수를 전달할 수 있습니다.  이 경우  `_In_ _Pre_defensive_`  는 있지만 호출자는 오류 NULL을 전달 하려고 하면, 함수 본문 분석 합니다 매개 변수는 NULL 일 수를 첫 번째 NULL을 확인 하지 않고 포인터를 참조 취소 하려고 표시 됩니다 나타내는 신뢰 경계에 권장 됩니다.   `_Post_defensive_`  주석 콜백이 있는 신뢰할 수 있는 타사 호출자로 간주 됩니다 및 신뢰할 수 없는 코드는 호출된 코드에서 사용 하기 위해 사용할 수도 있습니다.  
  
## \_Out\_writes\_  
 다음 예제는 `_Out_writes_`의 보통의 잘못된 사용을 보여 줍니다.  
  
```cpp  
  
// Incorrect  
void Func1(_Out_writes_(size) CHAR *pb,   
    DWORD size  
);  
  
```  
  
 주석  `_Out_writes_`  버퍼를 사용 해야 한다는 것을 나타냅니다.   `cb`  종료 시 초기화 하는 첫 번째 바이트를 사용 하 여 할당 된 바이트 수입니다.  이 주석은 엄격 하 게 잘못 되지 않으며 할당 된 크기를 표현 하는 것이 좋습니다.  그러나 요소의 개수 함수에 의해 초기화 되는 것을 알려주지 않습니다.  
  
 다음 예제에서는 완전히 버퍼 초기화 부분의 정확한 크기를 지정 하려면 세 가지 올바른 방법을 보여 줍니다.  
  
```cpp  
  
// Correct  
void Func1(_Out_writes_to_(size, *pCount) CHAR *pb,   
    DWORD size,  
    PDWORD pCount  
);  
  
void Func2(_Out_writes_all_(size) CHAR *pb,   
    DWORD size  
);  
  
void Func3(_Out_writes_(size) PSTR pb,   
    DWORD size  
);  
  
```  
  
## \_Out\_ PSTR  
 `_Out_ PSTR` 의 사용은 거의 항상 잘못된 것입니다.  이 출력 매개 변수는 문자 버퍼를 가리키는 것으로 해석 되 고 NULL로 끝나는 것입니다.  
  
```cpp  
  
// Incorrect  
void Func1(_Out_ PSTR pFileName, size_t n);  
  
// Correct  
void Func2(_Out_writes_(n) PSTR wszFileName, size_t n);  
  
```  
  
 `_In_ PCSTR` 과 같은 주석은 일반적이고 유용 합니다.  입력된 문자열에 NULL 종료를 가리키는의 전제 조건  `_In_`  하면 NULL로 끝나는 문자열을 인식 합니다.  
  
## \_In\_ WCHAR\* p  
 `_In_ WCHAR* p`입력된 포인터 라는  `p`  문자를 가리키는 있습니다.  그러나 대부분의 경우에서이 없는 것입니다 사양입니다.  대신, 아마도 의도 NULL로 끝나는 배열; 사양 이렇게 하려면  `_In_ PWSTR` 을 사용하세요.  
  
```cpp  
  
// Incorrect  
void Func1(_In_ WCHAR* wszFileName);  
  
// Correct  
void Func2(_In_ PWSTR wszFileName);  
  
```  
  
 NULL 종료의 적절 한 사양이 일반적입니다.  적절 한 사용  `STR`  버전을 다음 예제와 같이 형식으로 대체 합니다.  
  
```cpp  
  
// Incorrect  
BOOL StrEquals1(_In_ PCHAR p1, _In_ PCHAR p2)  
{  
    return strcmp(p1, p2) == 0;  
}  
  
// Correct  
BOOL StrEquals2(_In_ PSTR p1, _In_ PSTR p2)  
{  
    return strcmp(p1, p2) == 0;  
}  
  
```  
  
## \_Out\_range\_  
 매개 변수는 포인터 값이 가리키는 포인터를 사용 하 여 요소의 범위를 표현할 경우  `_Deref_out_range_`  대신  `_Out_range_` 을 사용하세요.  다음 예제에서는 범위 pcbFilled이 아니라 \* pcbFilled이 표현됩니다.  
  
```cpp  
  
// Incorrect  
void Func1(  
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,   
    DWORD cbSize,   
    _Out_range_(0, cbSize) DWORD *pcbFilled  
);  
  
// Correct  
void Func2(  
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,   
    DWORD cbSize,   
    _Deref_out_range_(0, cbSize) _Out_ DWORD *pcbFilled   
);  
  
```  
  
 `_Deref_out_range_(0, cbSize)`유추할 수 있기 때문에 꼭 필요한 몇 가지 도구는  `_Out_writes_to_(cbSize,*pcbFilled)` , 있지만 편의 위해 여기 표시 됩니다.  
  
## \_When\_의 잘못된 컨텍스트  
 사전에 대한 사후 상태 평가를 사용하여 다른 일반적인 실수가 있습니다.  다음 예제에서 `_Requires_lock_held_`는 precondition입니다.  
  
```cpp  
  
// Incorrect  
_When_(return == 0, _Requires_lock_held_(p->cs))  
int Func1(_In_ MyData *p, int flag);  
  
// Correct  
_When_(flag == 0, _Requires_lock_held_(p->cs))  
int Func2(_In_ MyData *p, int flag);  
  
```  
  
 `result` 식은 전 상태로 사용할 수 없는 후 상태 값을 참조 합니다.  
  
## \_Success\_: TRUE  
 함수가 성공 하면 반환 값은 0이 아닌 경우  `return != 0`  대신 성공 조건으로  `return == TRUE` 을 사용합니다.  0이 아니면 반드시 동등성에 대 한 컴파일러를 제공 하는 실제 값을  `TRUE`  사용합니다.  매개 변수를  `_Success_`  는 식 및 다음 식은 동일한 것으로 평가 됩니다:  `return != 0` ,  `return != false` ,  `return != FALSE` , 및  `return`  매개 변수 또는 비교 없이 사용합니다.  
  
```cpp  
  
// Incorrect  
_Success_(return == TRUE, _Acquires_lock_(*lpCriticalSection))  
BOOL WINAPI TryEnterCriticalSection(  
  _Inout_ LPCRITICAL_SECTION lpCriticalSection  
);  
  
// Correct  
_Success_(return != 0, _Acquires_lock_(*lpCriticalSection))  
BOOL WINAPI TryEnterCriticalSection(  
  _Inout_ LPCRITICAL_SECTION lpCriticalSection  
);  
  
```  
  
## 참조 변수  
 참조 변수의 SAL의 이전 버전 주석 대상으로 암시적된 포인터를 사용 하 고 추가 되어야는  `__deref`  변수 참조에 연결 된 주석입니다.  이 버전 개체 자체를 사용 하고 `_Deref_`가 추가로 필요 하지 않습니다.  
  
```cpp  
  
// Incorrect  
void Func1(  
    _Out_writes_bytes_all_(cbSize) BYTE *pb,   
    _Deref_ _Out_range_(0, 2) _Out_ DWORD &cbSize  
);  
  
// Correct  
void Func2(  
    _Out_writes_bytes_all_(cbSize) BYTE *pb,   
    _Out_range_(0, 2) _Out_ DWORD &cbSize  
);  
  
```  
  
## 반환 값에 대한 주석  
 다음 예제에서는 주석을 반환 값에 일반적인 문제를 보여 줍니다.  
  
```cpp  
  
// Incorrect  
_Out_opt_ void *MightReturnNullPtr1();  
  
// Correct  
_Ret_maybenull_ void *MightReturnNullPtr2();  
  
```  
  
 이 예제에서는  `_Out_opt_`  포인터는 전제 조건으로 NULL 일 수 있음을 표시 합니다.  그러나 전제 조건이 반환 값에 적용할 수 없습니다.  이 경우에 올바른 주석은  `_Ret_maybenull_` 입니다.  
  
## 참고 항목  
 [C\/C\+\+ 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [SAL 이해](../code-quality/understanding-sal.md)   
 [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)   
 [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)   
 [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)   
 [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)   
 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [내장 함수](../code-quality/intrinsic-functions.md)