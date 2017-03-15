---
title: "dependency2&#39; 종속성의 &#39;dependency1&#39; 종속성은 어셈블리가 아닙니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.notcomplusassembly2"
ms.assetid: e3b96601-458e-40de-81ea-ddcae9b42996
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# dependency2&#39; 종속성의 &#39;dependency1&#39; 종속성은 어셈블리가 아닙니다.
프로젝트 시스템에서 어셈블리\(dependency2\)의 특정 종속성\(dependency1\)이 .NET 어셈블리가 아님을 확인했습니다.  
  
 **이 오류를 해결하려면**  
  
-   어셈블리가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 또는.NET Framework에서 제공된 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 설치합니다.  
  
     또는  
  
-   적절한 타사 컨트롤을 다시 설치하세요.  
  
     이 오류가 발생해도 프로젝트는 빌드됩니다. 그러나 런타임 오류가 발생할 수 있습니다.  
  
## 참고 항목  
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Assemblies in the Common Language Runtime](http://msdn.microsoft.com/ko-kr/33a0bc6a-6bb3-44c7-ada7-4a046e8c0945)