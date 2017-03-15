---
title: "컴파일러 오류 CS0434 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0434"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0434"
ms.assetid: 8f8871fc-a4bb-4a9e-ba19-999f4943001e
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0434
NamespaceName2의 NamespaceName1 네임스페이스가 NamespaceName3의 TypeName1 형식과 충돌합니다.  
  
 이 오류는 가져온 형식과 가져온 중첩된 네임스페이스의 정규화된 이름이 같을 때 발생합니다. 해당 이름이 참조되는 경우 컴파일러가 둘 사이를 구분할 수 없습니다. 가져온 소스 코드를 변경할 수 있는 경우 형식 또는 네임스페이스의 이름을 변경하여 해당 어셈블리 내에서 각각 고유하게 하면 이 오류를 해결할 수 있습니다.  
  
 다음 코드에서는 CS0434 오류를 생성합니다.  
  
## 예제  
 이 코드는 동일한 정규화된 이름을 사용하여 해당 형식의 첫 번째 복사본을 만듭니다.  
  
```  
// CS0434_1.cs // compile with: /t:library namespace TypeBindConflicts { namespace NsImpAggPubImp { public class X { } } }  
```  
  
## 예제  
 이 코드는 동일한 정규화된 이름을 사용하여 해당 형식의 두 번째 복사본을 만듭니다.  
  
```  
// CS0434_2.cs // compile with: /t:library namespace TypeBindConflicts { // Conflicts with another import (import2.cs). public class NsImpAggPubImp { } // Try this instead: // public class UniqueClassName { } }  
```  
  
## 예제  
 이 코드는 동일한 정규화된 이름을 사용하는 형식을 참조합니다.  
  
```  
// CS0434.cs // compile with: /r:cs0434_1.dll /r:cs0434_2.dll using TypeBindConflicts; public class Test { public TypeBindConflicts.NsImpAggPubImp.X n2 = null; // CS0434 }  
```