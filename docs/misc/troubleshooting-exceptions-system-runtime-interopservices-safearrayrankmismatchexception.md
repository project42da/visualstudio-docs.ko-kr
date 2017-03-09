---
title: "예외 문제 해결: System.Runtime.InteropServices.SafeArrayRankMismatchException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHSafeArrayRankMismatch"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "SafeArrayRankMismatchException 클래스"
ms.assetid: 6c69355c-8bfd-49bb-acad-b4d7236ae2e7
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Runtime.InteropServices.SafeArrayRankMismatchException
<xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> 예외는 들어오는 SAFEARRAY의 차수가 관리되는 시그니처에 지정된 차수와 일치하지 않는 경우에 throw됩니다.  
  
## 관련 팁  
 **배열의 차원이 올바른지 확인하세요.**  
 형식 라이브러리에서 안전 배열의 차수와 범위를 확인할 수 없으므로 차수는 1로, 하한은 0으로 가정됩니다.[Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)에서 생성하는 관리되는 서명에 차수와 범위를 정의해야 합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [배열에 대한 기본 마샬링](../Topic/Default%20Marshaling%20for%20Arrays.md)   
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)