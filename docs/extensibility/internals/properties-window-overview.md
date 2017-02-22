---
title: "속성 창 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 창"
ms.assetid: 289ed4f2-02ac-4899-855e-42dfe57ee05f
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 속성 창 개요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**속성** 창에서 windows에서 사용할 수 있는 두 가지 유형의 선택한 개체의 속성을 표시 하는 데 사용의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)입니다.  Windows 이러한 두 가지 유형이 있습니다.  
  
-   솔루션 탐색기, 클래스 뷰 및 개체 브라우저 같은 도구 창  
  
-   이러한 편집기와 디자이너 폼 디자이너, XML 편집기, HTML 편집기로 포함 된 문서가 windows  
  
## 속성 창을 사용 하 여  
 해당  **속성이** 단일 또는 여러 개의 선택된 항목의 속성 창에 표시 됩니다.  여러 항목을 선택 하면 선택한 모든 개체에 대 한 모든 속성의 교차 표시 됩니다.  
  
 양식 디자인 창 또는 COM \+ 메타 데이터를 사용 하 여 HTML 편집기 내에서 선택한 개체와 관련 된 이벤트에 표시 되는  **속성** 창.  예를 들어, 단추를 선택 하 고 연관 된 이벤트를 다음과 같이 표시할는 `OnClick` 이벤트를 해당 단추를 연결할 수 있습니다.  
  
 이벤트에 표시 되는  **속성** 창을 주로 코드에 바인딩되는 개체를 사용 합니다.  아무 것도 코드를 사용할 수 없는 파일 형식을 편집 하는 경우 이벤트가 있을 것입니다.  이벤트에 표시 됩니다만  **속성** 바인딩 간에 특정 객체와 연관 된 특정 이벤트 및 코드를 실행 하면 창을.  이러한 예는 코드 숨김 선택한 개체는 해당 개체가 활성화 될 때 실행 됩니다.  
  
 다음 표에서 사용 되는 기본 인터페이스의  **속성이** 창.  
  
|인터페이스 이름|설명|  
|--------------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ICategorizeProperties>|범주 목록을 제공 합니다.는  **속성이** 창 및 각 속성 범주에 매핑합니다.|  
|[IDispatch 인터페이스](http://msdn.microsoft.com/ko-kr/ebbff4bc-36b2-4861-9efa-ffa45e013eb5)|개체의 메서드 및 속성 프로그래밍 도구 및 자동화를 지 원하는 다른 응용 프로그램에 노출 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IProvidePropertyBuilder>|줄임표 \(...\) 단추를 호출을 제공  *빌더* 개체에서 구현 하는 모달 대화 상자가 windows를 엽니다.  값 텍스트 필드에서 사용자가 쉽게 형식화 되지 않은 경우에 사용 합니다.  예를 들어, RGB 값을 결정 하 여 색상 피커를 엽니다 사용 될 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>|표시 된 정보를 업데이트 하는 데 사용 되는 개체에 대 한 액세스는  **속성이** 창.  <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>Vspackages가 선택할 수 있는 개체를 표시 하는 관련 된 속성을 포함 하는 각 창에 대 한 구현입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>|인터페이스 및 구조체의 필드 메서드 같은 개체 형식에 대 한 정보를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>|Vspackages를 선택 이벤트 알림을 수신 하 고 현재 프로젝트 계층, 항목, 요소 값 및 명령 UI 컨텍스트에 대 한 정보를 검색할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMultiItemSelect>|환경을에 액세스 하는 여러 항목을 선택할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>|지역화 된 이름이 표시 되는 몇 가지 속성을 제공 하는 데 사용 되는  **속성이** 창.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>|현재 선택 항목, 요소 값 또는 명령 UI 컨텍스트 변경의 등록 된 Vspackages에 알립니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>|현재 선택 영역에 변경 된 환경 알리고 새 선택 영역에 관련 된 항목 및 계층 구조 정보에 액세스 합니다.|  
  
 에 대 한 자세한 내용은 `IDispatch`에서 MSDN library를 참조 하십시오.  
  
## 참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)   
 [속성 창의 필드 및 인터페이스](../../extensibility/internals/properties-window-fields-and-interfaces.md)