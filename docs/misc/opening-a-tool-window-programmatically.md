---
title: "프로그래밍 방식으로 도구 창 열기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 창, 프로그래밍 방식으로 만들기"
ms.assetid: 0017441e-7aa3-4a61-9939-57af11d90d97
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# 프로그래밍 방식으로 도구 창 열기
도구 창은 일반적으로 메뉴의 명령을 클릭하거나 해당하는 바로 가기 키를 눌러 엽니다. 그러나 명령 처리기와 같이 프로그래밍 방식으로 도구 창을 열어야 할 수도 있습니다.  
  
 도구 창을 제공하는 관리되는 VSPackage에서 도구 창을 열려면 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A>를 사용합니다. 다른 VSPackage에서 도구 창을 열려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.FindToolWindow%2A>를 사용합니다. 두 경우 모두, 필요에 따라 도구 창이 생성됩니다.  
  
 다음 코드는 C\# Reference.ToolWindow 샘플에서 가져온 것입니다.  
  
### 프로그래밍 방식으로 도구 창을 열려면  
  
1.  도구 창, 프레임 및 구현하는 VSPackage를 만듭니다. 자세한 내용은 [도구 창 추가](../extensibility/adding-a-tool-window.md)을 참조하세요.  
  
2.  도구 창을 제공하는 VSPackage에 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute>를 추가합니다.  
  
    ```c#  
    [ProvideToolWindow(typeof(PersistedWindowPane), Style = VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideMenuResource(1000, 1)] [MsVsShell.DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\8.0Exp")] [PackageRegistration(UseManagedResourcesOnly = true)] [Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")] // your package will have a different GUID public class PackageToolWindow : Package {  
    ```  
  
     그러면 도구 창 PersistedWindowPane이 **솔루션 탐색기**에 도킹된 상태로 열리도록 등록됩니다. 자세한 내용은 [등록 하는 도구 창](../extensibility/registering-a-tool-window.md)을 참조하세요.  
  
3.  <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A>를 사용하여 도구 창을 찾거나 아직 없는 경우 새로 만들 수 있습니다.  
  
    ```vb#  
    ' Get the 1 (index 0) and only instance of our tool window. ' If it does not already exist it will get created. Dim pane As MsVsShell.ToolWindowPane = Me.FindToolWindow(GetType(PersistedWindowPane), 0, True) If pane Is Nothing Then End If  
  
    ```  
  
    ```c#  
    // Get the 1 (index 0) and only instance of our tool window. // If it does not already exist it will get created. MsVsShell.ToolWindowPane pane =     this.FindToolWindow(typeof(PersistedWindowPane), 0, true); if (pane == null) {  
    ```  
  
4.  도구 창에서 도구 창 프레임을 가져옵니다.  
  
    ```vb#  
    Dim frame As IVsWindowFrame = TryCast(pane.Frame, IVsWindowFrame) If frame Is Nothing Then End If  
  
    ```  
  
    ```c#  
    IVsWindowFrame frame = pane.Frame as IVsWindowFrame; if (frame == null) {  
    ```  
  
5.  도구 창을 표시합니다.  
  
    ```vb#  
    ' Bring the tool window to the front and give it focus ErrorHandler.ThrowOnFailure(frame.Show())  
  
    ```  
  
    ```c#  
    // Bring the tool window to the front and give it focus ErrorHandler.ThrowOnFailure(frame.Show());  
    ```