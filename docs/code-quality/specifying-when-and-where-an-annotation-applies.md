---
title: "주석 적용 시기 및 위치 지정 | Microsoft Docs"
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
  - "_Group_"
  - "_At_"
  - "_When_"
  - "_At_buffer_"
ms.assetid: 8e4f4f9c-5dfa-4835-87df-ecd1698fc650
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 주석 적용 시기 및 위치 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

조건부 주석 경우 분석기를 지정 하는 다른 주석 해야 합니다.  예를 들어, 함수에 동기적 이거나 비동기적일 수 있는 변수, 함수는 다음과 같이 동작 합니다: 동기의 경우에서 항상 결국 성공 하지만 비동기 작업의 경우에 오류를 보고 바로 성공할 수 없는 경우가 있습니다.  함수를 동기적으로 호출 반환 있을 것 때문에 코드 분석기 값을 제공 결과 값을 확인 합니다.  그러나 함수를 비동기적으로 호출 하 고 함수 결과 선택 하지 않은 경우 심각한 오류가 발생할 수 있습니다.  사용할 수 있는 상황을 보여 주는이 예제는 `_When_` 주석\-이 문서의 뒷부분에 설명 된\-검사를 합니다.  
  
## 구조적 주석  
 주석 적용 시기 및 위치를 제어 하는 다음과 같은 구조적 주석을 사용 합니다.  
  
|주석|설명|  
|--------|--------|  
|`_At_(expr, anno-list)`|`expr` 는 rvalue를 생성하는 식입니다.  주석에서 `anno-list` 에서 명명 된 개체에 적용 되는 `expr`입니다.  각 주석에서 `anno-list`, `expr` 주석 사전 조건에서 해석 되 고 사후 조건의 경우 주석 사후 조건의 해석 됩니다 경우 사전 조건에서 해석 됩니다.|  
|`_At_buffer_(expr, iter, elem-count, anno-list)`|`expr` 는 rvalue를 생성하는 식입니다.  주석에서 `anno-list` 에서 명명 된 개체에 적용 되는 `expr`입니다.  각 주석에서 `anno-list`, `expr` 주석 사전 조건에서 해석 되 고 사후 조건의 경우 주석 사후 조건의 해석 됩니다 경우 사전 조건에서 해석 됩니다.<br /><br /> `iter` 주석으로 범위가 지정 된 변수 이름 \(포함의  `anno-list` \).  `iter`암시적 형식에  `long` .  같은 이름의 변수를 포함 하는 범위 계산에서 숨겨집니다.<br /><br /> `elem-count`정수로 확인되는 C\+\+ 식입니다.|  
|`_Group_(anno-list)`|주석에서 `anno-list` 각 주석에 적용 되는 그룹 주석에 적용 되는 한정자로 간주 됩니다.|  
|`_When_(expr, anno-list)`|`expr`변환할 수 있는 식 `bool`입니다.  0이 아닌 경우 \(`true`\)에 지정 된 주석  `anno-list`  적용 가능한 것으로 간주 됩니다.<br /><br /> 기본적으로 각 주석에서 `anno-list`, `expr` 주석을 경우 출력 값을 사용하여 주석이 되는 사후 조건 경우 입력된 값을 사용하여 해석됩니다.  기본값을 재정의 하는 데 사용할 수 있는 `_Old_` 입력된 값을 사용 해야 함을 나타내기 위해 사후 조건을 평가할 때 내장합니다. **Note:**  여러 주석을 사용하여 결과로 받아들일 수 `_When_` 값을 변경할 수 있는 경우\-예를 들어, `*pLength`\-때문에 관련 된 평가한 결과를 `expr` 사전에서 사후 조건의 평가 결과에서 달라질 수 있습니다.|  
  
## 참고 항목  
 [C\/C\+\+ 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [SAL 이해](../code-quality/understanding-sal.md)   
 [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)   
 [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)   
 [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)   
 [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)   
 [내장 함수](../code-quality/intrinsic-functions.md)   
 [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)