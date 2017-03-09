---
title: "컴파일러 오류 CS0135 | Microsoft Docs"
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
  - "CS0135"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0135"
ms.assetid: 1bda402c-e8bd-4117-93d9-f4968d9e8303
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0135
'declaration1'이 'declaration2' 선언과 충돌합니다.  
  
 컴파일러는 일반적으로 코드에서 논리 오류를 발생시키는 이름 숨기기를 허용하지 않습니다.  
  
## 예제  
 다음 샘플에서는 CS0135를 생성합니다.  
  
```  
// CS0135.cs  
public class MyClass2  
{  
   public static int i = 0;  
  
   public static void Main()  
   {  
      {  
         int i = 4;  
         i++;  
      }  
      i = 0;   // CS0135  
   }  
}  
```  
  
 [C\# 언어 사양](/dotnet/csharp/language-reference/language-specification), 섹션 7.5.2.1에서:  
  
 지정된 식별자가 식 또는 선언자에서 지역 변수 선언 공간\(§3.3\) 안에 단순한 이름으로 발생할 때마다 식 또는 선언자의 단순한 이름과 동일한 식별자가 두 번 발생할 때 한 번씩은 동일한 엔터티를 참조해야 합니다. 이 규칙은 지정된 블록, 스위치 블록, for\-, foreach\- 또는 using\-문 또는 무명 함수 내에서 이름의 의미가 항상 같아야 합니다.