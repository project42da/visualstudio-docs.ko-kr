---
title: 내장 함수
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _String_length_
- _Param_
- _Curr_
- _Old_
- _Nullterm_length_
- _Inexpressible_
ms.assetid: adf29f8c-89fd-4a5e-9804-35ac83e1c457
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 0e58f84a48104553e5517d24f746769e6f0959e5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="intrinsic-functions"></a>내장 함수
의도 하지 않은 식 않는다는 점을 SAL에 식을 C/c + + 식 수-예를 들어, + +,--, 및이 컨텍스트에서 의도 하지 않은 모든 함수 호출 합니다.  그러나 SAL는 일부 함수와 비슷한 개체 및 SAL 식에 사용할 수 있는 일부 예약 된 기호를 제공 합니다. 이 라고 *내장 함수*합니다.

## <a name="general-purpose"></a>일반 용도
 다음과 같은 내장 함수 주석을 sal 일반 유틸리티를 제공합니다.

|주석|설명|
|----------------|-----------------|
|`_Curr_`|현재 주석이 추가 되는 개체에 대 한 동의어입니다.  경우는 `_At_` 주석 사용 중인 `_Curr_` 첫 번째 매개 변수를 동일 `_At_`합니다.  그렇지 않으면 매개 변수 또는 주석이 어휘 적으로 연결 된 전체 함수/반환 값은입니다.|
|`_Inexpressible_(expr)`|버퍼의 크기를 너무 복잡해 서 주석 식을 사용 하 여 표시할 수는 경우에 따라 표시-예를 들어 구성원을 선택는 입력된 데이터 집합을 검색 한 다음를 계산 하 여 계산 됩니다.|
|`_Nullterm_length_(param)`|`param` 최대 버퍼를 제외 하는 null 종결자에 있는 요소의 수가입니다. 비 집계, void가 아닌 형식의 모든 버퍼에 적용할 수 있습니다.|
|`_Old_(expr)`|사전 조건에서 평가 되는 경우 `_Old_` 입력된 값을 반환 `expr`합니다.  값을 반환 한다는 사후 조건에서 계산할 때 `expr` 것 평가 사전 조건에서으로 합니다.|
|`_Param_(n)`|`n`번째 매개 변수 1부터 계산 하는 함수를 `n`, 및 `n` 리터럴 정수 계열 상수입니다. 매개 변수 이름이이 주석은 매개 변수 이름으로 액세스 합니다. **참고:** `n` , 줄임표로 정의 된 또는 이름이 사용 되지 않습니다 함수 프로토타입을에 사용할 수 있습니다 하는 위치 매개 변수를 참조할 수 있습니다.  |
|`return`|C/c + + 예약 키워드 `return` 함수의 반환 값을 나타내는 SAL 식에 사용할 수 있습니다.  값 에서만 사용 가능 게시물 상태 이면 것은 사전 상태에서 사용 하는 구문 오류입니다.|

## <a name="string-specific"></a>특정 문자열
 다음과 같은 내장 함수 주석을 문자열을 조작할을 수 있습니다. 이러한 함수의 4를 모두 같은 용도로 사용: null 종결자 앞 발견 된 형식의 요소 수를 반환 합니다. 이 참조 하는 요소에서 데이터의 종류는 차이가 발생 합니다. 사용 하 여, null로 끝나는의 길이 지정 하려는 경우 버퍼링 하는 문자로 구성 되어 있지는 `_Nullterm_length_(param)` 이전 섹션에서 주석입니다.

|주석|설명|
|----------------|-----------------|
|`_String_length_(param)`|`param` null 종결자를 포함 하지 않고 하지만 최대 문자열에 있는 요소의 수가입니다. 이 주석 문자 문자열 형식으로 예약 됩니다.|
|`strlen(param)`|`param` null 종결자를 포함 하지 않고 하지만 최대 문자열에 있는 요소의 수가입니다. 이 주석 문자에 사용 하 여 배열 및 C 런타임 함수를 유사한 예약 되어 [strlen()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)합니다.|
|`wcslen(param)`|`param` 최대 (포함 되지 않음) 하는 문자열에 있는 요소의 수는 null 종결자입니다. 이 주석으로 예약 되어 와이드 문자에 사용 하 여 배열 및 C 런타임 함수를 유사한 [wcslen()](/cpp/c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l)합니다.|

## <a name="see-also"></a>참고 항목
 [C/c + + 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md) [SAL 이해](../code-quality/understanding-sal.md) [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md) [함수동작에주석지정](../code-quality/annotating-function-behavior.md) [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md) [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md) [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md) [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)