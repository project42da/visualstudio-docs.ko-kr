---
title: "속성 확장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window, providing support
ms.assetid: 68e2cbd4-861c-453f-8c9f-4ab6afc80e67
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5c47295c1906c6517638bdf8e9c3a55897f38aa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="extending-properties"></a>속성 확장
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **속성** 창은 COM 및 COM + 구성 요소에 대 한 유니버설 속성 브라우저 이며 모든 지원 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 제품입니다. **속성** 창이 연동 `ITypeInfo` 정보 및 COM + 통합된 개발 환경 (IDE)에서 다른 창에 현재 선택 된 개체에 대 한 디자인 타임 속성을 나열할 메타 데이터를 입력 합니다.  
  
 **속성** F4 키를 눌러 키보드에서 또는 선택 하 여 열 수 있는 창을 **속성 창** 에 **보기** 메뉴는 보기 및 편집 하는 데 사용 됩니다 구성에 관계 없이, 디자인 타임 속성 및 선택한 개체의 이벤트입니다. 솔루션 및 프로젝트와 관련 된 구성에 종속 된 속성에 표시 됩니다 [속성 페이지](../../extensibility/internals/property-pages.md)합니다. 자세한 내용은 참조 [NIB: 프로젝트 속성](http://msdn.microsoft.com/en-us/fb126574-24ad-4c96-9b2b-6e1f3879ba50), [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md), 및 [프로젝트의 NIB: 항목 관리](http://msdn.microsoft.com/en-us/762e606b-7f44-4b66-97a1-e30a703654a0)합니다.  
  
 ![속성 창 개요](../../extensibility/internals/media/vspropertieswindow.png "vsPropertiesWindow")  
속성 창  
  
 이 섹션의 개별 영역에 관련 된 자세한 정보를 제공 된 **속성** 창 및 구현 해야 하는 인터페이스 및 창을 채울를 호출 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [속성 창 개요](../../extensibility/internals/properties-window-overview.md)  
 용도 설명는 **속성** 도구 창과 문서 창에 상대적인 창의 합니다.  
  
 [템플릿 정책 및 속성 창](../../extensibility/internals/template-policy-and-the-properties-window.md)  
 엔터프라이즈 템플릿 프로젝트에 해당 정책을 적용할 수 있습니다 어떻게 및 엔터프라이즈 템플릿 프로젝트에 프로젝트 포함 되어는 방법을 설명 합니다.  
  
 [속성 창 필드 및 인터페이스](../../extensibility/internals/properties-window-fields-and-interfaces.md)  
 에 표시 되는 정보를 결정 하는 선택에 대 한 기준에 설명 된 **속성** 창.  
  
 [속성 창 개요 목록](../../extensibility/internals/properties-window-object-list.md)  
 용도 설명는 **속성** 창 개체 목록 방법,이 목록에서 다른 개체에 대 한 호출을 트리거하는 경우 환경이 정보를 받는 새 개체 선택 되어 있는지를 설명 하는 합니다.  
  
 [속성 창 단추](../../extensibility/internals/properties-window-buttons.md)  
 에 표시 되는 4 개의 기본 단추의 용도 설명는 **속성** 창 도구 모음입니다.  
  
 [속성 눈금 표시](../../extensibility/internals/properties-display-grid.md)  
 표에서 속성 이름 및 속성 값 필드 있는 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 프로젝트에 설명으로 구성 요소는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
 [컴파일 및 빌드](../../ide/compiling-and-building-in-visual-studio.md)  
 사용 하는 방법에 대해 설명 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 지속적으로 테스트 하 고 빌드하는 동안 응용 프로그램을 디버깅 하기 위한 플랫폼입니다.  
  
 [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx)  
 설명의 `IDispatch` 인터페이스에 처음 액세스 하 고 메서드 및 개체의 속성에 대 한 정보를 검색 하는 런타임에 바인딩된 메커니즘을 제공 하는 자동화를 지원 하도록 설계 되었습니다.  
  
 [응용 프로그램 설정 (.NET) 관리](../../ide/managing-application-settings-dotnet.md)  
 속성 값은 응용 프로그램의 컴파일된 코드 대신 외부 구성 파일에 저장 되므로 응용 프로그램을 구성할 수 있는 응용 프로그램 설정에 대 한 개요를 제공 합니다.  
  
 [솔루션 및 프로젝트](../../ide/solutions-and-projects-in-visual-studio.md)  
 에 대해 설명 어떻게 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 참조, 데이터 연결, 폴더 및 솔루션 및 프로젝트를 통해 개발 작업에 필요한 파일을 같은 항목을 효율적으로 관리 합니다.  
  
 [Visual Studio의 다른 부분 확장](../../extensibility/extending-other-parts-of-visual-studio.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 의 나머지와 일치 하는 UI 요소를 만드는 서비스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.