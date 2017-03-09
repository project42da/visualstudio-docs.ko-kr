---
title: "The dependency &#39;file&#39; cannot be found | Microsoft Docs"
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
  - "vs.tasklisterror.supdepnotfound"
ms.assetid: a0e6e658-c723-40da-8275-fa212165bd7d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The dependency &#39;file&#39; cannot be found
프로젝트의 참조 중 하나가 찾을 수 없는 참조\(종속성\)를 포함합니다.  
  
 소스 코드의 제어를 받는 프로젝트에 참여하면 시스템의 일부 종속성이 확인되지 않습니다.  이는 참조 경로 속성이 시스템별 속성이어서 소스 코드의 제어를 받지 않기 때문입니다.  
  
### 이 오류를 해결하려면  
  
1.  표시된 어셈블리 참조를 디스크에서 찾은 다음 참조 경로 속성을 수정하십시오.  
  
2.  디스크에서 어셈블리 파일을 찾을 수 없으면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 설치하거나, 디스크에서 어셈블리의 종속성을 찾을 수 없는 경우 타사 사용자 지정 컨트롤을 다시 설치해야 합니다.  뿐만 아니라 소스 제어에서 사용 중인 프로젝트에 참여할 때는 프로젝트에 필요한 타사 컨트롤을 설치해야 합니다.  
  
 이 경우에도 프로젝트가 빌드되지만  응용 프로그램을 실행할 때 TypeLoadException이 발생합니다.  뿐만 아니라 해당 종속성이 배포 프로세스에 보고되지 않습니다.  
  
 솔루션 탐색기의 **참조** 노드에서 프로젝트의 참조를 볼 수 있습니다.  
  
## 참고 항목  
 [NIB: Reference Paths Dialog Box \(Visual Basic\)](http://msdn.microsoft.com/ko-kr/8e549b39-7256-456a-8fd7-089b23facf9c)