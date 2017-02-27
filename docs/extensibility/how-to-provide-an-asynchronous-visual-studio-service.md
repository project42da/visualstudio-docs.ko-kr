---
title: "방법: Visual Studio 비동기 서비스를 제공 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: Visual Studio 비동기 서비스를 제공 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

UI 스레드를 차단 하지 않고 서비스를 가져올 하려는 경우 비동기 서비스 만들고 백그라운드 스레드에서 패키지를 로드 해야 합니다. 이 목적을 위해 사용할 수는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage> 대신 <xref:Microsoft.VisualStudio.Shell.Package>, 특별 한 비동기 메서드를 비동기 패키지와 서비스를 추가 하 고  
  
 동기 Visual Studio 서비스를 제공 하는 방법에 대 한 정보를 참조 하십시오. [방법: 서비스를 제공 합니다.](../extensibility/how-to-provide-a-service.md)합니다.  
  
## 비동기 서비스를 구현합니다.  
  
1.  VSIX 프로젝트를 만듭니다 \(**파일 \/ 새 \/ 프로젝트 \/ Visual C\# \/ Extensiblity \/ VSIX 프로젝트**\). 프로젝트 이름을 **TestAsync**합니다.  
  
2.  VSPackage 프로젝트에 추가 합니다. 프로젝트 노드를 선택 된 **솔루션 탐색기** 클릭 **추가 \/ 새 항목 \/ Visual C\# 항목 \/ 확장성 \/ Visual Studio 패키지**합니다. 이 파일의 이름을 **TestAsyncPackage.cs**합니다.  
  
3.  TestAsyncPackage.cs를 패키지가 아닌 AsyncPackage에서 상속 하도록 패키지를 변경 합니다.  
  
    ```c#  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  서비스를 구현 하려면 세 가지 형식을 만드는 필요 합니다.  
  
    -   서비스를 설명 하는 인터페이스입니다. 이러한 인터페이스의 대부분은 빈를 즉, 이러한 메서드가 없습니다.  
  
    -   서비스 인터페이스를 설명 하는 인터페이스입니다. 이 인터페이스에 메서드를 구현 해야 합니다.  
  
    -   서비스와 서비스 인터페이스를 구현 하는 클래스입니다.  
  
5.  다음 예제에서는 세 가지 종류의 기본 구현을 보여 줍니다. 서비스 클래스의 생성자는 서비스 공급자를 설정 해야 합니다. 이 예제 패키지 코드 파일에 서비스를 추가 합니다.  
  
6.  다음 코드를 추가 문을 사용 하 여 패키지 파일:  
  
    ```c#  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;  
    ```  
  
7.  비동기 서비스 구현은 다음과 같습니다. 참고 생성자에서 동기 서비스 공급자 보다는 비동기 서비스 공급자를 설정 해야 합니다.  
  
    ```  
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private Microsoft.VisualStudio.Shell.IAsyncServiceProvider serviceProvider;  
        public TextWriterService(Microsoft.VisualStudio.Shell.IAsyncServiceProvider provider)  
        {  
            serviceProvider = provider;  
        }  
        public async System.Threading.Tasks.Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
        public TaskAwaiter GetAwaiter()  
        {  
            return new TaskAwaiter();  
        }  
    }  
    public interface STextWriterService  
    {  
    }  
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
        TaskAwaiter GetAwaiter();  
    }  
    ```  
  
## 서비스를 등록 하는 중  
 서비스를 등록 하려면 추가 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 서비스를 제공 하는 패키지에 있습니다. 서비스를 등록 하면 동기에서 두 가지 차이점이 있습니다.  
  
-   자동 로드 하 고 있다면 추가 해야 패키지를는 <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags> BackgroundLoad 값 특성입니다. 자동 로드 VSPackages에 대 한 자세한 내용은 참조 [Vspackage를 로드합니다.](../extensibility/loading-vspackages.md)합니다.  
  
-   추가 해야는 **AllowsBackgroundLoading \= true** 필드는 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>합니다. PackageRegistrationAttribute에 대 한 자세한 내용은 참조 [Vspackage를 등록 및 등록 취소](../extensibility/registering-and-unregistering-vspackages.md)합니다.  
  
 다음은 한 AsyncPackage 비동기 서비스 등록의 예::  
  
```c#  
[ProvideService((typeof(STextWriterService)), IsAsyncQueryable = true)]  
[ProvideAutoLoad(UIContextGuids80.SolutionExists, PackageAutoLoadFlags.BackgroundLoad)]  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]   
[Guid(TestAsyncPackage.PackageGuidString)]  
public sealed class TestAsyncPackage : AsyncPackage  
{. . . }  
```  
  
## 서비스 추가  
  
1.  TestAsyncPackage.cs를에서 제거 된 `Initialize()` 메서드와 재정의 `InitializeAsync()` 메서드. 서비스를 추가 하 고는 서비스를 만들 수는 콜백 메서드를 추가 합니다. 서비스를 추가 하는 비동기 이니셜라이저의 예는 다음과 같습니다.  
  
    ```  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
