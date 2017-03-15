---
title: "&#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 메서드에 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc31531"
  - "vbc31531"
helpviewer_keywords: 
  - "BC31531"
ms.assetid: 0ea3a16c-cfe0-4cb5-b740-358679272f8d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Runtime.InteropServices.DllImportAttribute&#39;는 &#39;AddHandler&#39;, &#39;RemoveHandler&#39; 또는 &#39;RaiseEvent&#39; 메서드에 적용할 수 없습니다.
`DllImportAttribute` 특성을 `AddHandler`, `RemoveHandler` 또는 `RaiseEvent` 메서드 선언에 적용했습니다. 이 특성은 빈 `Function` 또는 `Sub`에서만 사용할 수 있습니다.  
  
 **오류 ID:** BC31531  
  
### 이 오류를 해결하려면  
  
-   메서드 선언에서 `DllImportAttribute` 특성을 제거합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- 삭제](http://msdn.microsoft.com/ko-kr/35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [RaiseEvent \- 삭제](http://msdn.microsoft.com/ko-kr/7f765da0-5491-40b6-9ed5-24c98f9daad9)