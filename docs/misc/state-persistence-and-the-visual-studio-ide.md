---
title: "상태 지속성 및 Visual Studio IDE | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDE 설정, 상태 지속성"
  - "사용자 설정[Visual Studio SDK], 유지"
  - "도구 옵션 페이지[Visual Studio SDK], 설정 유지"
  - "IDE, 상태 지속성"
  - "지속성, 사용자 설정"
ms.assetid: fdd49bb1-ed3b-4428-b685-de65c3215c1c
caps.latest.revision: 24
caps.handback.revision: 24
manager: "douge"
---
# 상태 지속성 및 Visual Studio IDE
**가져오기\/내보내기 설정** 에 있는  **도구** 메뉴 통합된 개발 환경 \(IDE\)을 가져오고 사용자 지정을 내보내는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 Api에는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 하나 이상의 설정 범주 \(상태 변수 그룹\)는 사용자가 선택 하는 경우 저장할 수를 정의 하는 VSPackage 활성화는  **가져오기\/내보내기 설정** 명령을.  
  
 고유 각 설정 범주를 식별 하 라고 하는 고유한 레지스트리 항목에 정의 된 GUID는  *사용자 지정 설정을 포인트*.  
  
> [!NOTE]
>  표준 구현은  **도구옵션** 페이지는  **도구 상자**, 하는 `Microsoft.VisualStudio.Shell.DialogPage` 자동으로 지 속성에 대 한 지원을 제공 합니다.  Settings API 기본 메커니즘을 재정의할 수 있습니다.  자세한 내용은 [도구 상자 확장](../misc/extending-the-toolbox.md), [옵션 페이지](../misc/options-pages.md) 및 <xref:Microsoft.VisualStudio.Shell.DialogPage>을 참조하십시오.  
  
## 단원 내용  
 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)  
 레지스트리 설정 \(사용자 지정 설정 지점\) 및 특성을 지정 하는 데 사용에 대해 설명에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 주어진된 Vspackage에서 사용 되는 설정 구현 합니다.  
  
 [방법: Interop 어셈블리를 사용하여 설정 내보내기](../misc/how-to-export-settings-by-using-interop-assemblies.md)  
 사용 하 여 구성 데이터를 저장 하는 것에 대 한 지원을 구현 하는 방법에 대 한 자세한 설명을 제공의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackages interop 어셈블리에 대 한 설정 메커니즘을 기준으로 합니다.  
  
 [방법: Interop 어셈블리를 사용하여 설정 가져오기](../misc/how-to-use-interop-assemblies-to-import-settings.md)  
 사용 하 여 구성 데이터를 검색 하기 위한 지원을 구현 하는 방법에 대 한 자세한 설명을 제공의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackages interop 어셈블리에 대 한 설정 메커니즘을 기준으로 합니다.  
  
 [설정 내보내기](../misc/exporting-settings.md)  
 사용 하 여 구성 데이터를 저장 하는 것에 대 한 지원을 구현 하는 방법에 대 한 자세한 설명을 포함의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackages 설정 메커니즘을 관리 하는 패키지 프레임 워크를 기반으로 합니다.  
  
 [설정 가져오기](../misc/importing-settings.md)  
 사용 하 여 구성 데이터를 검색 하기 위한 지원을 구현 하는 방법에 대 한 자세한 설명을 제공의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackages 설정 메커니즘을 관리 하는 패키지 프레임 워크를 기반으로 합니다.  
  
## 관련 단원  
 [Working with Settings](http://msdn.microsoft.com/ko-kr/4c0a56ab-6091-4ebc-9dc7-52c40846bacb)  
 IDE의 내보내기\/가져오기 섹션을 관리 하는 방법에 설명 합니다.  
  
 [옵션 페이지](../misc/options-pages.md)  
 기술 지원에 설명 하는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 자동으로 기존의 또는 새로 만들기를 관리할 수 제공  **도구옵션** 페이지.  
  
 [도구 상자 확장](../misc/extending-the-toolbox.md)  
 기술 지원에 설명 하는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 관리 나 확장을 자동으로 제공는  **도구 상자**.  
  
 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)  
 사용자 기본 설정을 유지 하 여 Vspackage를 프로그래밍 하는 방법에 설명 합니다.