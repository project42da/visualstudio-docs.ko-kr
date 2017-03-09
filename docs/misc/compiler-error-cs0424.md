---
title: "컴파일러 오류 CS0424 | Microsoft Docs"
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
  - "CS0424"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0424"
ms.assetid: 09ae482c-255a-4f99-8dc8-ba31c3ea8c71
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0424
'class': ComImport 특성이 있는 클래스는 기본 클래스를 지정할 수 없습니다.  
  
 <xref:System.Runtime.InteropServices.ComImportAttribute> 특성을 지정하는 것은 COM 모듈에서 클래스에 대한 구현을 가져올 것을 의미합니다. 기본 클래스에서 상속된 추가 메서드 또는 필드는 COM 모듈에 정의된 구현에 추가할 수 없습니다.  
  
 다음 샘플에서는 CS0424를 생성합니다.  
  
```  
// CS0424.cs // compile with: /target:library using System.Runtime.InteropServices; public class A {} [ ComImport, Guid("7ab770c7-0e23-4d7a-8aa2-19bfad479829") ] class B : A {}   // CS0424 error  
```