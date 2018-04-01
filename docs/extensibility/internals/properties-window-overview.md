---
title: 속성 창 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window
ms.assetid: 289ed4f2-02ac-4899-855e-42dfe57ee05f
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1f766fe903df4f7a7ea36fb4ec1654b889457f65
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-window-overview"></a>속성 창 개요
**속성** 창을 사용 하는 두 가지 주요 유형의에서 사용할 수 있는 windows에서 선택한 개체에 대 한 속성을 표시 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE). 이러한 두 창의 유형은 다음과 같습니다.  
  
-   솔루션 탐색기, 클래스 뷰 및 개체 브라우저와 같은 도구 창  
  
-   이러한 편집기와 forms 디자이너, XML 편집기 및 HTML 편집기와 디자이너를 포함 하는 문서 창  
  
## <a name="using-the-properties-window"></a>속성 창을 사용 하 여  
 **속성** 단일 또는 여러 선택된 항목의 속성 창에 표시 됩니다. 여러 항목을 선택 하는 경우 선택한 모든 개체에 대 한 모든 속성의 교집합 표시 됩니다.  
  
 양식 디자인 창 또는 COM + 메타 데이터를 사용 하 여 HTML 편집기 내에서 선택한 개체와 관련 된 이벤트에 표시 됩니다는 **속성** 창. 단추 선택와 같은 연결 된 이벤트를 표시 하는 예를 들어 한 `OnClick` 단추에 연결할 수 있는 이벤트입니다.  
  
 이벤트에 표시 되는 **속성** 창은 코드에 바인딩되는 개체와 데 주로 사용 됩니다. 코드와 작업에 없는 파일 형식을 편집 하는 경우 모든 이벤트가 하지 않을 수 있습니다. 이벤트에만 표시 됩니다는 **속성** 코드 및 특정 개체와 관련 된 특정 이벤트를 실행 하는 서로 바인딩되지 창. 이러한 예로 해당 개체가 활성화 될 때 실행 되는 선택한 개체를 지 원하는 코드 것입니다.  
  
 다음 표에서 사용 하는 기본 인터페이스는 **속성** 창.  
  
|인터페이스 이름|설명|  
|--------------------|-----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>|범주를의 목록을 제공는 **속성** 창 범주를 각 속성에 매핑합니다.|  
|[IDispatch 인터페이스](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx)|개체의 메서드 및 속성 프로그래밍 도구 및 자동화를 지 원하는 기타 응용 프로그램을 노출 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>|호출 하는 줄임표 (...) 단추를 제공 *빌더* 개체 자체에서 구현 하는 모달 대화 상자 창을 열입니다. 값을 텍스트 필드에 사용자가 쉽게 형식화 되지 않은 때 사용 됩니다. 예를 들어, RGB 값을 결정 하는 색 선택을 열을 사용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>|에 표시 된 정보를 업데이트 하는 데 사용 되는 개체에 대 한 액세스를 제공는 **속성** 창. <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>관련된 표시할 속성을 사용 하 여 선택할 수 있는 개체를 포함 하는 각 창에 대 한 Vspackage에 의해 구현 됩니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>|구조체의 필드 및 인터페이스의 메서드는 등 개체의 유형에 대 한 정보를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>|Vspackage를 선택 이벤트에 대 한 알림을 수신 하 고 현재 프로젝트 계층 구조, 항목, 요소 값 및 명령 UI 컨텍스트 하는 방법에 대 한 정보를 검색할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMultiItemSelect>|여러 선택 항목에 액세스할 수 있는 환경을 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>|에 표시 되는 일부 속성에서 지역화 된 이름을 제공 하는 데는 **속성** 창.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>|변경 내용을 현재 선택 영역, 요소 값 또는 명령 UI 컨텍스트에 등록 된 Vspackage를에 알립니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>|현재 선택한 항목의 변경의 환경에 게 알리는 하 고 계층 및 항목 관련 정보를 새 선택에 대 한 액세스를 제공 합니다.|  
  
 에 대 한 자세한 내용은 `IDispatch`, MSDN library를 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)   
 [속성 창 필드 및 인터페이스](../../extensibility/internals/properties-window-fields-and-interfaces.md)