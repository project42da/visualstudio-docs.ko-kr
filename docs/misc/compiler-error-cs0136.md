---
title: "컴파일러 오류 CS0136 | Microsoft Docs"
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
  - "CS0136"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0136"
ms.assetid: 379a1a7d-c52c-4f2b-9e77-c1107d26faf4
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0136
'var'이라는 지역 변수는 'var'에 다른 의미를 주기 때문에 이 범위에서 선언할 수 없습니다. 이 변수는 이미 'parent or current\/child' 범위에서 다른 의미를 나타내도록 사용되었습니다.  
  
 변수 선언이 그렇지 않을 경우 범위에 있을 다른 선언을 숨깁니다. CS0136을 생성한 줄에서 선언된 변수의 이름을 바꿉니다.  
  
## 예제  
 다음 샘플에서는 CS0136을 생성합니다.  
  
```  
// CS0136.cs  
namespace MyNamespace  
{  
   public class MyClass  
   {  
      public static void Main()  
      {  
         int i = 0;  
         {  
            char i = 'a';   // CS0136, hides int i  
         }  
         i++;  
      }  
   }  
}  
```  
  
 [C\# 언어 사양](/dotnet/csharp/language-reference/language-specification), 섹션 7.5.2.1에서:  
  
 지정된 식별자가 식 또는 선언자에서 지역 변수 선언 공간\(§3.3\) 안에 단순한 이름으로 발생할 때마다 식 또는 선언자의 단순한 이름과 동일한 식별자가 두 번 발생할 때 한 번씩은 동일한 엔터티를 참조해야 합니다. 이 규칙은 지정된 블록, 스위치 블록, for\-, foreach\- 또는 using\-문 또는 무명 함수 내에서 이름의 의미가 항상 같아야 합니다.