---
title: 속성 창의 필드 및 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Properties window, fields and interfaces
ms.assetid: 0328f0e5-2380-4a7a-a872-b547cb775050
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a286d8cc782305b746789f56af431d7a62f8e2fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-window-fields-and-interfaces"></a>Properties Window Fields and Interfaces
에 표시 되는 정보를 확인 하려면 선택 영역에 대 한 모델은 **속성** 창이 IDE에서 포커스가 있는 창에 기반 합니다. 모든 창 및 개체 선택된 창 내에서 전역 선택 컨텍스트에 푸시 해당 선택 항목 컨텍스트 개체를 가질 수 있습니다. 환경 해당 창에 포커스가 있을 때 창 프레임의 값으로 글로벌 선택 항목 컨텍스트를 업데이트 합니다. 포커스가 변경 될 때 선택 항목 컨텍스트를 사라지면 합니다.  
  
## <a name="tracking-selection-in-the-ide"></a>IDE에서 선택 영역 추적  
 창 프레임 또는 IDE가 소유한 사이트에 라는 서비스 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>합니다. 다음 단계에서는 다른 열린 창으로 포커스를 변경 하거나에서 서로 다른 프로젝트 항목을 선택 하는 사용자에 의해 발생 한 항목을 어떻게 변경 설명 **솔루션 탐색기**는 에표시되는내용을변경하려면구현 **속성** 창.  
  
1.  VSPackage에는 선택한 창 호출 하 여 만든 개체 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> 있어야 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> 호출 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>합니다.  
  
2.  선택한 창으로 제공 선택 컨테이너 자체 만듭니다 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 개체입니다. VSPackage 호출 하는 선택 항목이 변경 됨 경우 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 모든 수신기는 환경에 알리기 위해 포함 하는 **속성** 변경의 창. 또한 계층 및 항목 새 선택 관련 정보에 대 한 액세스를 제공 합니다.  
  
3.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> 선택한 계층 항목에 전달 하는 `VSHPROPID_BrowseObject` 매개 변수 정보를 표시는 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 개체입니다.  
  
4.  파생 된 개체는 [IDispatch 인터페이스](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) 값이 반환 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 항목을 요청 하 고 환경에 래핑되어에 대 한 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> (다음 단계 참조). 환경에 대 한 두 번째 호출에서는 호출이 실패 한 경우 `IVsHierarchy::GetProperty`, 선택 컨테이너를 전달 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 계층 항목 또는 항목을 제공 합니다.  
  
     VSPackage를 만들지 않고 프로젝트 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 구현 하는 VSPackage의 환경에서 제공한 창 하기 때문에 (예를 들어 **솔루션 탐색기**) 생성 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 을 대신 합니다.  
  
