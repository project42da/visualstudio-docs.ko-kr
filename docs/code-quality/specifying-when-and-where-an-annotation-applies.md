---
title: 주석 적용 시기 및 위치 지정
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- _Group_
- _At_
- _When_
- _At_buffer_
ms.assetid: 8e4f4f9c-5dfa-4835-87df-ecd1698fc650
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 9d99ebce3adc27039763e11ed4882a20199e8469
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="specifying-when-and-where-an-annotation-applies"></a>주석 적용 시기 및 위치 지정
주석을 이면 조건부 분석기 되도록 지정 하려면 다른 주석이 필요할 수 있습니다.  예를 들어 함수에는 동기 또는 비동기 일 수 있는 변수, 있으면 함수는 다음과 같이 동작: 동기 경우에서 항상 결국 성공 하지만 비동기 작업의 경우에 오류를 보고 즉시 성공할 수 없는 경우. 함수를 동기적으로 호출 되 면 반환 하지는 하기 때문에 코드 분석기 한 값을 제공 결과 값을 확인 합니다.  그러나 함수를 비동기적으로 호출 하는 경우 함수 결과 선택 하지 않으면 심각한 오류가 발생할 수 있습니다. 사용할 수 있는 상황을 보여 주는이 예제는 `_When_` 주석-이 문서의 뒷부분에 설명 된-확인을 사용 하 합니다.

## <a name="structural-annotations"></a>구조적 주석
 주석 적용 시기 및 위치를 제어 하려면 다음과 같은 구조 주석을 사용 합니다.

|주석|설명|
|----------------|-----------------|
|`_At_(expr, anno-list)`|`expr` lvalue를 생성 하는 식이입니다. 에 대 한 주석 `anno-list` 로 명명 된 개체에 적용 됩니다 `expr`합니다. 각 주석이 대 한 `anno-list`, `expr` 사전 조건에 주석이 해석 되 고 경우에 사후 조건에는 주석이 해석 되는 사후 조건 경우 사전 조건으로 해석 됩니다.|
|`_At_buffer_(expr, iter, elem-count, anno-list)`|`expr` lvalue를 생성 하는 식이입니다. 에 대 한 주석 `anno-list` 로 명명 된 개체에 적용 됩니다 `expr`합니다. 각 주석이 대 한 `anno-list`, `expr` 사전 조건에서 주석이 해석 되 고 경우에 사후 조건에는 주석이 해석 되는 사후 조건 경우 사전 조건으로 해석 됩니다.<br /><br /> `iter` 주석으로 범위가 제한 된 변수의 이름입니다 (포함 `anno-list`). `iter` 에 암시적 형식이 `long`합니다. 바깥쪽 범위에서 동일 하 게 명명 된 변수는 평가에서 숨겨집니다.<br /><br /> `elem-count` 정수로 확인 되는 식이입니다.|
|`_Group_(anno-list)`|에 대 한 주석 `anno-list` 각 주석에 적용 되는 그룹 주석에 적용 되는 모든 한정자가를 고려 합니다.|
|`_When_(expr, anno-list)`|`expr` 로 변환할 수 있는 식 `bool`합니다. 0이 아닌 경우 (`true`)에 지정 된 주석은 `anno-list` 적용 가능한 것으로 간주 됩니다.<br /><br /> 기본적으로 각 주석에서에 대해 `anno-list`, `expr` 주석이 이며 경우 출력 값을 사용 하 여 주석이 사후 조건 하는 경우 입력된 값을 사용 하 여 해석 됩니다. 기본값을 재정의 하려면 사용할 수 있습니다는 `_Old_` 입력된 값을 사용 해야 함을 나타내기 위해 사후 조건을 평가할 때 내장 함수입니다. **참고:** 다른 주석을 사용 하 여 결과로 받아들일 수 `_When_` 경우 변경할 수 있는 값-예를 들어 `*pLength`-과정이 진행 중 이므로 계산된 된 결과 `expr` 사전 조건에서 해당 계산에서 달라질 수 있습니다 사후 조건에서 발생 합니다.|

## <a name="see-also"></a>참고 항목
 [C/c + + 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md) [SAL 이해](../code-quality/understanding-sal.md) [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md) [함수동작에주석지정](../code-quality/annotating-function-behavior.md) [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md) [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md) [내장 함수](../code-quality/intrinsic-functions.md) [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)