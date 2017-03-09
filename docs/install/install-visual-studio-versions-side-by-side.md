---
title: "Visual Studio 버전 Side-by-Side 설치 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "side-by-side 설치[Visual Studio]"
  - "도움말[Visual Studio], 설치"
  - "Express Edition[Visual Studio]"
ms.assetid: 4d00f240-4910-4699-aaf3-cda6461f0c29
caps.latest.revision: 48
caps.handback.revision: 47
author: "TerryGLee"
ms.author: "tglee"
manager: "ghogen"
---
# Visual Studio 버전 Side-by-Side 설치
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이전 버전이 설치된 컴퓨터에 이 버전의 Visual Studio를 설치할 수 있습니다. 설치 오류가 발생할 경우 문제를 직접 디버그할 수 있도록 [로그 수집 도구](http://go.microsoft.com/fwlink/?LinkId=262077)를 사용하여 오류에 대한 정보를 수집할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전은 출시 순서대로 설치하는 것이 좋습니다. 예를 들어 Visual Studio 2015를 설치하기 전에 Visual Studio 2013을 설치합니다.  
  
 여러 버전을 함께 설치하기 전에 다음과 같은 조건을 검토해야 합니다.  
  
-   Visual Studio 2015를 사용하여 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]에서 만든 솔루션을 여는 경우 Visual Studio 2015 특정 기능을 구현하지 않았다면 나중에 이전 버전에서 다시 솔루션을 열어 수정할 수 있습니다.  
  
-   Visual Studio 2015를 사용하여 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)] 이전 버전에서 만든 솔루션을 열려면 Visual Studio 2015와 호환되도록 프로젝트와 파일을 수정해야 할 수 있습니다. 자세한 내용은 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)를 참조하세요.  
  
-   둘 이상의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전이 설치된 컴퓨터에서 한 버전을 제거할 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 파일 연결이 모든 버전에 대해 제거됩니다.**옵션** 대화 상자의 **환경**, **일반** 페이지에 있는 [파일 연결 복원](../ide/reference/general-environment-options-dialog-box.md) 단추를 사용하여 이 파일 연결을 다시 매핑할 수 있습니다.  
  
-   모든 확장이 호환되는 것은 아니므로 Visual Studio에서는 확장을 자동으로 업그레이드하지 않습니다.[Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkId=178891) 또는 소프트웨어 게시자에서 확장을 다시 설치해야 합니다.  
  
## .NET Framework 버전 및 Side\-by\-Side 설치  
  
-   Visual Basic, Visual C\# 및 Visual F\# 프로젝트에는 **프로젝트 디자이너**의 **대상 프레임워크** 옵션을 사용하여 프로젝트에 사용할 .NET Framework 버전을 지정합니다. C\+\+ 프로젝트의 경우 .vcxproj 파일을 수정하여 수동으로 대상 프레임워크를 변경할 수 있습니다. 자세한 내용은 [버전 호환성](../Topic/Version%20Compatibility%20in%20the%20.NET%20Framework.md)을 참조하세요.  
  
     프로젝트를 만들 때 **새 프로젝트** 대화 상자의 **.NET Framework** 목록에서 프로젝트 대상으로 사용할 .NET Framework 버전을 지정할 수 있습니다.  
  
     언어별 정보는 다음 테이블에서 해당 항목을 참조하세요.  
  
    |언어|항목|  
    |--------|--------|  
    |[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]|[프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](../ide/reference/application-page-project-designer-visual-basic.md)|  
    |Visual C\#|[프로젝트 디자이너, 응용 프로그램 페이지\(C\#\)](../ide/reference/application-page-project-designer-csharp.md)|  
    |Visual F\#|[프로젝트 구성](../Topic/Configuring%20Projects%20\(F%23\).md)|  
    |C\+\+|[방법: 대상 프레임워크 및 플랫폼 도구 집합 수정](../Topic/How%20to:%20Modify%20the%20Target%20Framework%20and%20Platform%20Toolset.md)|  
    |[!INCLUDE[jsprjscript](../debugger/debug-interface-access/includes/jsprjscript_md.md)]|[이전 버전의 공용 언어 런타임에서 JScript 응용 프로그램 실행](http://msdn.microsoft.com/ko-kr/bbea51b5-ac03-4e6c-b9a6-f487ef63eda5)|  
  
## 참고 항목  
 [Visual Studio 설치](../Topic/Installing%20Visual%20Studio%202015.md)   
 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)   
 [버전 호환성](../Topic/Version%20Compatibility%20in%20the%20.NET%20Framework.md)   
 [여러 언어 버전의 Visual Studio 설치](../Topic/Installing%20Multiple%20Language%20Versions%20of%20Visual%20Studio.md)   
 [C\/C\+\+ 격리된 응용 프로그램 및 side\-by\-side 어셈블리 빌드](/visual-cpp/build/building-c-cpp-isolated-applications-and-side-by-side-assemblies)   
 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)