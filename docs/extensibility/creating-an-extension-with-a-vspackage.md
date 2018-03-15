---
title: "VSPackage를 사용 하 여 확장을 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cc5e08-4897-44f2-8309-e3478f1f999e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: df971bdf72ff52cfa6343b6237de072238087ac4
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="creating-an-extension-with-a-vspackage"></a>VSPackage를 사용 하 여 확장 만들기
이 연습에서는 VSIX 프로젝트를 만들고 VSPackage 프로젝트 항목을 추가 하는 방법을 보여 줍니다. 메시지 상자를 표시 하려면 UI 셸 서비스를 가져올 수는 VSPackage를 사용 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-vspackage"></a>VSPackage 만들기  
  
1.  라는 VSIX 프로젝트를 **FirstPackage**합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자의 **Visual C# / 확장성**합니다.  
  
2.  프로젝트를 열 때 라는 Visual Studio 패키지 항목 템플릿을 추가 **FirstPackage**합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **Visual Studio 패키지**합니다. 에 **이름** 창의 맨 아래에 필드에서 명령 파일 이름을 변경한 **FirstPackage.cs**합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
     Visual Studio의 실험적 인스턴스가 표시 됩니다. 실험적 인스턴스에 대 한 자세한 내용은 참조 [의 실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.  
  
4.  실험적 인스턴스를 열고는 **도구 / 확장명 및 업데이트** 창. 표시 됩니다는 **FirstPackage** 여기 확장 합니다. (열면 **확장명 및 업데이트** Visual Studio에 해당 하는 작업 인스턴스를에 표시 되지 않습니다 **FirstPackage**).  
  
## <a name="loading-the-vspackage"></a>VSPackage를 로드합니다.  
 이 시점에서 확장 로드 되지 않으면 로드 하는 것이 없으므로 합니다. (도구 창 열기 메뉴 명령 클릭) UI 또는 VSPackage 특정 UI 컨텍스트에서 로드 해야 함을 지정 하 여 상호 작용할 때 일반적으로 확장을 로드할 수 있습니다. Vspackage 및 UI 컨텍스트를 로드 하는 방법에 대 한 자세한 내용은 참조 [로드 Vspackage](../extensibility/loading-vspackages.md)합니다. 이 절차에서는 솔루션을 열 때 VSPackage를 로드 하는 방법을 살펴보겠습니다.  
  
1.  FirstPackage.cs 파일을 엽니다. FirstPackage 클래스의 선언을 찾습니다. 기존 특성 다음 코드로 바꿉니다.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid(FirstPackage.PackageGuidString)]  
    public sealed class FirstPackage : Package  
    ```  
  
2.  VSPackage에 로드 된 것을 알 수 있는 메시지를 추가 해 보겠습니다. VSPackage 요소가 배치 된 후에 Visual Studio 서비스를 가져올 수 때문에이 수행 하려면 VSPackage의 initialize () 메서드를 사용 합니다. (서비스에 대 한 자세한 내용은 참조 [하는 방법: 서비스 가져오기](../extensibility/how-to-get-a-service.md).) 가져오는 코드로 FirstPackage의 initialize () 메서드를 대체는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스를 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스 및 호출 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowMessageBox%2A> 메서드.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        base.Initialize();  
  
        IVsUIShell uiShell = (IVsUIShell)GetService(typeof(SVsUIShell));  
        Guid clsid = Guid.Empty;  
        int result;  
        Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(uiShell.ShowMessageBox(  
            0,  
            ref clsid,  
            "FirstPackage",  
             string.Format(CultureInfo.CurrentCulture, "Inside {0}.Initialize()", this.GetType().FullName),  
            string.Empty,  
            0,  
            OLEMSGBUTTON.OLEMSGBUTTON_OK,  
            OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST,  
            OLEMSGICON.OLEMSGICON_INFO,  
            0,  
            out result));  
    }  
    ```  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
4.  실험적 인스턴스에서 솔루션을 엽니다. 라고 표시 하는 메시지 상자가 표시 되어야 **첫 번째 패키지 내 initialize ()**합니다.