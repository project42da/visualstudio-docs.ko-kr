---
title: "함수 동작에 주석 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_On_failure_"
  - "_Return_type_success_"
  - "_Always_"
  - "_Maybe_raises_SEH_exception_"
  - "_Raises_SEH_exception_"
  - "_Called_from_function_class_"
  - "_Function_class_"
  - "_Must_inspect_result_"
  - "_Success_"
  - "_Check_return_"
  - "_Use_decl_annotations_"
ms.assetid: c0aa268d-6fa3-4ced-a8c6-f7652b152e61
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 함수 동작에 주석 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[함수 매개 변수 및 값 반환](../code-quality/annotating-function-parameters-and-return-values.md) 주석을 추가 하는 것 외에도 전체 함수 속성에 주석을 달 수 있습니다.  
  
## 함수 주석  
 전체 함수에 적용하고 동작 방식을 요약하거나 기대를 설명합니다.  
  
|주석|설명|  
|--------|--------|  
|`_Called_from_function_class_(name)`|독립 실행형. 대신이 조건자와 함께 `_When_` 주석이 사용됩니다.  자세한 내용은 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)을 참조하십시오.<br /><br /> `name` 매개 변수는 또한 표시 되는 임의의 문자열을 `_Function_class_` 일부 함수 선언에 주석을.  `_Called_from_function_class_` 를 분석 하는 함수를 사용 하 여 주석을 처리 하는 경우 0이 아닌 반환 `_Function_class_` 의 같은 값을 가지는 `name`. 그렇지 않으면 0을 반환 합니다.|  
|`_Check_return_`|반환 값에 주석을 추가하고 호출자를 검사 해야만 합니다.  Void 컨텍스트에서 호출 되면 함수는 오류를 보고해야 합니다.|  
|`_Function_class_(name)`|`name` 매개 변수는 사용자가 지정하는 임의의 문자열입니다.  다른 네임 스페이스에서 다른 네임 스페이스에 존재 합니다.  함수, 함수 포인터 또는\-가장 유용하게\-함수 포인터 형식에는 하나 이상의 함수 클래스에 속하는 것으로 지정 될 수 있습니다.|  
|`_Raises_SEH_exception_`|항상 따르는 구조적 예외 처리기 \(SEH\) 예외를 발생 시키는 함수 주석을 `_When_` 및 `_On_failure_` 조건에 추가합니다.  자세한 내용은 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)을 참조하십시오.|  
|`_Maybe_raises_SEH_exception_`|선택적으로 SEH 예외를 적용시킬 수 있는 함수에 주석을 `_When_` 및 `_On_failure_` 조건에 추가합니다.|  
|`_Must_inspect_result_`|반환 값, 매개 변수 및 전역 변수를 포함하여 모든 출력 값에 주석을 추가 합니다.  분석기는 주석이 지정된 개체의 값은 이후에 검사하지 오류를 보고 합니다. 조건식이 사용되는지 출력 매개 변수를 지정 하거나 전역 또는 매개 변수로 전달된 "검사"를 포함 합니다.  반환 값에 대해 `_Must_inspect_result_` 는 `_Check_return_`를 암시합니다.|  
|`_Use_decl_annotations_`|헤더에서 주석 목록 대신 함수 정의 \(함수 본문\)에서 사용할 수 있습니다.  `_Use_decl_annotations_` 이 사용될 때, 같은 기능에 대한 범위 헤더에 표시되는 주석은 마치 `_Use_decl_annotations_` 주석을 갖고 있는 정의에서 나타나는 것 처럼 사용됩니다.|  
  
## 성공\/실패 주석  
 함수가 실패할 때, 이 결과는 불완전하게 되거나 함수가 성공하면 결과는 다르게 됩니다.  다음 목록에서 주석을 실패 동작을 표현하는 방법을 제공 합니다.  이러한 주석을 사용하여 성공여부를 결정할 수 있도록 설정해야 합니다. 따라서 `_Success_` 주석이 필요 합니다.  `NTSTATUS` 및 `HRESULT` 가 `_Success_` 주석을 안에 생성하는 것을 주목해야 합니다.; 그러나 사용자 지정 `_Success_` 주석을 `NTSTATUS` 또는 `HRESULT` 에 갖고 있으면, 주석을 생성하는 것을 오버라이드 합니다.  
  
|주석|설명|  
|--------|--------|  
|`_Always_(anno_list)`|`anno_list _On_failure_(anno_list)` 주석에 해당하는, `anno_list` 에서의 주석은 함수의 성공 여부를 적용 합니다.|  
|`_On_failure_(anno_list)`|`_Success_` 가 함수에 주석을 지정할 때 사용됩니다.\-명시적으로 또는 암시적으로 통해 `_Return_type_success_` 이 형식 정의에 있습니다.  `_On_failure_` 주석이 함수 매개 변수 또는 반환 값의 `anno_list` 에서 \(anno\) `_When_(!expr, anno)` 로 코딩된 것 처럼 표현되었을 때, `expr` 인 곳은 요구된 `_Success_` 에서의 파라미터입니다.  즉, 모든 조건에서 `_Success_` 의 암시적인 응용 프로그램은 `_On_failure_` 에 적용 되지 않습니다.|  
|`_Return_type_success_(expr)`|형식 정의에 적용될 수 있습니다.  해당 형식을 반환하고 명시적으로 `_Success_` 을 하지 않는 모든 함수는 마치 `_Success_(expr)`을 갖고 있는 것 처럼 주석이 달리는 것을 나타냅니다.  `_Return_type_success_` 는 함수 또는 함수 포인터 형식 정의에 사용할 수 없습니다.|  
|`_Success_(expr)`|`expr` 는 rvalue를 생성하는 식입니다.  `_Success_` 이 함수 선언 또는 정의에 나타내어 지면 함수에서 각 주석\(`anno`\) 과 사후 조건은 마치 `_When_(expr, anno)` 에 코딩된 것 처럼 동작합니다.  `_Success_` 주석은 반환 형식이나 매개 변수가 없는 함수에만 사용할 수 있습니다.  최대 하나의 `_Success_` 주석이 있을 수 있고 이것은 어떠한 `_When_`, `_At_`, 또는 `_Group_` 이 될 수 없습니다.  자세한 내용은 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)을 참조하십시오.|  
  
## 참고 항목  
 [C\/C\+\+ 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [SAL 이해](../code-quality/understanding-sal.md)   
 [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)   
 [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)   
 [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)   
 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [내장 함수](../code-quality/intrinsic-functions.md)   
 [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)