---
title: "글꼴 및 색상 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK], 글꼴 및 색"
  - "글꼴 및 색 컨트롤 [Visual Studio SDK] 편집기"
ms.assetid: 2203e4e7-8b7f-44ec-8884-6ff718d4f278
caps.latest.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 22
---
# 글꼴 및 색상 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 텍스트 글꼴 및 색 설정에 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)입니다.  또한 범주 및 표시 항목의 개념에 소개 하 고 VSPackages 코어 편집기 텍스트 특성 사용 하는 방법에 대해 설명 합니다.  
  
## 글꼴 및 색 속성 페이지  
 에 표시 되는 텍스트의 특성을 관리할 수는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\) 통해는  **글꼴 및 색** 속성 페이지.  찾을 수 있는  **글꼴 및 색** 속성 페이지에  **도구** 메뉴를 클릭  **옵션**.  **환경**을 확장한 다음 **글꼴 및 색**을 클릭합니다.  
  
## 범주 및 항목 표시  
 글꼴 및 색으로 구성  **범주** 및  **표시 항목**.  
  
-   A  **범주** 여러 논리 또는 기능적 컨테이너입니다  **표시 항목**.  
  
     목록을  **범주** 되는  **설정 표시** 의 드롭다운 상자를  **글꼴 및 색** 속성 페이지.  
  
-   A  **디스플레이 항목** 는 잘 정의 된 텍스트 주석, 문자열, 또는 표시 때 조정 하 게 하는 것을 제어 구조와 같은 엔터티입니다.  
  
 각  **디스플레이 항목** 고유 하 게 정의 되어 있는  **범주** 포함 된.  따라서 둘 이상의  **범주** 가질 수는  **디스플레이 항목** 같은 이름을 가진.  
  
## VSPackage 컨트롤의 글꼴 및 색  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Vspackages에 있습니다.  
  
-   글꼴 및 색상 정의  **범주**.  
  
-   글꼴 및 색을 표시 하는 데 지정  **표시 항목**.  
  
-   상호 작용은  **글꼴 및 색** 속성 페이지입니다.  
  
-   집계 여러  **범주** 그룹에 있습니다.  
  
-   기본 설정의 변경 내용을 유지 합니다.  
  
 글꼴 및 색 선택 영역 내에서 상호 작용 하는 두 가지는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)].  
  
-   한 가지 방법은 라  *구문 색 지정*.  기존 사용자 지정 있는 Vspackage에서 사용 되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기 언어 서비스를 구현 하 고 원본 편집기를 만듭니다.  
  
     하나의  **범주** 즉이 메커니즘을 지 원하는, 해당  **텍스트 편집기**.  
  
-   다른 모든 일반적인 대안을 지 원하는  **범주** 및 제외 텍스트를 표시할 때 원본 편집기 사용자 인터페이스 구성 요소입니다.  자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>를 참조하십시오.  
  
## 코어 편집기 텍스트 설정  
 의해 코어 편집기의 언어 서비스 개체에 대 한 글꼴 및 색 설정을 제어는  **텍스트 편집기범주** 에서 찾을 수는  **설정 표시** 의 드롭다운 상자를  **글꼴 및 색** 속성 페이지.  
  
 편집기에서 작업 하는 경우 특수 한 글꼴 및 언어 서비스를 제어 하 고 확장할 수 있습니다 색상 제어 메커니즘을 사용 해야 해당  **텍스트 편집기** 설정 합니다.  메커니즘 이라고  *구문 색 지정* 제공 합니다.  
  
-   글꼴 및 표시 항목의 색을 관리 하기 위한 간단한 기술입니다.  
  
     자세한 내용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem>을 참조하십시오.  
  
-   잘 정의 되 고 최적화 된 색 처리 메커니즘입니다.  
  
     자세한 내용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>를 참조하십시오.  
  
-   기능을 모두 내장 디스플레이 항목을 사용 하는  **텍스트 편집기범주** 를 확장 하 고.  
  
     자세한 내용은 [방법: 기본 제공 색 항목을 사용 하 여](../extensibility/internals/how-to-use-built-in-colorable-items.md) 및 [사용자 지정 색 항목](../extensibility/internals/custom-colorable-items.md)을 참조하십시오.  
  
-   자동 지 속성의 현재 상태에 기본 제공 되는 정보와 사용자 지정 표시 항목에는  **텍스트 편집기** 범주입니다.  
  
 구문 색 참조에 대 한 자세한 내용은 [구문 레거시 언어 서비스에 색 지정](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md).  
  
## 참고 항목  
 [편집기에서 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)   
 [구문 레거시 언어 서비스에 색 지정](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)