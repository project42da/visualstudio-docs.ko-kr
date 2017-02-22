---
title: "VSPackage를 사용 하 여 확장 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c0cc5e08-4897-44f2-8309-e3478f1f999e
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# VSPackage를 사용 하 여 확장 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 VSIX 프로젝트를 만들고 VSPackage 프로젝트 항목을 추가 하는 방법을 보여 줍니다. 메시지 상자를 표시 하기 위해 UI 셸로 서비스를 작동 하 여 VSPackage를 사용 합니다.  
  
## 필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## VSPackage 만들기  
  
1.  라는 이름의 VSIX 프로젝트 **FirstPackage**합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  프로젝트를 열면 라는 Visual Studio 패키지 항목 템플릿을 추가 **FirstPackage**합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **Visual Studio 패키지**합니다. 에 **이름** 창의 맨 아래에 필드, 명령 파일 이름을 **FirstPackage.cs**합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
     Visual Studio의 실험적 인스턴스가 표시 됩니다. 실험적 인스턴스에서 대 한 자세한 내용은 참조 [실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.  
  
4.  실험적 인스턴스를 열고는 **도구 \/ 확장 및 업데이트** 창입니다. 표시 되어야는 **FirstPackage** 여기 확장 합니다. \(열면 **확장 및 업데이트** 표시 되지 않습니다 Visual Studio의 작업 인스턴스에, **FirstPackage**\).  
  
## VSPackage를 로드합니다.  
 이 시점에서 확장 로드 되지 않으면 로드 하는 아무 것도 있기 때문입니다. \(도구 창, 메뉴 명령 클릭\) UI 또는 특정 UI 컨텍스트에서 VSPackage가 로드를 지정 하 여 상호 작용할 때 일반적으로 확장을 로드할 수 있습니다. Vspackage 및 UI 컨텍스트를 로드 하는 방법에 대 한 자세한 내용은 참조 [Vspackage를 로드합니다.](../extensibility/loading-vspackages.md)합니다. 이 절차에서는 솔루션을 열 때 VSPackage를 로드 하는 방법을 살펴보겠습니다.  
  
1.  FirstPackage.cs 파일을 엽니다. FirstPackage 클래스의 선언을 찾습니다. 기존 특성을 다음으로 바꿉니다.  
  
    ```c#  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid(FirstPackageGuids.PackageGuidString)]  
    public sealed class FirstPackage : Package  
    ```  
  
2.  VSPackage가 로드를 알 수 있도록 하는 메시지를 추가 해 보겠습니다. VSPackage 요소가 배치 된 후에 Visual Studio 서비스를 가져올 수 있으므로이 수행 하는 VSPackage initialize \(\) 메서드를 사용 합니다. \(서비스를 시작 하는 방법에 대 한 자세한 내용은 참조 [방법: 서비스 가져오기](../extensibility/how-to-get-a-service.md).\) FirstPackage의 initialize \(\) 메서드를 가져오는 코드를 바꿉니다는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell> 서비스를 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell> 인터페이스를 호출 하 고 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ShowMessageBox%2A> 메서드.  
  
    ```c#  
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
  
4.  실험적 인스턴스에서 솔루션을 엽니다. 알리는 메시지 상자가 표시 됩니다 **첫 번째 패키지 내 initialize \(\)**합니다.