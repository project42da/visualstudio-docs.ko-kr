---
title: "&#39;assembly&#39;가 다중 파일 어셈블리인지 확인할 수 없습니다. 어셈블리 매니페스트가 손상되었을 수 있습니다. 다중 파일 어셈블리가 아닌 것으로 간주합니다. | Microsoft Docs"
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
  - "vs.tasklisterror.unknownscatterstatusforcopy"
ms.assetid: be49d3f2-b091-488c-8579-e27ef09d9c80
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# &#39;assembly&#39;가 다중 파일 어셈블리인지 확인할 수 없습니다. 어셈블리 매니페스트가 손상되었을 수 있습니다. 다중 파일 어셈블리가 아닌 것으로 간주합니다.
프로젝트 시스템에서는 프로젝트가 참조하는 어셈블리를 읽을 수 없으므로 다중 파일 어셈블리를 참조하는지 여부를 확인할 수 없습니다. 따라서 어셈블리가 출력 디렉터리에 제대로 복사되지 않을 수 있습니다.  
  
 **이 오류를 해결하려면**  
  
-   어셈블리가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 또는.NET Framework에서 제공된 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 설치합니다.  
  
     또는  
  
-   적절한 타사 컨트롤을 다시 설치하세요.  
  
     이 오류가 발생해도 프로젝트는 빌드됩니다. 그러나 런타임 오류가 발생할 수 있습니다.  
  
## 참고 항목  
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [Assemblies in the Common Language Runtime](http://msdn.microsoft.com/ko-kr/33a0bc6a-6bb3-44c7-ada7-4a046e8c0945)