---
title: "VisibilityItem 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VisibilityItem 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, VisibilityItem"
ms.assetid: 0932f551-972d-4194-84bb-426e3e4375e4
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# VisibilityItem 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`VisibilityItem` 요소는 명령 및 도구 모음 정적 표시 여부를 결정 합니다. 명령 또는 메뉴 및 연결 된 명령 UI 컨텍스트는 모든 항목을 식별합니다. Visual Studio 명령, 메뉴 및 도구 모음 및 표시 유형을 정의 하는 Vspackage를 로드 하지 않고 검색 합니다. IDE를 사용 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> 메서드 명령 UI 컨텍스트의 활성 인지 여부를 확인 합니다.  
  
 Visual Studio에서는 VSPackage에 의해 결정 하는 명령 표시 유형을 VSPackage가 로드 되 면 보다는 `VisibilityItem`합니다. 명령의 표시 여부를 확인 하려면 하거나 구현할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus> 이벤트 처리기 또는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 명령을 구현 방법에 따라 메서드.  
  
 명령이 나 된 메뉴에는 `VisibilityItem` 요소는 연결 된 컨텍스트 활성 경우에 나타납니다. 각 명령 컨텍스트 조합에 대 한 항목을 포함 하 여 하나 이상의 명령 UI 컨텍스트가 있는 단일 명령, 메뉴 또는 도구 모음을 연결할 수 있습니다. 명령이 나 메뉴와 연결 된 여러 명령 UI 컨텍스트 다음 명령이 나 메뉴 표시 되는지 관련 된 명령이 UI 컨텍스트 중 하나가 활성화할 때입니다.  
  
 `VisibilityItem` 요소 명령, 메뉴 및 도구 모음, 그룹에 하지에 적용 됩니다. 요소는 관련 없는 `VisibilityItem` 요소는 부모 메뉴 활성화 될 때마다 표시 합니다.  
  
## 구문  
  
```  
<VisibilityItem  
  guid ="="cmdGuidMyProductCommands"  
  id=="cmdidAddWidget"  
  context="guidNotViewSourceMode"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|guid|필수 요소. GUID\/ID 명령 식별자의 GUID입니다.|  
|ID|필수 요소. ID는 GUID\/ID 명령 식별자입니다.|  
|컨텍스트|필수 요소. 이 명령은 표시 되는 UI 컨텍스트.|  
|조건|선택적 요소.[조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)을 참조하세요.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)|`VisibilityConstraints` 요소 그룹 명령 및 도구 모음을 정적 표시 여부를 결정 합니다.|  
  
## 설명  
 에 표준 Visual Studio UI 컨텍스트에 정의 *Visual Studio SDK 설치 경로*\\VisualStudioIntegration\\Common\\Inc\\vsshlids.h 뿐만 아니라 파일에서와 같이 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids> 및 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80> 클래스입니다. UI 컨텍스트의 전체 집합에 정의 되어는 <xref:Microsoft.VisualStudio.VSConstants> 클래스입니다.  
  
## 예제  
  
```  
<VisibilityConstraints> <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget" context="guidNotViewSourceMode"/> </VisibilityConstraints>  
```  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A>   
 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand.BeforeQueryStatus>   
 <xref:Microsoft.VisualStudio.VSConstants>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids>   
 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>   
 [VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)