5.  메서드를 호출 하는 환경 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> 에 따라 개체를 가져오는 데는 `IDispatch` 인터페이스를 작성 하는 **속성** 창.  
  
 값은 **속성** 창 변경, Vspackage 구현 `IVsTrackSelectionEx::OnElementValueChangeEx` 및 `IVsTrackSelectionEx::OnSelectionChangeEx` 요소 값에 변경 내용을 보고 해야 합니다. 환경을 다음 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 또는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 표시 되는 정보를 유지 하는 **속성** 창이 속성 값과 동기화 합니다. 자세한 내용은 참조 [속성 창에서 속성 값 업데이트](#updating-property-values-in-the-properties-window)합니다.  
  
 선택 하 여 다른 프로젝트 항목에 **솔루션 탐색기** 해당 항목에 관련 된 속성을 표시 하려면 선택할 수도 있습니다에서 사용할 수 있는 드롭다운 목록을 사용 하 여 폼 이나 문서 창 내에서 다른 개체는 **속성** 창. 자세한 내용은 참조 [속성 창의 개체 목록](../../extensibility/internals/properties-window-object-list.md)합니다.  
  
 정보에 표시 되는 방식을 변경할 수는 **속성** 을 범주, 사전순에서 창 그리드는 에서적절한단추를클릭하여선택한개체에대한속성페이지를도열수,사용가능한경우 **속성** 창. 자세한 내용은 참조 [속성 창 단추](../../extensibility/internals/properties-window-buttons.md) 및 [속성 페이지](../../extensibility/internals/property-pages.md)합니다.  
  
 마지막으로 아래쪽은 **속성** 창에서 선택한 필드에 대 한 설명을 포함는 **속성** 창 표입니다. 자세한 내용은 참조 [속성 창에서 필드 설명 가져오기](#getting-field-descriptions-from-the-properties-window)합니다.  
  
## <a name="updating-property-values-in-the-properties-window"></a> 속성 창에서 속성 값 업데이트
**속성** 창이 속성 값 변경과 동기화 상태를 유지하도록 하는 방법에는 두 가지가 있습니다. 첫 번째 호출 하는 것은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 환경에서 제공 하는 도구 및 문서 창의 생성 및 액세스를 포함 하는 기본적인 창 관리 기능에 대 한 액세스를 제공 하는 인터페이스입니다. 다음 단계에서 이 동기화 프로세스를 설명합니다.  
  
### <a name="updating-property-values-using-ivsuishell"></a>IVsUIShell을 사용하여 속성 값 업데이트  
  
#### <a name="to-update-property-values-using-the-ivsuishell-interface"></a>IVsUIShell 인터페이스를 사용하여 속성 값을 업데이트하려면  
  
1.  호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> (통해 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스) 언제 든 지 해당 VSPackages, 프로젝트 또는 편집기를 만들거나 도구 창과 문서 창 열거 해야 합니다.  
  
2.  구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.RefreshPropertyBrowser%2A> 유지 하는 **속성** 창에는 프로젝트에 대 한 속성 변경과 동기화 (또는 탐색 하는 다른 선택 된 개체는 **속성** 창) 구현하지않고<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 하 고 발생 <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink.OnChanged%2A> 이벤트입니다.  
  
3.  구현 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.AdviseHierarchyEvents%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.UnadviseHierarchyEvents%2A> 를 설정 하 고 비활성화를 구현 하는 계층 구조를 필요 없이 계층 이벤트의 클라이언트 알림을 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>합니다.  
  
### <a name="updating-property-values-using-iconnection"></a>IConnection을 사용하여 속성 값 업데이트  
 **속성** 창과 속성 값 변경의 동기화를 유지하는 두 번째 방법은 연결 가능 개체에 `IConnection` 를 구현하여 송신 인터페이스가 있음을 나타내는 것입니다. 속성 이름을 지역화 하려는 경우에서 개체를 파생 <xref:System.ComponentModel.ICustomTypeDescriptor>합니다. <xref:System.ComponentModel.ICustomTypeDescriptor> 구현에서 반환 하는 속성 설명자를 수정 하 고 속성의 이름을 변경할 수 있습니다. 파생 되는 특성을 만듭니다. 설명을 지역화 하려면 <xref:System.ComponentModel.DescriptionAttribute> Description 속성을 재정의 합니다.  
  
#### <a name="considerations-in-implementing-the-iconnection-interface"></a>IConnection 인터페이스 구현 시 고려 사항  
  
1.  `IConnection` 통해 열거자 하위 개체에 대 한 액세스를 제공는 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> 인터페이스입니다. 또한 모든 연결 지점 하위 개체에 대 한 액세스 제공 구현 하는 각는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 인터페이스입니다.  
  
2.  모든 찾아보기 개체가 구현을 담당는 <xref:Microsoft.VisualStudio.OLE.Interop.IPropertyNotifySink> 이벤트입니다. **속성** 창은 `IConnection`를 통해 설정된 이벤트에 대해 통지합니다.  
  
3.  연결 지점 제어의 구현에서 허용 연결 수 (하나 이상의) <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>합니다. 하나의 인터페이스만 허용 하는 연결점을 반환할 수 있습니다 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> 에서 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.EnumConnections%2A> 메서드.  
  
4.  클라이언트가 호출할 수는 `IConnection` 통해 열거자 하위 개체에 대 한 액세스를 얻으려고 인터페이스는 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> 인터페이스입니다. <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnectionPoints> 각 송신 인터페이스 ID (IID)에 대 한 연결점을 열거할 인터페이스를 호출할 수 있습니다.  
  
5.  `IConnection` 와 연결점 하위 개체에 대 한 액세스를 얻으려고 호출할 수도 있습니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 각 송신 IID에 대 한 인터페이스입니다. 통해는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 클라이언트 인터페이스를 시작 하거나 연결 가능 개체 및 클라이언트 자체 동기화로 통지 루프를 종료 합니다. 클라이언트 호출 또한 있습니다는 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint> 인터페이스를 통해 열거자 개체를 가져올는 <xref:Microsoft.VisualStudio.OLE.Interop.IEnumConnections> 인터페이스를 알고 있는 연결을 열거 합니다.  
  
## <a name="getting-field-descriptions-from-the-properties-window"></a> 속성 창에서 필드 설명 가져오기
**속성** 창 맨 아래 설명 영역에는 선택한 속성 필드와 관련된 정보가 표시됩니다. 이 기능은 기본적으로 켜져 있습니다. 설명 필드를 숨기려면 **속성** 창을 오른쪽 단추로 클릭하고 **설명**을 클릭합니다. 그러면 메뉴 창에서 **설명** 제목 옆의 확인 표시가 사라집니다. 같은 방법으로 **설명** 을 다시 토글하면 필드가 표시됩니다.  
  
 설명 필드에 정보에서 가져온 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>합니다. 각 메서드, 인터페이스, coclass 등은 형식 라이브러리에 지역화되지 않은 `helpstring` 특성을 가질 수 있습니다. **속성** 창에서 문자열을 검색 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo.GetDocumentation%2A>합니다.  
  
### <a name="to-specify-localized-help-strings"></a>지역화된 도움말 문자열을 지정하려면  
  
1.  형식 라이브러리( `helpstringdll` )의 라이브러리 문에`typelib`특성을 추가합니다.  
  
    > [!NOTE]
    >  형식 라이브러리가 개체 라이브러리 (.olb) 파일인 경우 이 단계는 선택 사항입니다.  
  
2.  문자열에 대한 지정 `helpstringcontext` 특성을 지정합니다. `helpstring` 특성을 지정할 수도 있습니다.  
  
     이러한 특성은 실제 .chm 파일 도움말 항목에 포함된 `helpfile` 및 `helpcontext` 특성과 별개입니다.  
  
 강조 표시 된 속성 이름에 대해 표시할 설명 정보를 검색 하는 **속성** 창 호출 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetDocumentation2%2A> 선택 되어 있는 속성에 대 한 원하는 지정 `lcid` 특성에 출력 문자열입니다. 내부적으로 <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2> 에 지정 된.dll 파일을 찾아서는 `helpstringdll` 특성 및 호출 `DLLGetDocumentation` 지정한 컨텍스트와 연결 된 해당.dll 파일에 대해 및 `lcid` 특성입니다.  
  
 `DLLGetDocumentation` 의 서명 및 구현:  
  
```cpp  
STDAPI DLLGetDocumentation  
(  
   ITypeLib * /* ptlib */,  
   ITypeInfo * /* ptinfo */,  
   LCID /* lcid */,  
   DWORD dwCtx,  
   BSTR * pbstrHelpString  
);  
```  
  
 `DLLGetDocumentation` 함수는 DLL에 대한.def 파일에 정의된 내보내기여야 합니다.  
  
 내부적으로 .olb 파일이 생성되는데 실제로 이것은 DLL입니다. 이 DLL에는 형식 라이브러리(.tlb) 파일 리소스 하나와 내보내기 함수 `DLLGetDocumentation`하나가 있습니다.  
  
 .olb 파일의 경우 .tlb 파일 자체를 포함하는 것과 같은 파일이므로 `helpstringdll` 특성은 선택 사항입니다.  
  
 따라서 **설명** 창에 문자열이 나타나도록 하려면 최소한 형식 라이브러리에서 `helpstring` 특성을 지정해야 합니다. 이러한 문자열을 지역화하려면 `helpstringdll` (선택 사항) 특성 및 `helpstringcontext` (필수) 특성을 지정하고 `DLLGetDocumentation`을(를) 구현해야 합니다.  
  
 idl의 `helpstringcontext` 특성 및 `DLLGetDocumentation`을(를) 통해 지역화된 정보를 가져올 경우 추가 인터페이스를 구현할 필요가 없습니다.  
  
 구현 하 여 지역화 된 이름 및 속성의 설명을 가져오는 또 하나의 방법은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.GetLocalizedPropertyInfo%2A>합니다. 이 메서드의 구현에 관련 된 자세한 내용은 참조 하십시오. [속성 창의 필드 및 인터페이스](../../extensibility/internals/properties-window-fields-and-interfaces.md)합니다.  

## <a name="see-also"></a>참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)