---
title: "컴파일러 오류 CS0738 | Microsoft Docs"
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
  - "CS0738"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0738"
ms.assetid: 01ce94ee-2435-4326-befc-2b020c441a4f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0738
'type name'은 'member name' 인터페이스 멤버를 구현하지 않습니다. 'method name'에 일치하는 반환 형식 'type name'이 없으므로 'interface member'를 구현할 수 없습니다.  
  
 클래스에서 구현 메서드의 반환 값은 구현하는 인터페이스 멤버의 반환 값과 일치해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  메서드의 반환 형식을 인터페이스 멤버의 반환 형식과 일치하도록 변경합니다.  
  
## 예제  
 다음 코드에서는 클래스 메서드가 `void`를 반환하고 동일한 이름의 인터페이스 멤버가 `int`를 반환하기 때문에 CS0738을 생성합니다.  
  
```  
using System; interface ITest { int TestMethod(); } public class Test: ITest { public void TestMethod() { } // CS0738 // Try the following line instead. // public int TestMethod(); }  
```  
  
## 참고 항목  
 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)