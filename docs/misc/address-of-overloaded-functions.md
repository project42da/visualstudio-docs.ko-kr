---
title: "오버로드된 함수의 주소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "주소 [c + +] 오버 로드 된 함수"
  - "오버 로드 된 반환 주소 [c + +]"
  - "함수 오버 로드 함수 주소"
  - "이 오버 로드 된 함수 포인터"
ms.assetid: e7913e65-a295-445d-b2b0-1e60f8dfbc54
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 오버로드된 함수의 주소
인수 없이 함수 이름을 사용하면 해당 함수의 주소가 반환됩니다. 예:  
  
```  
int Func( int i, int j );  
int Func( long l );  
  
...  
  
int (*pFunc) ( int, int ) = Func;  
```  
  
 위의 예제에서는 `Func`의 첫 번째 버전이 선택되고 해당 주소가 `pFunc`에 복사됩니다.  
  
 컴파일러는 대상의 인수 목록과 정확하게 일치하는 인수 목록이 있는 함수를 찾아 선택할 함수의 버전을 결정합니다. 오버로드된 함수 선언의 인수는 다음 중 하나와 일치합니다.  
  
-   초기화되는 개체\(위의 예제에 나와 있음\)  
  
-   할당 문의 왼쪽  
  
-   함수에 대한 형식 인수  
  
-   사용자 정의 연산자에 대한 형식 인수  
  
-   함수 반환 형식  
  
 정확하게 일치하는 항목이 없는 경우 함수의 주소를 사용하는 식은 모호해지고 오류가 생성됩니다.  
  
 비멤버 함수 `Func`가 위의 예제에서 사용되었지만 오버로드된 멤버 함수의 주소를 사용할 때 동일한 규칙이 적용됩니다.  
  
## 참고 항목  
 [오버 로드 \(c \+ \+\)](../misc/overloading-cpp.md)