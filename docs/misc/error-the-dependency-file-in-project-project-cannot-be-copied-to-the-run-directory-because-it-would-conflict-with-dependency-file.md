---
title: "오류: &#39;project&#39; 프로젝트의 &#39;file&#39; 종속성이 &#39;file&#39; 종속성과 충돌하므로 실행 디렉터리에 종속성을 복사할 수 없습니다. | Microsoft Docs"
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
  - "vs.tasklisterror.copy_version_conflict"
ms.assetid: cd7de1eb-7d58-4e2c-9811-a7201f7817be
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 오류: &#39;project&#39; 프로젝트의 &#39;file&#39; 종속성이 &#39;file&#39; 종속성과 충돌하므로 실행 디렉터리에 종속성을 복사할 수 없습니다.
참조 간에 충돌이 존재합니다. 즉, 실행할 응용 프로그램의 bin 디렉터리에 파일 이름이 같은 둘 이상의 고유 종속성을 복사하려고 했습니다. 종속성이 모두 기본 참조가 아니므로 실행 디렉터리에서 충돌을 해결할 수 없습니다.  
  
 이 오류가 발생하면 빌드는 실패합니다.  
  
 작업 목록 항목을 두 번 클릭하여 충돌이 발생한 프로젝트의 참조 노드로 이동하세요.  
  
 **이 오류를 해결하려면**  
  
-   어셈블리 중 하나를 프로젝트의 직접 참조로 만듭니다. 단, 이 방법을 사용하면 선택한 어셈블리가 다른 버전의 참조된 어셈블리를 사용하는 어셈블리와 작동하지 않을 수 있습니다.  
  
     또는  
  
-   어셈블리의 두 복사본을 모두 강력한 이름으로 지정하고 전역 어셈블리 캐시에 둡니다. 이렇게 하면 어셈블리를 bin 디렉터리에 복사하지 않아도 됩니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [전역 어셈블리 캐시](../Topic/Global%20Assembly%20Cache.md)   
 [강력한 이름의 어셈블리](../Topic/Strong-Named%20Assemblies.md)   
 [어셈블리 버전 관리](../Topic/Assembly%20Versioning.md)   
 [방법: 프로젝트 종속성 만들기 및 제거](../ide/how-to-create-and-remove-project-dependencies.md)