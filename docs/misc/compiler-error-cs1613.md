---
title: "컴파일러 오류 CS1613 | Microsoft Docs"
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
  - "CS1613"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1613"
ms.assetid: 9d7ea9c8-9953-459f-a3f0-c7e65d1b9f59
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1613
'interface' 인터페이스에 대해 관리되는 coclass 래퍼 클래스 'class'를 찾을 수 없습니다. 어셈블리 참조가 있는지 확인하세요.  
  
 인터페이스에서 COM 개체를 인스턴스화하려고 했습니다. 인터페이스에 **ComImport** 및 `CoClass` 특성이 있지만 컴파일러가 `CoClass` 특성에 대해 지정된 형식을 찾을 수 없습니다.  
  
 이 오류를 해결하려면 다음 중 하나를 시도할 수 있습니다.  
  
-   coclass가 있는 어셈블리에 대한 참조를 추가합니다\(대체로 인터페이스와 coclass는 동일한 어셈블리에 있어야 함\). 자세한 내용은 [\/reference](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option) 또는 [참조 추가 대화 상자](http://msdn.microsoft.com/ko-kr/2feb0fe2-0805-4cc9-8cba-b0315849dfb7)를 참조하세요.  
  
-   인터페이스의 `CoClass` 특성을 수정합니다.  
  
 다음 샘플에서는 **CoClassAttribute**의 올바른 사용법을 보여 줍니다.  
  
```  
// CS1613.cs using System; using System.Runtime.InteropServices; [Guid("1FFD7840-E82D-4268-875C-80A160C23296")] [ComImport()] [CoClass(typeof(A))] public interface IA{} public class A : IA {} public class AA { public static void Main() { IA i; i = new IA(); // This is equivalent to new A(). // because of the CoClass attribute on IA } }  
```