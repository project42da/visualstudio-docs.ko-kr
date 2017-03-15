---
title: "&#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 인터페이스 메서드에 적용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31530"
  - "vbc31530"
helpviewer_keywords: 
  - "BC31530"
ms.assetid: e63f1f7d-b7df-4637-a0f4-2783479ca1af
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 인터페이스 메서드에 적용할 수 없습니다.
프로시저는 인터페이스 내에서 정의되지만 프로시저 정의는 <xref:System.Runtime.InteropServices.DllImportAttribute>를 적용합니다.  
  
 CLR\(공용 언어 런타임\)은 .NET Framework 외부의 관리되지 않는 DLL\(동적 연결 라이브러리\)에 정의된 대체 프로시저를 지정하면서 이 특성 및 해당 <xref:System.Runtime.InteropServices._Assembly.EntryPoint%2A> 속성을 인식합니다. 코드에서 <xref:System.Runtime.InteropServices.DllImportAttribute>가 적용되는 프로시저를 호출하는 경우 공용 언어 런타임에서 지정된 관리되지 않는 프로시저를 대신 호출합니다.  
  
 인터페이스 내의 프로시저 정의에는 구현이 없으므로 .NET Framework 외부의 관리되지 않는 플랫폼과 상호 작용할 수 없습니다.  
  
 **오류 ID:** BC31530  
  
### 이 오류를 해결하려면  
  
-   이 프로시저의 정의에서 <xref:System.Runtime.InteropServices.DllImportAttribute>를 제거합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)