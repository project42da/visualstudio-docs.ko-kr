---
title: "동적 도구 창 열기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, dynamic
ms.assetid: 21547ba7-6e81-44df-9277-265bf34f877a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 197bda3f825d0e709c1bc9ae08d8f0018b8b07c5
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="opening-a-dynamic-tool-window"></a>동적 도구 창 열기
도구 창은 일반적으로 메뉴나 해당 바로 가기 명령에서 열립니다. 하지만 때때로 특정 UI 컨텍스트 적용 되며 UI 컨텍스트가 더 이상 적용 될 때 닫힙니다 때마다 열리는 도구 창을 할 수 없습니다. 이러한 유형의 도구 창 호출 *동적* 또는 *자동 표시*합니다.  
  
> [!NOTE]
>  목록이 미리 정의 된 UI 컨텍스트가 대 한 참조 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT>합니다. 에  
  
 만들지 못하거나 수 있기를 구현 해야 하 고 시작 시 동적 도구 창을 열려면 하려는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx> 인터페이스 및 테스트에 오류 상태는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx.QueryShowTool%2A> 메서드. 시작 시 열 수 있는 동적 도구 창도 셸용 순서로 추가 해야 합니다는 `SupportsDynamicToolOwner` 패키지 등록이 값 (1로 설정 됨). 이 값은 표준의 일부가 아닙니다. <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>이므로 추가 사용자 지정 특성을 만들어야 합니다. 사용자 지정 특성에 대 한 자세한 내용은 참조 [확장을 등록 하는 사용자 지정 등록 특성을 사용 하 여](../extensibility/registering-and-unregistering-vspackages.md#using-a-custom-registration-attribute-to-register-an-extension)합니다.  
  
 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 도구 창을 엽니다. 필요에 따라 도구 창이 생성 됩니다.  
  
> [!NOTE]
>  사용자가 동적 도구 창을 닫을 수 있습니다. 사용자 도구 창을 다시 열 수 있도록 메뉴 명령을 만들려면 하려는 경우에 메뉴 명령은 그렇지 않으면 사용 안 함 확인 하 고 도구 창을 엽니다 동일한 UI 컨텍스트에서 활성화 해야 합니다.  
  
### <a name="to-open-a-dynamic-tool-window"></a>동적 도구 창을 열려면  
  
1.  라는 VSIX 프로젝트를 **DynamicToolWindow** 라는 도구 창 항목 템플릿을 추가 하 고 **DynamicWindowPane.cs**합니다. 자세한 내용은 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
2.  DynamicWindowPanePackage.cs 파일에서 DynamicWindowPanePackage 선언을 찾습니다. 추가 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 및 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute> 도구 창을 등록 하는 특성입니다.  
  
    ```vb  
    [ProvideToolWindow(typeof(DynamicWindowPane)]  
    [ProvideToolWindowVisibility(typeof(DynamicWindowPane), VSConstants.UICONTEXT.SolutionExists_string)]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [ProvideToolWindow(typeof(DynamicToolWindow.DynamicWindowPane))]  
    [Guid(DynamicWindowPanePackage.PackageGuidString)]  
    public sealed class DynamicWindowPanePackage : Package  
    {. . .}  
    ```  
  
     위의 특성에는 Visual Studio를 닫았다가 경우 지속 되지 않는 일시적인 윈도우로 DynamicWindowPane 라는 도구 창을 등록 합니다. DynamicWindowPane 열릴 때마다 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_string> 적용 되며 그렇지 않은 경우 종료 합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스 표시 되어야 합니다. 도구 창이 나타나지 않습니다.  
  
4.  실험적 인스턴스에서 프로젝트를 엽니다. 도구 창이 나타납니다.