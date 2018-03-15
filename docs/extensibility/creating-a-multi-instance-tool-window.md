---
title: "다중 인스턴스 도구 창을 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multi
- tool windows
ms.assetid: 4a7872f1-acc9-4f43-8932-5a526b36adea
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e13fb299d513f045c4c7c339a9c6602890079e40
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="creating-a-multi-instance-tool-window"></a>다중 인스턴스 도구 창 만들기
여러 인스턴스를 동시에 열릴 수 있도록 도구 창을 프로그래밍할 수 있습니다. 기본적으로 도구 창을 열고 하나의 인스턴스만을 가질 수 있습니다.  
  
 다중 인스턴스 도구 창을 사용 하는 경우에 여러 관련된 리소스의 동시에 정보를 표시할 수 있습니다. 예를 들어 여러 줄에 배치할 수 있습니다 <xref:System.Windows.Forms.TextBox> 프로그래밍 세션 중 몇 가지 코드 조각의 동시에 사용할 수 있도록 다중 인스턴스 도구 창에서 제어 합니다. 또한 예를 들어를 배치할 수 있습니다는 <xref:System.Windows.Forms.DataGrid> 컨트롤 및 드롭다운 목록 상자에 다중 인스턴스 도구 창 여러 실시간 데이터 소스를 동시에 추적할 수 있도록 합니다.  
  
## <a name="creating-a-basic-single-instance-tool-window"></a>Basic (인스턴스) 도구 창 만들기  
  
1.  라는 프로젝트 **MultiInstanceToolWindow** VSIX 서식 파일을 사용 하 고 명명 된 사용자 지정 도구 창 항목 템플릿을 추가 **MIToolWindow**합니다.  
  
    > [!NOTE]
    >  도구 창을 사용 된 확장을 만드는 방법에 대 한 자세한 내용은 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
## <a name="making-a-tool-window-multi-instance"></a>도구 창 다중 인스턴스 만들기  
  
1.  열기는 **MIToolWindowPackage.cs** 파일을 찾을 `ProvideToolWindow` 특성입니다. 및 `MultiInstances=true` 다음 예제와 같이 매개 변수:  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
        [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
        [ProvideMenuResource("Menus.ctmenu", 1)]  
        [ProvideToolWindow(typeof(MultiInstanceToolWindow.MIToolWindow), MultiInstances = true)]  
        [Guid(MIToolWindowPackage.PackageGuidString)]  
        public sealed class MIToolWindowPackage : Package  
    {. . .}  
    ```  
  
2.  MIToolWindowCommand.cs 파일에서 ShowToolWindos() 메서드를 찾습니다. 이 메서드를 호출 하는 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 메서드 집합과 해당 `create` 나타내는 플래그입니다. `false` 기존 도구 창의 인스턴스를 통해 사용 가능한 될 때까지 반복 됩니다 되도록 `id` 를 찾을 수입니다.  
  
3.  도구 창의 인스턴스를 만들려면 호출는 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 메서드 집합과 해당 `id` 하는 사용 가능한 값 및 해당 `create` 플래그를 `true`합니다.  
  
     기본적으로 값은 `id` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Package.FindToolWindow%2A> 방법은 `0`합니다. 이 값이 단일 인스턴스 도구 창을으로 열립니다. 둘 이상의 인스턴스를 호스팅할 수에 대 한 모든 인스턴스에 자체 고유 해야 `id`합니다.  
  
4.  호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 에서 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> 에서 반환 되는 개체는 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane.Frame%2A> 도구 창 인스턴스의 속성입니다.  
  
5.  기본적으로는 `ShowToolWindow` 도구 창 항목 템플릿에 의해 만들어진 메서드는 단일 인스턴스 도구 창을 만듭니다. 수정 하는 방법을 보여 주는 다음 예제는 `ShowToolWindow` 메서드 여러 인스턴스를 만듭니다.  
  
    ```csharp  
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