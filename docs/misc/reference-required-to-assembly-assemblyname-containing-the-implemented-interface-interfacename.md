---
title: "구현된 &#39;&lt;interfacename&gt;&#39; 인터페이스를 포함하는 &#39;&lt;assemblyname&gt;&#39; 어셈블리에 대한 참조가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30009"
  - "bc30009"
helpviewer_keywords: 
  - "BC30009"
ms.assetid: b2dfb89d-7fde-4a8e-ba7f-fe1e59eabaca
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 구현된 &#39;&lt;interfacename&gt;&#39; 인터페이스를 포함하는 &#39;&lt;assemblyname&gt;&#39; 어셈블리에 대한 참조가 필요합니다.
구현된 '\<interfacename\>' 인터페이스를 포함하는 '\<assemblyname\>' 어셈블리에 대한 참조가 필요합니다. 하나를 프로젝트에 추가합니다.  
  
 인터페이스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL\(동적 연결 라이브러리\)에서 정의됩니다. 둘 이상의 DLL 또는 어셈블리에서 인터페이스가 정의된 경우 모호성을 방지하기 위해 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에 참조가 필요합니다.  
  
 **오류 ID:** BC30009  
  
### 이 오류를 해결하려면  
  
-   참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.  
  
## 참고 항목  
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)