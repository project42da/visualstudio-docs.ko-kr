---
title: "컴파일러 경고(수준 2) CS1698 | Microsoft Docs"
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
  - "CS1698"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1698"
ms.assetid: 65cac5d0-e045-40f9-911c-1bf50e710b18
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1698
순환 어셈블리 참조 'AssemblyName1'이 출력 어셈블리 이름 'AssemblyName2'와 일치하지 않습니다. 출력 어셈블리 이름이 일치하도록 변경하거나 'AssemblyName1'에 대한 참조를 추가하세요.  
  
 CS1698은 어셈블리 참조가 잘못된 경우에 발생합니다. 참조된 어셈블리를 다시 컴파일할 경우 발생할 수 있습니다. 이 오류를 해결하려면 그 자체가 참조하는 어셈블리의 종속성인 어셈블리를 바꾸지 마세요.  
  
## 예제  
  
```  
// CS1698_a.cs // compile with: /target:library /keyfile:mykey.snk [assembly:System.Reflection.AssemblyVersion("2")] public class CS1698_a {}  
```  
  
## 예제  
  
```  
// CS1698_b.cs // compile with: /target:library /reference:CS1698_a.dll /keyfile:mykey.snk public class CS1698_b : CS1698_a {}  
```  
  
## 예제  
 다음 샘플에서는 CS1698을 생성합니다.  
  
```  
// CS1698_c.cs // compile with: /target:library /out:cs1698_a.dll /reference:cs1698_b.dll /keyfile:mykey.snk // CS1698 expected [assembly:System.Reflection.AssemblyVersion("3")] public class CS1698_c : CS1698_b {} public class CS1698_a {}  
  
```