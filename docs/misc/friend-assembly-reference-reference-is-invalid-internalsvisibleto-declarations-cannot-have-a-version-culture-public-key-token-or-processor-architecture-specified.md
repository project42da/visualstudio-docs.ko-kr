---
title: "Friend 어셈블리 참조 &lt;reference&gt;가 잘못되었습니다. InternalsVisibleTo 선언에는 버전, 문화권, 공개 키 토큰 또는 프로세서 아키텍처를 지정할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31534"
  - "vbc31534"
helpviewer_keywords: 
  - "BC31534"
ms.assetid: ae1e470e-3105-48f2-87b1-466e395a7d44
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Friend 어셈블리 참조 &lt;reference&gt;가 잘못되었습니다. InternalsVisibleTo 선언에는 버전, 문화권, 공개 키 토큰 또는 프로세서 아키텍처를 지정할 수 없습니다.
<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에 전달된 어셈블리 이름에는 `Version`, `Culture`, `PublicKeyToken` 또는 `processorArchitecture` 특성이 있습니다.  
  
 **오류 ID:** BC31534  
  
### 이 오류를 해결하려면  
  
1.  <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에 전달된 어셈블리 이름에서 `Version`, `Culture`, `PublicKeyToken` 또는 `processorArchitecture` 특성을 제거합니다.  
  
## 참고 항목  
 <xref:System.Reflection.AssemblyName>   
 [빌드에 없음: Friend 어셈블리\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/80e7a33a-ca91-450b-a00e-c5a7986e228c)