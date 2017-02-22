---
title: "내장 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_String_length_"
  - "_Param_"
  - "_Curr_"
  - "_Old_"
  - "_Nullterm_length_"
  - "_Inexpressible_"
ms.assetid: adf29f8c-89fd-4a5e-9804-35ac83e1c457
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 내장 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

SAL 식은 부작용 없는 식을 제공합니다. 예를 들어 \+\+, \-\- 그리고 함수는 모든 이 내용에서 부작용을 갖고 있습니다.  그러나 SAL은 일부 함수와 비슷한 개체와 SAL 식에 사용할 수 있는 몇 가지 예약 된 기호를 제공합니다.  이러한 함수를 *고유한 함수*라고 합니다.  
  
## 일반 용도  
 다음 instrinsic 함수 주석 SAL에 일반 유틸리티를 제공합니다.  
  
|주석|설명|  
|--------|--------|  
|`_Curr_`|현재 주석이 추가되는 개체에 대한 약어입니다.  `_At_` 주석을 사용 중이면, `_Curr_` 는 `_At_` 에 첫 번째 매개 변수와 동일합니다.  그렇지 않으면 주석 의미상 연결된 전체 함수\/반환 값 또는 매개 변수입니다.|  
|`_Inexpressible_(expr)`|버퍼의 크기를 나타내는 주석 식을 사용하여 너무 복잡 한 경우 표현\-예를 들어 구성원 선택 입력된 데이터 집합을 검색 한 후 계산하여 계산 됩니다.|  
|`_Nullterm_length_(param)`|`param` 는 null 종결자를 포함하지 않는 최대 버퍼의 요소 수 입니다.  버퍼 비 집계, void가 아닌 형식에 적용할 수 있습니다.|  
|`_Old_(expr)`|이전 상태에서 계산되는 경우 `_Old_` 는 입력값 `expr` 를 반환합니다.  사후 조건에서 계산하는 경우 이전 상태에서 계산된 `expr` 값을 반환합니다.|  
|`_Param_(n)`|`n`th 매개 변수를 1부터 계산 하는 함수 `n`, 및 `n` 는 리터럴 정수 계열 상수입니다.  매개 변수 이름이 지정되면 이 이름에 의해 주석 매개 변수 이름으로 액세스할 수 있도록 합니다. **Note:**  `n` 는 줄임표에 의해 정의되거나 이름이 사용되지 않는 함수 프로토타입에 사용될 수 있는 위치 매개 변수를 참조할 수 있습니다.|  
|`return`|C\/C\+\+ 예약된 키워드 `return` 는 함수의 반환 값을 나타내는 SAL 식에 사용할 수 있습니다.  게시 상태에만 사용할 수 있는 값; 구문 오류 전 상태로 사용합니다.|  
  
## 특정 문자열  
 다음 내장 함수 주석 문자열을 조작할 수 있습니다.  이러한 함수의 네 모두 같은 용도로 사용: null 종결자가 되기 전에 발견되는 형식의 요소 수를 반환합니다.  차이점은 참조 하는 요소에 있는 데이터의 종류입니다.  Null로 끝나는 길이 지정 하려면 버퍼에 없는 문자로 구성 되는 것을 주의하여, 이전 섹션에서의 `_Nullterm_length_(param)` 주석을 사용합니다.  
  
|주석|설명|  
|--------|--------|  
|`_String_length_(param)`|`param` 는 null 종결자를 포함하지 않는 최대 버퍼의 요소 수 입니다.  이 주석 문자 문자열 형식에 대한 예약이 되어 있습니다.|  
|`strlen(param)`|`param` 는 null 종결자를 포함하지 않는 최대 버퍼의 요소 수 입니다.  이 주석 문자를 사용하여 배열과 같은 C 런타임 함수 [strlen\(\)](/visual-cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)에 대해 예약됩니다.|  
|`wcslen(param)`|`param` 는 null 종결자를 포함하지 않는 최대 버퍼의 요소 수 입니다.  이 주석은 와이드 문자의 사용에 대해 예약되고 배열과 같은 C 런타임 함수 [wcslen\(\)](/visual-cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)와 비슷합니다.|  
  
## 참고 항목  
 [C\/C\+\+ 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [SAL 이해](../code-quality/understanding-sal.md)   
 [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)   
 [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)   
 [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)   
 [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)   
 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)