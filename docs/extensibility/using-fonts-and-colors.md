---
title: 글꼴 및 색을 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- fonts, controlling in IDE
- IDE, controlling text color and fonts
- Fonts and Colors property page
- font and color control [Visual Studio SDK]
- text, IDE
ms.assetid: d1a9b99f-fbdc-45ed-920a-e08c3d931ac9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4415d00e5a1233bfdf14dbc86a3a7ed2f7b8e770
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="using-fonts-and-colors"></a>글꼴 및 색을 사용 하 여
[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 글꼴 및 색을 사용 하 여 텍스트를 표시 하는 것에 대 한 지원을 제공 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [글꼴 및 색 개요](../extensibility/font-and-color-overview.md)  
 텍스트 글꼴 및 색 설정에 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE). 또한 범주 및 표시 항목의 개념을 소개 하 고 Vspackage 및 코어 편집기 텍스트 특성을 사용 하는 방법을 설명 합니다.  
  
 [글꼴 및 텍스트 색 지정에 대 한 색상 정보 가져오기](../extensibility/getting-font-and-color-information-for-text-colorization.md)  
 텍스트 색 지정을 관리 하는 Vspackage에서 구현 하기 위한 지침을 제공 **범주** 이외의 **텍스트 편집기**합니다.  
  
 [저장 된 글꼴 및 색 설정에 액세스](../extensibility/accessing-stored-font-and-color-settings.md)  
 방법을 현재 글꼴 및 색에 설명 설정을 저장, 검색 및 적용할 수 있습니다.  
  
 [사용자 지정 범주를 구현 하는 항목 표시](../extensibility/implementing-custom-categories-and-display-items.md)  
 기준인 창을 만들고 사용할 수 있는 자체의 기본 단계를 설명 **항목 표시** 및 **범주** 텍스트 표시를 지원 하도록 합니다.  
  
 이 접근 방식에서는 구현 하는 VSPackage는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> 인터페이스 및 관련된 인터페이스입니다.  
  
 [방법: 기본 제공 글꼴 및 색 구성표에 액세스](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)  
 정의 하 고, 기본 제공 글꼴 및 색을 사용 하 여 범주를 등록 하 고 시스템에서 제공한 글꼴 및 색의 사용을 시작 하는 방법에 설명 합니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>  
 인스턴스를 제공 된 `IVsFontAndColorDefaults` 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup> 에 나열 된 특정 항목에 해당 하는 인터페이스는 **표시 설정에 대 한** 목록에 **글꼴 및 색** 는 의페이지**옵션** 대화 상자.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>  
 IDE를 지원 하기 위해 VSPackage를 사용 하면 **글꼴 및 색** 기본 글꼴 및 색을 창이 나 UI 구성 요소를 정의 하 여 페이지입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>  
 메커니즘을 제공 글꼴 및 색 지원 디스플레이 항목 그룹-두 개 이상의 범주의 합집합을 나타내는 상위 범주를 지정할 수를 제공 하는 VSPackage입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>  
 VSPackage를 글꼴 및 색 데이터를 검색 하거나을 레지스트리에 저장할 수 있습니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>  
 글꼴 및 색 설정의 변경 내용에 대 한 글꼴 및 색 정보를 사용 하는 Vspackage를에 알립니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities>  
 입력 및 출력 데이터의 메서드에 의해 사용 되는 작업을 위한 도구를 제공 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **글꼴 및 색** 메커니즘입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager>  
 글꼴 및 색 설정의 캐시 제어 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [레거시 언어 서비스 개발](../extensibility/internals/developing-a-legacy-language-service.md)  
 Vspackage 언어 서비스를 사용 하 여 사용자 지정 하는 방법에 대해 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기입니다.  
  
 [사용자 지정 편집기의 구문 색 지정](../extensibility/syntax-coloring-in-custom-editors.md)  
 Descries 방법을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기 언어 서비스를 사용 하 여 구문 색 지정을 구현 합니다.  
  
 [Visual Studio의 다른 부분 확장](../extensibility/extending-other-parts-of-visual-studio.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 의 나머지와 일치 하는 UI 요소를 만드는 서비스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.