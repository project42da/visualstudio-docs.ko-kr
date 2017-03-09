---
title: "컴파일러 오류 CS0423 | Microsoft Docs"
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
  - "CS0423"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0423"
ms.assetid: e4ec44b6-bf9c-41f7-a309-8f8b9e325691
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0423
'class'에 ComImport 특성이 있으므로 'method'는 extern 또는 abstract여야 합니다.  
  
 ComImport 특성을 지정하는 것은 COM 모듈에서 클래스에 대한 구현을 가져올 것을 의미합니다. 추가 메서드가 정의되지 않을 수 있습니다.  
  
 다음 샘플에서는 CS0423을 생성합니다.  
  
```  
// CS0423.cs using System.Runtime.InteropServices; [ ComImport, Guid("7ab770c7-0e23-4d7a-8aa2-19bfad479829") ] class ImageProperties { public static void Main()  // CS0423 { ImageProperties i = new ImageProperties(); } }  
```