---
title: 글꼴 및 색 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], font and color
- font and color control [Visual Studio SDK], editors
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8185d5c931ccf0b3b15fba10405cf050eb7c6241
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="font-and-color-overview"></a>글꼴 및 색 개요
이 항목의 텍스트 글꼴 및 색 설정에 설명 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE). 또한 범주 및 표시 항목의 개념을 소개 하 고 Vspackage 및 코어 편집기 텍스트 특성을 사용 방법에 대해 설명 합니다.  
  
## <a name="the-fonts-and-colors-property-page"></a>글꼴 및 색상 속성 페이지  
 에 표시 되는 텍스트의 특성을 관리할 수는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE)를 통해는 **글꼴 및 색** 속성 페이지. 찾을 **글꼴 및 색** 속성 페이지는 **도구** 메뉴를 클릭 **옵션**합니다. 확장 **환경**, 클릭 하 고 **글꼴 및 색**합니다.  
  
## <a name="categories-and-display-items"></a>범주 및 표시 항목  
 글꼴 및 색으로 구성 됩니다 **범주** 및 **표시 항목**합니다.  
  
-   A **범주** 의 수에 대 한 논리적 또는 기능적 컨테이너인 **표시 항목**합니다.  
  
     목록이 **범주** 에 **설정에 대 한 표시** 의 드롭다운 목록 상자는 **글꼴 및 색** 속성 페이지.  
  
-   A **표시 항목** 같은 주석, 문자열 또는 제어 되는 구조를 표시 하는 경우 색이 지정 하는 잘 정의 된 텍스트 엔터티입니다.  
  
 각 **표시 항목** 내에서 고유 하 게 정의 **범주** 해당 항목을 포함 합니다. 따라서 둘 이상의 **범주** 가질 수 있습니다는 **표시 항목** 동일한 이름을 가진입니다.  
  
## <a name="vspackage-control-of-fonts-and-colors"></a>글꼴 및 색의 VSPackage 제어  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Vspackage를 사용 하면:  
  
-   글꼴 및 색을 정의 **범주**합니다.  
  
-   글꼴 및 색 표시 하는 데 지정 **표시 항목**합니다.  
  
-   와 상호 작용은 **글꼴 및 색** 속성 페이지.  
  
-   집계 여러 **범주** 그룹으로 합니다.  
  
-   기본 설정에서의 변경 내용을 유지 합니다.  
  
 내의 글꼴 및 색 선택 항목와 상호 작용 하는 방법은 두 가지가 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]합니다.  
  
-   한 가지 방법은 라고 *구문 색 지정*합니다. 기존 사용자 지정 하는 VSPackage에서 사용 되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기 하는 언어 서비스를 구현 하 고 소스 편집기를 만듭니다.  
  
     하나의 **범주** 이 메커니즘을 즉 지원, **텍스트 편집기**합니다.  
  
-   다른 모든는 보다 일반적인 좋은 지원 **범주** 및 텍스트를 표시할 때 소스 편집기 이외의 사용자 인터페이스 구성 요소입니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>을 참조하세요.  
  
## <a name="core-editor-text-settings"></a>코어 편집기 텍스트 설정  
 언어 서비스 개체의 핵심 편집기에 대 한 글꼴 및 색 설정에 따라 관리 됩니다는 **텍스트 EditorCategory** 에 **설정에 대 한 표시** 의 드롭다운 목록 상자는 **글꼴 및 색** 속성 페이지.  
  
 특수 한 글꼴 및 색 제어 메커니즘을 제어 하 고 확장 하기 위해 언어 서비스 제공 하를 사용 해야 편집기를 사용할 때의 **텍스트 편집기** 설정 합니다. 메커니즘은 라고 *구문 색 지정* 제공:  
  
-   글꼴 및 색 표시 항목을 관리 하기 위한 간소화 된 기술입니다.  
  
     자세한 내용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem>를 참조하세요.  
  
-   잘 정의 하 고 최적화 된 색 지정 메커니즘입니다.  
  
     자세한 내용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>을 참조하세요.  
  
-   기본 제공 표시 항목을 사용 하는 둘 다 수의 **텍스트 EditorCategory** 및 확장 하 고 있습니다.  
  
     자세한 내용은 참조 [하는 방법: 기본 제공 색 항목을 사용 하 여](../extensibility/internals/how-to-use-built-in-colorable-items.md) 및 [사용자 지정 색 항목](../extensibility/internals/custom-colorable-items.md)합니다.  
  
-   현재 상태 모두 기본 제공 및 사용자 지정 자동 지 속성의 항목만 표시는 **텍스트 편집기** 범주입니다.  
  
 구문 색 참조에 대 한 자세한 내용은 [레거시 언어 서비스의 구문 색 지정](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [편집기에서 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)   
 [레거시 언어 서비스의 구문 색 지정](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)