2.  Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll에 대 한 참조를 추가 합니다.  
  
3.  비동기 메서드로 만들어 서비스를 반환 하는 콜백 메서드를 구현 합니다.  
  
    ```c#  
    public async System.Threading.Tasks.Task<object> CreateService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        STextWriterService service = null;  
        await System.Threading.Tasks.Task.Run(() => {  
                    service = new TextWriterService(this);  
             });  
  
        return service;  
    }  
  
    ```  
  
## 서비스를 사용 하 여  
 이제 서비스를 가져오고 해당 메서드를 사용 하 여 수 있습니다.  
  
1.  이니셜라이저의이 알아봅니다 하지만 서비스를 사용 하려는 서비스 위치를 가져올 수 있습니다.  
  
    ```c#  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await writer.WriteLineAsync(<userpath>), "this is a test");  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
     원본을 변경 해야 *\< userpath \>* 파일 이름 및 컴퓨터에 맞는 경로\!  
  
2.  빌드 및 코드를 실행 합니다. Visual Studio의 실험적 인스턴스에서 나타나면 솔루션을 엽니다. 이렇게 하면 자동 로드를 AsyncPackage 됩니다. 이니셜라이저가 실행 되 면 사용자가 지정한 위치에는 파일을 찾습니다.  
  
## 명령 처리기의 비동기 서비스를 사용 하 여  
 메뉴 명령에는 비동기 서비스를 사용 하는 방법의 예를 들면 다음과 같습니다. 다른 동기 메서드를 서비스를 사용 하 여 여기에 표시 된 절차를 사용할 수 있습니다.  
  
1.  프로젝트에 메뉴 명령을 추가 합니다. \(에 **솔루션 탐색기**, 를 선택 하 고 프로젝트 노드를 마우스 오른쪽 단추를 선택 **추가 \/ 새 항목 \/ 확장성 \/ 사용자 지정 명령**.\) 명령 파일 이름을 **TestAsyncCommand.cs.**  
  
2.  사용자 지정 명령 템플릿을 다시 추가 `Initialize()` 메서드 명령을 초기화 하기 위해 TestAsyncPackage.cs 파일에 있습니다. Initialize \(\) 메서드에서 명령 초기화 하는 행을 복사 합니다. 다음과 같이 같아야 합니다.  
  
    ```  
    TestAsyncCommand.Initialize(this);  
    ```  
  
     이 줄을 이동는 `InitializeAsync()` AsyncPackageForService.cs 파일에서 메서드에 있습니다. 레지스트리를 사용 하 여 명령을 초기화 하기 전에 주 스레드를 전환 해야 이므로 비동기 초기화에, <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>합니다. 이제 다음과 같이 것이 보여야 합니다.  
  
    ```c#  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        TestAsyncCommand.Initialize(this);    
  
        this.AddService(typeof(STextWriterService), CreateService);  
  
        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await writer.WriteLineAsync((<userpath>, "this is a test");  
  
        await base.InitializeAsync(cancellationToken, progress);  
    }  
  
    ```  
  
3.  삭제 된 `Initialize()` 메서드.  
  
4.  TestAsyncCommand.cs 파일에서 찾기는 `MenuItemCallback()` 메서드. 메서드의 본문을 삭제 합니다.  
  
5.  추가 하 여 문:  
  
    ```  
    using System.IO;  
    ```  
  
6.  비동기 메서드는 추가 `GetAsyncService()`, 를 서비스를 가져오고 해당 메서드를 사용 하 여:  
  
    ```c#  
    private async System.Threading.Tasks.Task GetAsyncService()  
    {  
        ITextWriterService textService =   
           this.ServiceProvider.GetService(typeof(STextWriterService))  
              as ITextWriterService;  
        // don’t forget to change <userpath> to a local path  
        await writer.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  이 메서드를 호출 하는 `MenuItemCallback()` 메서드:  
  
    ```  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        GetAsyncService();  
    }  
  
    ```  
  
8.  솔루션을 빌드하고 디버깅을 시작 합니다. Visual Studio의 실험적 인스턴스가 표시 되 면는 **도구** 메뉴를 찾고는 **호출 TestAsyncCommand** 메뉴 항목입니다. 여기를 클릭 하는 경우에 TextWriterService 지정한 파일에 씁니다. \(필요가 없습니다 솔루션을 열고 또한 로드할 패키지를 사용 하면 명령을 호출 하기 때문에.\)  
  
## 참고 항목  
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)