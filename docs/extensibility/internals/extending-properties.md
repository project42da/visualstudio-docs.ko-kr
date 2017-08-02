---
title: "속성 확장 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Properties window, providing support
ms.assetid: 68e2cbd4-861c-453f-8c9f-4ab6afc80e67
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: fec1140bc90d494a0c611ed84786f364f17f6087
ms.lasthandoff: 02/22/2017

---
# <a name="extending-properties"></a>속성 확장
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **속성** 창은 COM 및 COM + 구성 요소에 대 한 범용 속성 브라우저 이며 모든 지원 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 제품입니다. **속성** 창이 연동 `ITypeInfo` 정보 및 COM + 통합된 개발 환경 (IDE)에서 다른 창에서 현재 선택 된 개체에 대 한 디자인 타임 속성을 나열 하려면 메타 데이터를 입력 합니다.  
  
 **속성** F4 키를 눌러 키보드에서 하거나 선택 하 여 열 수 있는 창 **속성 창** 에 **보기** 메뉴, 보기 및 편집 구성 독립적, 디자인 타임 속성 및 선택 된 개체의 이벤트를 사용 합니다. 솔루션 및 프로젝트와 연관 되는 구성에 종속 된 속성에 표시 됩니다 [속성 페이지](../../extensibility/internals/property-pages.md)합니다. 자세한 내용은 참조 [NIB: 프로젝트 속성](http://msdn.microsoft.com/en-us/fb126574-24ad-4c96-9b2b-6e1f3879ba50), [관리 구성 옵션](../../extensibility/internals/managing-configuration-options.md), 및 [프로젝트의 NIB: 항목 관리](http://msdn.microsoft.com/en-us/762e606b-7f44-4b66-97a1-e30a703654a0)합니다.  
  
 ![속성 창 개요](~/extensibility/internals/media/vspropertieswindow.png "vsPropertiesWindow")  
속성 창  
  
 이 섹션의 개별 영역에 관련 된 자세한 정보를 제공 된 **속성** 창 및 구현 해야 하는 인터페이스와 창을 채울를 호출 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [속성 창 개요](../../extensibility/internals/properties-window-overview.md)  
 용도 설명는 **속성** 도구 창과 문서 창에 상대적인 창의 합니다.  
  
 [템플릿 정책 및 속성 창](../../extensibility/internals/template-policy-and-the-properties-window.md)  
 엔터프라이즈 템플릿 프로젝트에 프로젝트는 포함 하는 방법 및 엔터프라이즈 템플릿 프로젝트에 해당 정책을 적용할 수는 방법을 설명 합니다.  
  
 [속성 창의 필드 및 인터페이스](../../extensibility/internals/properties-window-fields-and-interfaces.md)  
 에 표시 되는 정보를 결정 하는 선택에 대 한 기준에 설명 된 **속성** 창입니다.  
  
 [속성 창의 개체 목록](../../extensibility/internals/properties-window-object-list.md)  
 용도 설명 된 **속성** 창 개체 목록 방법,이 목록에서 다른 개체에 대 한 호출 트리거하면 환경 합리적인 새 개체가 선택 되어 있는지를 설명 하는 합니다.  
  
 [속성 창 단추](../../extensibility/internals/properties-window-buttons.md)  
 에 표시 되는&4; 개의 기본 단추의 용도 설명의 **속성** 창 도구 모음입니다.  
  
 [눈금 표시 속성](../../extensibility/internals/properties-display-grid.md)  
 속성 이름 및 속성 값 필드 모눈에서 발견 되는 위치에 대해 설명 합니다.  
  
 [속성 창 선택 영역 추적 발표](../../misc/announcing-property-window-selection-tracking.md)  
 선택 영역에 대 한 추적에 대해 설명 된 **속성** 창입니다.  
  
 [자식 속성을 가진 속성 숨기기](../../misc/hiding-properties-that-have-child-properties.md)  
 구현 하 여 자식 속성을 갖는 속성을 숨기는 방법에 설명 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>인터페이스.</xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>  
  
 [사용자 지정 속성 창 제공](../../misc/providing-a-custom-properties-window.md)  
 사용자 고유의 속성 브라우저를 제공 하는 단계를 자세히 설명 합니다.  
  
 [속성 창에서 필드 설명 가져오기](../../misc/getting-field-descriptions-from-the-properties-window.md)  
 선택한 속성 필드와 관련 된 정보를 표시 하는 설명 영역을 찾을 수 있는 위치에 설명 합니다.  
  
 [속성 창에서 속성 값을 업데이트합니다.](../../misc/updating-property-values-in-the-properties-window.md)  
 유지 하는 방법을 보여 주는 단계별 지침을 제공 된 **속성** 창 속성 값 변경 내용과 동기화 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로젝트 형식](../../extensibility/internals/project-types.md)  
 프로젝트에 설명의 구성 요소로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE입니다.  
  
 [컴파일 및 빌드](../../ide/compiling-and-building-in-visual-studio.md)  
 사용 하는 방법에 대해 설명 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 지속적으로 테스트 하 고을 빌드할 때 응용 프로그램을 디버깅 하기 위한 플랫폼입니다.  
  
 [HTML 문서 속성, 속성 창](http://msdn.microsoft.com/Library/46e3d164-a1a7-42f9-87b0-344e10a37b62)  
 속성 창에서 직접 HTML 문서를 편집 하는 것에 대 한 지침을 제공 하 고 속성 창에서 HTML 문서에 있는 필드를 자세히 보여 주는 표가 제공 합니다.  
  
 [IDispatch](http://msdn.microsoft.com/en-us/ebbff4bc-36b2-4861-9efa-ffa45e013eb5)  
 설명의 `IDispatch` 인터페이스에는 처음에 액세스 하는 메서드와 개체의 속성에 대 한 정보를 검색할 런타임에 바인딩 메커니즘을 제공 하는 자동화를 지원 하도록 설계 됩니다.  
  
 [NIB: 동적 속성 (Visual Studio) 소개](http://msdn.microsoft.com/en-us/f5102027-1431-4195-ae40-9b991de46d3a)  
 속성 값은 응용 프로그램의 컴파일된 코드는 대신 외부 구성 파일에 저장 되므로 응용 프로그램을 구성할 수 있는 동적 속성에 간략하게 설명 합니다.  
  
 [NIB: 컨테이너로 서의 프로젝트](http://msdn.microsoft.com/en-us/87d40f63-f487-4767-8963-64beec27ba1b)  
 컨테이너에 논리적으로 관리, 빌드 및 디버그 응용 프로그램을 구성 하는 항목에 대 한 해결책으로 프로젝트의 역할에 설명 합니다.  
  
 [NIB: 프로젝트 속성](http://msdn.microsoft.com/en-us/fb126574-24ad-4c96-9b2b-6e1f3879ba50)  
 프로젝트 설정을 사용 하면 전체 프로젝트에 적용 되는 컨트롤 속성 및 프로젝트의 특정 빌드 구성에만 적용 되는 속성을 관리 하는 방법에 대해 설명 합니다.  
  
 [솔루션 및 프로젝트](../../ide/solutions-and-projects-in-visual-studio.md)  
 설명 어떻게 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 참조, 데이터 연결, 폴더 및 솔루션 및 프로젝트를 통해 개발 작업에 필요한 파일을 같은 항목을 효율적으로 관리 합니다.  
  
 [Visual Studio의 다른 부분을 확장합니다.](../../extensibility/extending-other-parts-of-visual-studio.md)  
 사용 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 의 나머지와 일치 하는 UI 요소를 만들기 위해 서비스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.
