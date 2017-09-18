---
title: "다중 인스턴스 도구 창 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "다중"
  - "도구 창"
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 다중 인스턴스 도구 창 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

도구 창을 여러 개 동시에 열 수 있도록 프로그래밍할 수 있습니다. 기본적으로 도구 창을 열고 인스턴스가 하나만 있을 수 있습니다.  
  
 다중 인스턴스 도구 창을 사용 하면 여러 관련된 리소스의 동시에 정보를 표시할 수 있습니다. 예를 들어, 여러 줄에 배치할 수 있습니다 <xref:System.Windows.Forms.TextBox> 프로그래밍 세션 동안 여러 코드 조각의 동시에 사용할 수 있도록 다중 인스턴스 도구 창에서 제어 합니다. 배치할 수는 또한 예를 들어 한 <xref:System.Windows.Forms.DataGrid> 제어 하 고 드롭다운 목록 상자에 다중 인스턴스 도구 창을 여러 실시간 데이터 소스를 동시에 추적할 수 있도록 합니다.  
  
## Basic \(인스턴스\) 도구 창 만들기  
  
1.  라는 프로젝트 **MultiInstanceToolWindow** 라는 사용자 지정 도구 창 항목 템플릿을 추가 하 고 VSIX 템플릿을 사용 하 여 **MIToolWindow**합니다.  
  
    > [!NOTE]
    >  도구 창으로 확장을 만들기에 대 한 자세한 내용은 참조 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
## 도구 창 다중 인스턴스 만들기  
  
1.  열기는 **MIToolWindowPackage.cs** 파일을 찾아서는 `ProvideToolWindow` 특성입니다. 및 `MultiInstances=true` 매개 변수를 다음 예와에서 같이 합니다.  
  
    ```c#  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackageGuids.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  MIToolWindowCommand.cs 파일에서 ShowToolWindos\(\) 메서드를 찾습니다. 이 메서드를 호출 하는 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 메서드 집합과 해당 `create` 플래그를 `false` 를 기존 도구 창 인스턴스를 통해 사용할 수 있는 될 때까지 반복 됩니다 `id` 를 찾을 수 있습니다.  
  
3.  도구 창 인스턴스를 만들려면 호출의 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 메서드 집합과 해당 `id` 을 사용할 수 있는 값 및 해당 `create` 플래그를 `true`합니다.  
  
     기본적으로 값은 `id` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 메서드는 `0`합니다. 이렇게 하면 단일 인스턴스 도구 창을 있습니다. 호스팅 되도록 개 이상의 인스턴스에 대 한 모든 인스턴스는 자체 고유 해야 `id`합니다.  
  
4.  호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 메서드를는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 에서 반환 되는 개체는 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> 도구 창 인스턴스의 속성입니다.  
  
5.  기본적으로는 `ShowToolWindow` 도구 창 항목 템플릿에 의해 만들어진 메서드는 단일 인스턴스 도구 창을 만듭니다. 다음 예제를 수정 하는 방법을 보여 줍니다는 `ShowToolWindow` 여러 인스턴스를 만드는 방법.  
  
    ```c#  
    private void ShowToolWindow(object sender, EventArgs e)  
    {  
        for (int i = 0; i < 10; i++)  
        {  
            ToolWindowPane window = this.package.FindToolWindow(typeof(MIToolWindow), i, false);  
            if (window == null)  
            {  
                // Create the window with the first free ID.   
                window = (ToolWindowPane)this.package.FindToolWindow(typeof(MIToolWindow), i, true);  
                if ((null == window) || (null == window.Frame))  
                {  
                    throw new NotSupportedException("Cannot create tool window");  
                }  
  
            IVsWindowFrame windowFrame = (IVsWindowFrame)window.Frame;  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(windowFrame.Show());  
            break;  
            }  
        }  
    }  
    ```