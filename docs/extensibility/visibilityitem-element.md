---
title: "VisibilityItem 요소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VisibilityItem element (VSCT XML schema)
- VSCT XML schema elements, VisibilityItem
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: db041f839e9b7e8ad3268175829ecfee9380e736
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="visibilityitem-element"></a>VisibilityItem 요소
`VisibilityItem` 요소 명령 및 도구 모음 정적 표시 여부를 결정 합니다. 명령 또는 메뉴 및 관련된 명령 UI 컨텍스트는 모든 항목을 식별합니다. Visual Studio 명령, 메뉴 및 도구 모음 및 표시 여부를 정의 하는 Vspackage를 로드 하지 않고 검색 합니다. 사용 하 여 IDE는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> 명령 UI 컨텍스트 활성 상태 인지 확인 하는 메서드.  
  
 Visual Studio는 VSPackage에서 결정 해야 하는 명령 표시 유형에서는 VSPackage를 로드 한 다음 보다는 `VisibilityItem`합니다. 명령의 표시 여부를 확인 하려면를 구현할 수 있습니다 하나는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 이벤트 처리기 또는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 명령을 구현 방법과 따라 메서드.  
  
 명령 또는 있는 메뉴는 `VisibilityItem` 요소가 연결 된 컨텍스트 활성 경우에 표시 됩니다. 각 명령 컨텍스트부터 조합에 대 한 항목을 포함 하 여 하나 이상의 명령 UI 컨텍스트가 있는 단일 명령, 메뉴 또는 도구 모음을 연결할 수 있습니다. 명령이 나 메뉴와 연결 된 여러 명령 UI 컨텍스트가 있는 경우 다음 명령 또는 메뉴 표시 되지만 관련된 명령이 UI 컨텍스트 중 하나가 활성화 된 경우  
  
 `VisibilityItem` 요소 명령, 메뉴 및 도구 모음, 그룹에 하지에 적용 됩니다. 요소는 관련 없는 `VisibilityItem` 요소는 부모 메뉴 활성화 될 때마다 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|guid|필수 요소. GUID/ID 명령 식별자의 GUID입니다.|  
|ID|필수 요소. ID는 GUID/ID 명령 식별자입니다.|  
|컨텍스트(context)|필수 요소. 이 명령은 표시 되는 UI 컨텍스트.|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` 요소 명령 및 도구 모음 그룹의 정적 표시 여부를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 에 정의 된 표준 Visual Studio UI 컨텍스트는 *Visual Studio SDK 설치 경로*\VisualStudioIntegration\Common\Inc\vsshlids.h 파일에서와 같이 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> 및 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> 클래스입니다. UI 컨텍스트 자세한 집합에 정의 된는 <xref:Microsoft.VisualStudio.VSConstants> 클래스입니다.  
  
## <a name="example"></a>예제  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)