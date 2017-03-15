---
title: "글꼴 및 색을 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "글꼴, IDE에서 제어"
  - "IDE에서 텍스트 색 및 글꼴을 제어 합니다."
  - "글꼴 및 색 속성 페이지"
  - "글꼴 및 색 컨트롤 [Visual Studio SDK]"
  - "텍스트, IDE"
ms.assetid: d1a9b99f-fbdc-45ed-920a-e08c3d931ac9
caps.latest.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 27
---
# 글꼴 및 색을 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 텍스트를 표시 하려면 글꼴 및 색을 사용 하는 대 한 지원을 제공 합니다.  
  
## 단원 내용  
 [글꼴 및 색상 개요](../extensibility/font-and-color-overview.md)  
 텍스트 글꼴 및 색 설정에 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)입니다.  또한 범주 및 표시 항목의 개념을 소개 하 고 VSPackages 코어 편집기 텍스트 특성 사용 하는 방법에 대해 설명 합니다.  
  
 [글꼴 및 텍스트 색 지정에 대 한 색 정보 가져오기](../extensibility/getting-font-and-color-information-for-text-colorization.md)  
 텍스트 색 지정 관리 Vspackages에 구현 하기 위한 지침을 제공 합니다.  **범주** 이외의 다른  **텍스트 편집기**.  
  
 [저장 된 글꼴 및 색상 설정에 액세스](../extensibility/accessing-stored-font-and-color-settings.md)  
 설명 하는 방법 현재 글꼴 및 색 설정을 저장, 검색, 및 적용할 수 있습니다.  
  
 [사용자 지정 범주를 구현 하는 항목 표시](../extensibility/implementing-custom-categories-and-display-items.md)  
 창에서 작성 하 고 자체의 사용 하는 기본 단계에 설명 합니다  **표시할 항목** 및  **범주** 텍스트 표시 지원 하 고 있습니다.  
  
 이 방법을 구현할 수 있는 VSPackage 필요는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> 인터페이스와 관련 된 인터페이스입니다.  
  
 [방법: 기본 글꼴 및 색 구성표에 액세스](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)  
 정의 하 고 기본 글꼴 및 색을 사용 하 여 범주를 등록 하 고 시스템에서 제공 하는 글꼴 및 색의 사용을 시작 하는 방법을 설명 합니다.  
  
## 참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>  
 인스턴스를 제공는 `IVsFontAndColorDefaults` 나는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> 나열 된 특정 항목에 해당 하는 인터페이스는  **설정 표시를** 에 나열를  **글꼴 및 색** 의 페이지는  **옵션** 대화 상자.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>  
 IDE를 지원할 수 있는 VSPackage 있습니다  **글꼴 및 색** 페이지를 기본 글꼴 및 색 창 UI 구성 요소를 정의 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>  
 여 수 표시 항목 그룹\-공용 구조체의 두 개 이상의 범주를 나타내는 있는 super\-category 지원 글꼴 및 색을 지정할 수 있습니다 제공 된 VSPackage.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>  
 있는 Vspackage를 데이터, 글꼴 및 색을 검색 하거나 레지스트리에 저장할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>  
 글꼴 및 색상 정보를 변경 하는 방법에 대 한 글꼴 및 색 설정에 사용 하 고 있는 Vspackages에 알립니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities>  
 메서드를 통해 사용 되는 입력 및 출력 데이터 작업에 대 한 도구 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]**글꼴 및 색** 메커니즘입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager>  
 글꼴 및 색 설정의 캐싱을 제어 합니다.  
  
## 관련 단원  
 [언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)  
 VSPackages 언어 서비스에 사용자 지정 사용 하는 방법에 대해 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기입니다.  
  
 [사용자 지정 편집기에서 색을 지정 하는 구문](../extensibility/syntax-coloring-in-custom-editors.md)  
 Descries은 어떻게 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기 언어 서비스를 사용 하 여 구문 색상 표시를 구현 합니다.  
  
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 의 나머지 부분과 일치 하는 UI 요소를 만들 수 있는 서비스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].