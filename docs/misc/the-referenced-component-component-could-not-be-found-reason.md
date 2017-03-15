---
title: "The referenced component &#39;component&#39; could not be found. &lt;reason&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.referencenotfound"
ms.assetid: 35491b4d-e3e4-4e7c-8ac1-3adb09c1ef58
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The referenced component &#39;component&#39; could not be found. &lt;reason&gt;
프로젝트 시스템에서 특정 참조를 확인할 수 없습니다.  작업 목록 항목을 두 번 클릭하면 솔루션 탐색기에 포커스가 설정되고 확인할 수 없는 참조가 선택됩니다.  
  
 [ReferencePaths](http://msdn.microsoft.com/ko-kr/8e549b39-7256-456a-8fd7-089b23facf9c) 속성을 편집하여 경로에 해당 디렉터리가 포함되도록 하십시오.  
  
 이 오류는 프로젝트를 다른 시스템으로 옮겼을 때 발생할 수 있습니다.  `ReferencePath` 속성은 절대 경로로 저장됩니다.  참조 R1이 A 컴퓨터의 c:\\R\\R1.dll에 있으면 .vbproj.user나 .csproj.user 파일에 c:\\R을 `ReferencePath` 속성의 일부로 저장해야 합니다.  그러나 B 시스템에서 R1이 d:\\R\\R1.dll에 있으면 d:\\R이 참조 경로에 있지 않으므로 프로젝트 시스템에서 R1을 찾을 수 없습니다.  
  
 이와 비슷한 시나리오는 소스 코드 제어 시나리오입니다.  프로젝트에 참여하면 .vbproj.user 또는 .csproj.user 파일이 소스 제어에 저장되어 있지 않기 때문에 사용자 시스템에 복사되지 않습니다.  따라서 `ReferencePath` 속성의 초기 값이 비게 되고, `ReferencePath` 속성을 사용하여 확인하는 모든 참조를 확인할 수 없게 됩니다.  자세한 내용은 *Visual Studio .NET 및 Visual SourceSafe를 사용한 팀 개발*의 "종속성 관리"를 참조하십시오.  
  
 참조된 프로젝트가 현재 솔루션에 없을 때도 이 오류가 발생할 수 있습니다.  
  
 이 오류가 발생하면 프로젝트는 빌드되지 않습니다.  
  
 어셈블리 참조 확인에 대한 자세한 내용은 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)을 참조하십시오.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)