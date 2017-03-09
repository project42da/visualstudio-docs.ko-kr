---
title: "컴파일러 경고(수준 1) CS1684 | Microsoft Docs"
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
  - "CS1684"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1684"
ms.assetid: 620419bf-b6d5-4cda-a549-fcacf2f08920
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1684
'Type Name' 형식에 대한 참조는 'Namespace'에 정의된 것으로 되어 있지만 찾을 수 없습니다.  
  
 이 오류는 두 번째 네임스페이스 안에 있다고 하는데 실제로는 없는 형식을 참조하는 하나의 네임스페이스 안의 참조로 인해 발생할 수 있습니다. 예를 들어 mydll.dll에서는 `A` 형식이 yourdll.dll 안에 있다고 하는데 그러한 형식이 yourdll.dll 안에 없습니다. 이 오류가 발생하는 한 가지 가능한 원인은 사용 중인 yourdll.dll의 버전이 너무 오래되고 `A`가 아직 정의되지 않았기 때문입니다.  
  
 다음 샘플에서는 CS1684를 생성합니다.  
  
## 예제  
  
```  
// CS1684_a.cs // compile with: /target:library /keyfile:CS1684.key public class A { public void Test() {} } public class C2 {}  
```  
  
## 예제  
  
```  
// CS1684_b.cs // compile with: /target:library /r:cs1684_a.dll // post-build command: del /f CS1684_a.dll using System; public class Ref { public static A GetA() { return new A(); } public static C2 GetC() { return new C2(); } }  
```  
  
## 예제  
 이제 첫 번째 어셈블리를 다시 빌드하고 다시 컴파일할 때 정의되지 않도록 클래스 C2의 정의를 제외합니다.  
  
```  
// CS1684_c.cs // compile with: /target:library /keyfile:CS1684.key /out:CS1684_a.dll public class A { public void Test() {} }  
```  
  
## 예제  
 이 모듈은 `Ref` 식별자를 통해 두 번째 모듈을 참조합니다. 하지만 두 번째 모듈에는 이전 단계의 컴파일 때문에 더 이상 존재하지 않는 `C2` 클래스에 대한 참조가 포함되어 있기 때문에 CS1684 오류 메시지가 이 모듈의 컴파일에서 반환됩니다.  
  
```  
// CS1684_d.cs // compile with: /reference:cs1684_a.dll /reference:cs1684_b.dll // CS1684 expected class Tester { public static void Main() { Ref.GetA().Test(); } }  
```