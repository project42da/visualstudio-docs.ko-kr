---
title: "동적 도구 창 열기 | Microsoft Docs"
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
  - "동적 도구 창"
ms.assetid: 21547ba7-6e81-44df-9277-265bf34f877a
caps.latest.revision: 21
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# 동적 도구 창 열기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

일반적으로 도구 창에는 해당 하는 바로 가기 키 또는 메뉴를 명령에서 열립니다. 하지만 때때로 특정 UI 컨텍스트에 적용 되며 UI 컨텍스트의 더 이상 적용 될 때 닫힙니다 때마다 열리는 도구 창을 할 수 없습니다. 이러한 도구 창 이라고 *동적* 또는 *자동 표시*합니다.  
  
> [!NOTE]
>  미리 정의 된 UI 컨텍스트가 목록은 참조 하십시오. <xref:Microsoft.VisualStudio.VSConstants.UIContext>합니다. 에  
  
 시작 시 동적 도구 창을 열려는 하 고 만들 때 오류에 대 한 것이 불가능을 구현 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx> 인터페이스 및 테스트에 실패 조건은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwnerEx.QueryShowTool%2A> 메서드. 시작 시 열려야 하는 동적 도구 창이 있다는 것을 아는 셸에 대 한 순서로 추가 해야는 `SupportsDynamicToolOwner` 패키지 등록이 값 \(1로 설정 됨\). 이 값은 표준의 일부가 아닙니다. <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>, 추가 사용자 지정 특성을 만들어야 합니다. 사용자 지정 특성에 대 한 자세한 내용은 참조 [사용자 지정 등록 특성을 사용하여 확장 등록](../misc/using-a-custom-registration-attribute-to-register-an-extension.md)합니다.  
  
 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 도구 창을 엽니다. 필요에 따라 도구 창이 만들어집니다.  
  
> [!NOTE]
>  사용자가 동적 도구 창을 닫을 수 있습니다. 사용자 도구 창을 다시 열 수 있도록 메뉴 명령을 만들려면 원하는 도구 창과 그렇지 않으면 사용 안 함으로 열리는 동일한 UI 컨텍스트 메뉴 명령을 활성화 해야 합니다.  
  
### 동적 도구 창을 열려면  
  
1.  라는 이름의 VSIX 프로젝트 **DynamicToolWindow** 라는 도구 창 항목 템플릿을 추가 하 고 **DynamicWindowPane.cs**합니다. 자세한 내용은 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)을 참조하십시오.  
  
2.  DynamicWindowPanePackage.cs 파일에서 DynamicWindowPanePackage 선언을 찾습니다. 추가 된 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 특성과 T:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute 도구 창을 등록할 수 있습니다.  
  
    ```vb  
    [[ProvideToolWindow(typeof(DynamicWindowPane)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), VSConstants.UICONTEXT.SolutionExists_string)] [PackageRegistration(UseManagedResourcesOnly = true)] [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About [ProvideMenuResource("Menus.ctmenu", 1)] [ProvideToolWindow(typeof(DynamicToolWindow.DynamicWindowPane))] [Guid(DynamicWindowPanePackageGuids.PackageGuidString)] public sealed class DynamicWindowPanePackage : Package {. . .}  
    ```  
  
     Visual Studio를 닫았다가 하는 경우 지속 되지 않는 일시적인 창으로 DynamicWindowPane 라는 도구 창을 등록 됩니다. DynamicWindowPane 열릴 때마다 <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionExists_string> 적용 되며 그렇지 않으면 종료 합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 나타납니다. 도구 창이 나타나지 않습니다.  
  
4.  실험적 인스턴스에서 프로젝트를 엽니다. 도구 창이 표시 됩니다.