---
title: "상태 지속성 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "상태 지속성, 관리 패키지 프레임워크 지원"
  - "관리 패키지 프레임워크, 상태 지속성 지원"
  - "상태, 지속성"
ms.assetid: d25866f2-8d1f-477f-8aa5-3af3fbbf6e97
caps.latest.revision: 15
caps.handback.revision: 15
manager: "douge"
---
# 상태 지속성 지원
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]공용 개체의 상태를 유지할 수 있습니다.  예를 들어, 프로젝트 속성 이며 저장 솔루션 및 프로젝트 파일에서 복원 했습니다.  사용자 설정에 내보낸 후 설정 파일에서 가져온 수 있습니다.  
  
 일반적으로 VSPackages 시스템 레지스트리 또는 응용 프로그램 데이터 폴더에 현재 사용자 또는 컴퓨터에 대 한 로컬 저장소를 사용합니다.  정수나 문자열 같은 저장소에 대 한 약간의 공간을 필요로 하는 값은 일반적으로 시스템 레지스트리에 저장 됩니다.  비트맵 같은 저장소에 대 한 많은 공간을 필요로 하는 값을 파일에 저장 됩니다.  파일의 경로 시스템 레지스트리에 자신을 저장할 수 있습니다.  지 속성 메커니즘은 로컬 저장소에 액세스할 수 있는 권한이 있어야 합니다.  
  
## 로컬 저장소 위치에 대 한 지원  
 <xref:Microsoft.VisualStudio.Shell.Package> 클래스는 현재 사용자 또는 컴퓨터에 대 한 시스템 레지스트리 또는 응용 프로그램 데이터 폴더에 상태 정보를 찾는 데 지원을 제공 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>  
 에 대 한 로컬 컴퓨터의 레지스트리 루트의 경로 반환 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 예를 들어, HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\VisualStudio\\8.0Exp.  
  
 로컬 레지스트리 루트에서 얻은 것은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> 서비스 합니다.  사용할 수 없는 경우 가져온 된는 <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute> 있는 Vspackage의 특성입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>  
 현재 사용자 \(컴퓨터별\)의 경로 반환 레지스트리 루트를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 예를 들어, HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0Exp.  
  
 로컬 레지스트리 루트에서 얻은 것은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell> 서비스 합니다.  사용할 수 없는 경우이 VSPackage DefaultLocalRegistryRoot 특성에서 생성 됩니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserDataPath%2A>  
 에 대 한 공용 리포지토리로 사용 되는 디렉터리의 경로 반환 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 현재 로밍 사용자, 예를 들어, 단추로 데이터*YourAccountName*\\Application Data\\Microsoft\\VisualStudio\\8.0Exp.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.UserLocalDataPath%2A>  
 에 대 한 공용 리포지토리로 사용 되는 디렉터리의 경로 반환 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 현재 로밍하지 않은 사용자, 예를 들어, 단추로 데이터*YourAccountName*\\Local Settings\\Application Data\\Microsoft\\VisualStudio\\8.0Exp.  
  
## 참고 항목  
 [VSPackage 상태](../misc/vspackage-state.md)