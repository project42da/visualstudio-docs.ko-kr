---
title: "unchecked_adjacent_difference | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.unchecked_adjacent_difference"
  - "std::unchecked_adjacent_difference"
  - "unchecked_adjacent_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unchecked_adjacent_difference 함수"
ms.assetid: 3a6b0b49-a84b-40b1-bcd5-3bf76c6ef7d7
caps.latest.revision: 14
caps.handback.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
---
# unchecked_adjacent_difference
와 동일 [adjacent\_difference](../Topic/adjacent_difference.md), 출력 반복기로 확인 되지 않은 반복기를 사용할 수 있도록 하지만 때 \_SECURE\_SCL \= 1 정의 됩니다.`unchecked_adjacent_difference` 에 정의 된 `stdext` 네임 스페이스입니다.  
  
> [!NOTE]
>  이 알고리즘은 표준 C\+\+ 라이브러리의 Microsoft 확장입니다. 이 알고리즘을 사용하여 구현된 코드는 이식할 수 없습니다.  
  
## 구문  
  
```  
template<class InputIterator, class OutIterator>  
   OutputIterator unchecked_adjacent_difference(  
      InputIterator_First,  
      InputIterator _Last,  
      OutputIterator_Result   
   );  
  
template<class InputIterator, class OutputIterator, class BinaryOperation>  
   OutputIterator unchecked_adjacent_difference(  
      InputIterator_First,  
      InputIterator _Last,  
      OutputIterator_Result,   
      BinaryOperation _Binary_op  
   );  
```  
  
#### 매개 변수  
 `_First`  
 입력 범위에서 해당 선행 작업과 차별화해야 하거나 지정된 다른 이진 작업에서 값 쌍을 처리해야 하는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.  
  
 `_Last`  
 입력 범위에서 해당 선행 작업과 차별화해야 하거나 지정된 다른 이진 작업에서 값 쌍을 처리해야 하는 마지막 요소를 주소 지정하는 입력 반복기입니다.  
  
 `_Result`  
 일련의 차이 또는 지정된 작업의 결과를 저장할 대상 범위의 첫 번째 요소를 주소 지정하는 출력 반복기입니다.  
  
 `_Binary_op`  
 차이 절차에서 차감 연산을 대체하는 일반화된 연산에 적용할 이항 연산입니다.  
  
## 반환 값  
 대상 범위의 끝 주소를 지정 하는 출력 반복기: `_Result` \+ \(`_Last` \- `_First`\).  
  
## 설명  
 참조 [adjacent\_difference](../Topic/adjacent_difference.md) 코드 샘플입니다.  
  
 확인 된 반복기에 대 한 자세한 내용은 참조 하십시오. [Checked Iterators](/visual-cpp/standard-library/checked-iterators)합니다.  
  
## 요구 사항  
 **헤더:** \<numeric\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)