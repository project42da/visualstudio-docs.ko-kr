---
title: "unchecked_uninitialized_copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.unchecked_uninitialized_copy"
  - "unchecked_uninitialized_copy"
  - "std::unchecked_uninitialized_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unchecked_uninitialized_copy 함수"
ms.assetid: 38568841-314e-446b-91d0-92cc231e3b3c
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
---
# unchecked_uninitialized_copy
[uninitialized\_copy](../Topic/uninitialized_copy.md)와 동일하지만 \_SECURE\_SCL\=1이 정의된 경우 선택하지 않은 반복기를 출력 반복기로 사용하도록 허용합니다. 이 함수에 정의 된는 [stdext 네임스페이스](/visual-cpp/standard-library/stdext-namespace) 네임 스페이스입니다.  
  
> [!NOTE]
>  이 알고리즘은 표준 C\+\+ 라이브러리의 Microsoft 확장입니다. 이 알고리즘을 사용하여 구현된 코드는 이식할 수 없습니다.  
  
## 구문  
  
```  
template<class InputIterator, class ForwardIterator>  
   ForwardIterator unchecked_uninitialized_copy(  
      InputIterator _First,  
      InputIterator _Last,  
      ForwardIterator _Dest  
   );  
  
template<class InputIterator, class ForwardIterator, class Allocator>  
   ForwardIterator unchecked_uninitialized_copy(  
      InputIterator _First,  
      InputIterator _Last,  
      ForwardIterator _Dest,  
      Allocator& _Al  
   );  
```  
  
#### 매개 변수  
 `_First`  
 복사할 소스 범위에 있는 첫 번째 요소를 주소 지정하는 입력 반복기입니다.  
  
 `_Last`  
 복사할 소스 범위에 있는 마지막 요소를 주소 지정하는 입력 반복기입니다.  
  
 `_Dest`  
 복사할 대상 범위에 있는 첫 번째 요소를 주소 지정하는 정방향 반복기입니다.  
  
 `_Al`  
 이 개체에 사용할 할당자 클래스입니다.[vector::get\_allocator](../Topic/vector::get_allocator.md) 개체에 대 한 할당자 클래스를 반환합니다.  
  
## 반환 값  
 복사본을 수신하는 대상 범위에서 마지막 요소 하나 다음의 위치를 주소 지정하는 정방향 반복기입니다.  
  
## 설명  
 참조 [uninitialized\_copy](../Topic/uninitialized_copy.md) 코드 샘플입니다.  
  
 확인 된 반복기에 대 한 자세한 내용은 참조 하십시오. [Checked Iterators](/visual-cpp/standard-library/checked-iterators)합니다.  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** stdext