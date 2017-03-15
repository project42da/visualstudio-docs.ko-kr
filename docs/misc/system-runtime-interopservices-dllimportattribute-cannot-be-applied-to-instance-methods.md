---
title: "&#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 인스턴스 메서드에 적용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31529"
  - "bc31529"
helpviewer_keywords: 
  - "BC31529"
ms.assetid: c8bde5d7-c6bf-4d21-bb1a-e8627d65ad29
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 인스턴스 메서드에 적용할 수 없습니다.
공유되지 않는 프로시저가 <xref:System.Runtime.InteropServices.DllImportAttribute>로 선언되었습니다.  
  
 CLR\(공용 언어 런타임\)은 .NET Framework 외부의 관리되지 않는 DLL\(동적 연결 라이브러리\)에 정의된 대체 프로시저를 지정하면서 이 특성 및 해당 <xref:System.Runtime.InteropServices._Assembly.EntryPoint%2A> 속성을 인식합니다. 코드에서 <xref:System.Runtime.InteropServices.DllImportAttribute>가 적용되는 프로시저를 호출하는 경우 공용 언어 런타임에서 지정된 관리되지 않는 프로시저를 대신 호출합니다.  
  
 .NET Framework 외부의 관리되지 않는 플랫폼은 .NET Framework와 동일한 방식으로 비공유 프로시저를 지원하지 않으므로 비공유 프로시저를 사용하여 상호 운용할 수 없습니다.  
  
 **오류 ID:** BC31529  
  
### 이 오류를 해결하려면  
  
-   프로시저가 해당 클래스 또는 구조체의 각 인스턴스에 개별적으로 적용할 필요가 없는 경우 `Shared`로 선언합니다.  
  
-   프로시저가 `Shared`일 수 없는 경우 이 프로시저의 선언에서 <xref:System.Runtime.InteropServices.DllImportAttribute>를 제거합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)