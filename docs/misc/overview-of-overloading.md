---
title: "오버로드 개요 | Microsoft Docs"
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
  - "함수 오버 로드 함수 오버 로드 하는 방법에 대 한"
  - "연산자 오버 로드 된 연산자에 대 한 오버 로드"
ms.assetid: cd012dd4-607c-4f8e-bd2e-2bd506ac81ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 오버로드 개요
C\+\+ 언어를 사용하면 함수와 연산자를 오버로드할 수 있습니다. 오버로딩은 같은 범위에서 지정된 함수 이름의 정의를 두 개 이상 제공하는 방법입니다. 컴파일러는 호출에 사용된 인수를 기준으로 적절한 버전의 함수나 연산자를 선택합니다. 예를 들어 max 함수가 오버로드된 함수인 경우, 이 함수를 코드에서 다음과 같이 사용할 수 있습니다.  
  
```  
// overview_overload.cpp  
double max( double d1, double d2 )  
{  
   return ( d1 > d2 ) ? d1 : d2;  
}  
  
int max( int i1, int i2 )  
{  
   return ( i1 > i2 ) ? i1 : i2;  
}  
int main()  
{  
   int    i = max( 12, 8 );  
   double d = max( 32.9, 17.4 );  
}  
```  
  
 `int` 형식의 두 변수에 대한 최대값이 요청되는 첫 번째 함수 호출에서는 `max( int, int )` 함수가 호출됩니다. 그러나 두 번째 함수 호출에서는 인수가 `double` 형식이므로 `max( double, double )` 함수가 호출됩니다.  
  
## 참고 항목  
 [오버 로드 \(c \+ \+\)](../misc/overloading-cpp.md)