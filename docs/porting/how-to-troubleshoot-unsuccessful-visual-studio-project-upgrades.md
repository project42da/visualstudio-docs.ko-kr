---
title: "방법: 실패한 Visual Studio 프로젝트 업그레이드 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VisualStudio.SourceControl.CannotOpenFromSourceControlDSW"
  - "vs.UpgradeProjectSolution.8.0"
helpviewer_keywords: 
  - "응용 프로그램 업그레이드, Visual Studio"
  - "프로젝트 업그레이드[Visual Studio]"
  - "프로젝트[Visual Studio], 업그레이드"
  - "Visual Studio 변환 마법사"
  - "변환 마법사"
ms.assetid: 842fe448-c044-4343-8eae-d81711cf48ba
caps.latest.revision: 30
caps.handback.revision: 30
author: "TerryGLee"
ms.author: "tglee"
manager: "ghogen"
---
# 방법: 실패한 Visual Studio 프로젝트 업그레이드 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

때때로 Visual Studio는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 이전 버전에서 프로젝트를 완전히 변환 할 수 없습니다.  다음 섹션의 팁이 특정 문제를 해결하지 않으면, 더 많은 정보를 TechNet [Wiki: Development Portal](http://go.microsoft.com/fwlink/?LinkId=254808) 에서 찾을 수 있습니다.  
  
## 파일이 없기 때문에 프로젝트를 실행할 수 없습니다.  
 프로젝트 파일에는 F5 키를 누를 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 실행하는 데 사용되는 하드 코드된 파일 경로가 포함되어 있습니다.  이러한 경로에는 devenv.exe 및 기타 필수 파일의 위치가 들어 있습니다.  업그레이드 된 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서, 이러한 파일 경로가 변경 되었습니다.  
  
#### 잘못된 파일 경로를 해결하려면  
  
1.  텍스트 편집기에서 프로젝트 파일을 엽니다.  
  
2.  잘못된 파일 경로 특히 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전 번호가 포함된 파일 경로를 검색합니다.  
  
3.  새 대상을 가리키도록 잘못된 파일 경로를 수정합니다.  
  
## 참조가 유효하지 않기 때문에 프로젝트를 빌드할 수 없습니다.  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 업그레이드 하는 경우, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]버전으로 업그레이드 할 수 있습니다.  새 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]버전에서 지원되지 않는 참조가 프로젝트에 있을 경우 이러한 참조는 올바르게 해석되지 않을 수 있습니다.  이 문제는 특히 버전 번호가 포함된 참조\(예: `Microsoft.VisualStudio.Shell.Interop.8.0`\)에서 발생하기 쉽습니다.  
  
 코드에 잘못된 참조가 많은 경우에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 다중 대상 지정 기능을 사용하여 이전 버전의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 지정하면 가장 쉽게 문제를 해결할 수 있습니다.  
  
#### 잘못된 참조를 해결하려면  
  
1.  텍스트 편집기에서 프로젝트 파일을 엽니다.  
  
2.  프로젝트 속성을 엽니다.  
  
3.  올바른 **대상 프레임 워크** 값을 선택합니다.  대체적으로, `<TargetFrameworkVersion>` 요소의 값을 직접 프로젝트 파일에 수정할 수 있습니다.  
  
 업그레이드된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전에서 프로젝트를 실행하려면 프로젝트에 대한 참조뿐만 아니라 참조를 호출하는 `Imports` 또는 `Using` 문도 모두 업데이트해야 합니다.  IDE에서 프로젝트를 로드 하는 경우, **솔루션 탐색기** 또는 **관리자 참조** 대화 상자를 사용하여 참조를 업데이트 할 수 있습니다.  
  
## 참고 항목  
 [\/Upgrade](../ide/reference/upgrade-devenv-exe.md)   
 [Converting to ASP.NET 4](../Topic/Converting%20to%20ASP.NET%204.md)