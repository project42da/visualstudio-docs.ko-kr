---
title: '방법: 비동기 Visual Studio 서비스를 제공 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8741779cf96cb970f3ebc4907443b85ced5b80c0
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>방법: 비동기 Visual Studio 서비스를 제공 합니다.
UI 스레드를 차단 하지 않고 서비스를 가져올 하려는 경우 비동기 서비스 만들고 백그라운드 스레드에서 패키지를 로드 해야 합니다. 이 목적을 위해 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage> 아닌 <xref:Microsoft.VisualStudio.Shell.Package>, 비동기 패키지의 특별 한 비동기 메서드 사용 하 여 서비스를 추가 합니다.
  
 동기 Visual Studio 서비스를 제공 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 서비스 제공](../extensibility/how-to-provide-a-service.md)합니다.  
  
## <a name="implementing-an-asynchronous-service"></a>비동기 서비스 구현  
  
1.  VSIX 프로젝트를 만듭니다 (**파일 > 새로 만들기 > 프로젝트 > Visual C# > Extensiblity > VSIX 프로젝트**). 프로젝트 이름을 **TestAsync**합니다.  
  
2.  VSPackage 프로젝트에 추가 합니다. 프로젝트 노드를 선택는 **솔루션 탐색기** 클릭 **추가 > 새 항목 > Visual C# 항목 > 확장성 > Visual Studio 패키지**합니다. 이 파일의 이름을 **TestAsyncPackage.cs**합니다.  
  
3.  TestAsyncPackage.cs를 패키지가 아닌 AsyncPackage에서 상속 하도록 패키지를 변경 합니다.  
  
    ```csharp  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  서비스를 구현 하려면 세 가지 형식을 만들려면:  
  
    -   서비스를 식별 하는 인터페이스입니다. 이러한 인터페이스의 대부분은 빈, 즉, 서로 메서드가 없는 서비스를 쿼리 하기 위해 사용 되는 합니다.
  
    -   서비스 인터페이스를 설명 하는 인터페이스입니다. 이 인터페이스에 메서드를 구현 해야 합니다.  
  
    -   서비스와 서비스 인터페이스를 구현 하는 클래스입니다.  
  
5.  다음 예제에서는 세 가지 종류의 기본 구현을 보여 줍니다. 서비스 클래스의 생성자는 서비스 공급자를 설정 해야 합니다. 이 예제 패키지 코드 파일에 서비스를 추가 합니다.  
  
6.  다음 추가 문을 사용 하 여 패키지 파일:  
  
    ```csharp  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;
    using Microsoft.VisualStudio.Threading;
    using IAsyncServiceProvider = Microsoft.VisualStudio.Shell.IAsyncServiceProvider;
    using Task = System.Threading.Tasks.Task;
    ```  
  
7.  여기에 비동기 서비스 구현입니다. 생성자에서 동기 서비스 공급자 보다는 비동기 서비스 공급자를 설정 해야 하는 참고:  
  
    ```csharp
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private IAsyncServiceProvider asyncServiceProvider;  
        
        public TextWriterService(IAsyncServiceProvider provider)  
        {
            // constructor should only be used for simple initialization
            // any usage of Visual Studio service, expensive background operations should happen in the
            // asynchronous InitializeAsync method for best performance
            asyncServiceProvider = provider;  
        }
        
        public async Task InitializeAsync(CancellationToken cancellationToken)
        {
            await TaskScheduler.Default;
            // do background operations that involve IO or other async methods

            await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);               
            // query Visual Studio services on main thread unless they are documented as free threaded explicitly.
            // The reason for this is the final cast to service interface (such as IVsShell) may involve COM operations to add/release references.

            IVsShell vsShell = this.asyncServiceProvider.GetServiceAsync(typeof(SVsShell)) as IVsShell;
            // use Visual Studio services to continue initialization
        }
        
        public async Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
    }  

    public interface STextWriterService  
    {  
    }  
    
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
    }  
    ```  
  
## <a name="registering-a-service"></a>서비스를 등록 하는 중  
 서비스를 등록 하려면 추가 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 서비스를 제공 하는 패키지에 있습니다. 패키지와 서비스 모두 비동기 로드를 지원 하는지 확인 해야 할 서로 다른 동기 서비스 등록, 있습니다.
  
-   추가 해야 합니다는 **AllowsBackgroundLoading = true** 필드는 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 참조는 PackageRegistrationAttribute에 대 한 자세한 내용은 패키지를 비동기적으로 초기화 되도록 [등록 하 고 Vspackage의 등록을 취소](../extensibility/registering-and-unregistering-vspackages.md)합니다.  
  
-   추가 해야 합니다는 **IsAsyncQueryable = true** 필드는 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 서비스 인스턴스를 비동기적으로 초기화할 수 있도록 합니다.

 비동기 서비스 등록 AsyncPackage의 예는 다음과 같습니다.
  
```csharp  
[ProvideService((typeof(STextWriterService)), IsAsyncQueryable = true)]  
[ProvideAutoLoad(UIContextGuids80.SolutionExists, PackageAutoLoadFlags.BackgroundLoad)]  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]   
[Guid(TestAsyncPackage.PackageGuidString)]  
public sealed class TestAsyncPackage : AsyncPackage  
{. . . }  
```  
  
## <a name="adding-a-service"></a>서비스 추가  
  
1.  TestAsyncPackage.cs을에서 제거 된 `Initialize()` 메서드와 재정의 `InitializeAsync()` 메서드. 서비스를 추가 하 고는 서비스를 만드는 콜백 메서드를 추가 합니다. 서비스를 추가 하는 비동기 이니셜라이저의 예는 다음과 같습니다.  
  
    ```csharp
    protected override async Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);
    }  
  
    ```  
  
2.  Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll에 대 한 참조를 추가 합니다.  
  
3.  콜백 메서드를 만들어 서비스를 반환 하는 비동기 메서드로 구현 합니다.  
  
    ```csharp  
    public async Task<object> CreateTextWriterService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        TextWriterService service = new TextWriterService(this);  
        await service.InitializeAsync(cancellationToken);
        return service;
    }  
  
    ```  
  
## <a name="using-a-service"></a>서비스를 사용 하 여  
 이제 서비스를 가져오고 해당 메서드를 사용 하 여 수 있습니다.  
  
1.  이 이니셜라이저의 보여 주 겠지만 있지만 서비스를 사용 하려는 서비스 위치를 가져올 수 있습니다.  
  
    ```csharp  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync(<userpath>), "this is a test");  
    }  
  
    ```  
  
     변경에 반드시  *\<userpath >* 파일 이름 및 컴퓨터에 쉽게 알아볼 수 있는 경로!  
  
2.  빌드 및 코드를 실행 합니다. Visual Studio의 실험적 인스턴스가 나타나면 솔루션을 엽니다. 이렇게 하면 autoload AsyncPackage 됩니다. 이니셜라이저 실행 되 면 사용자가 지정한 위치에 파일을 찾아야 합니다.  
  
## <a name="using-an-asynchronous-service-in-a-command-handler"></a>비동기 서비스를 사용 하 여 명령 처리기에서  
 메뉴 명령에는 비동기 서비스를 사용 하는 방법의 예를 들면 다음과 같습니다. 다른 동기 메서드에서 서비스를 사용 하려면 여기에 표시 된 프로시저를 사용할 수 있습니다.  
  
1.  프로젝트에 메뉴 명령을 추가 합니다. (에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추를 선택한 선택 **추가 / 새 항목 / 확장성 사용자 지정 명령 /**.) 명령 파일 이름을 **TestAsyncCommand.cs 합니다.**  
  
2.  사용자 지정 명령 템플릿을 다시 추가 `Initialize()` 메서드 명령을 초기화 하기 위해 TestAsyncPackage.cs 파일에 있습니다. Initialize () 메서드에서 명령을 초기화 하는 줄을 복사 합니다. 다음과 같이 표시됩니다.  
  
    ```csharp
    TestAsyncCommand.Initialize(this);  
    ```  
  
     이 줄을 이동는 `InitializeAsync()` AsyncPackageForService.cs 파일에서 메서드. 레지스트리를 사용 하 여 명령 초기화 되기 전에 주 스레드를 전환 해야 합니다는 비동기 초기화에는이 이므로 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>합니다. 이 이제 다음과 같이 표시 됩니다.  
  
    ```csharp  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  

        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync((<userpath>, "this is a test");  
  
        await this.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);  
        TestAsyncCommand.Initialize(this);
    }  
  
    ```  
  
3.  삭제 된 `Initialize()` 메서드.  
  
4.  TestAsyncCommand.cs 파일에서 찾습니다는 `MenuItemCallback()` 메서드. 메서드의 본문을 삭제 합니다.  
  
5.  using 문을 추가합니다.  
  
    ```csharp 
    using System.IO;  
    ```  
  
6.  비동기 메서드를 라는 추가 `UseTextWriterAsync()`, 서비스를 가져오고 해당 메서드를 사용 하 여:  
  
    ```csharp  
    private async System.Threading.Tasks.Task UseTextWriterAsync()  
    {  
        // Query text writer service asynchronously to avoid a blocking call.
        ITextWriterService textService =   
           await AsyncServiceProvider.GlobalProvider.GetServiceAsync(typeof(STextWriterService))  
              as ITextWriterService;  

        // don't forget to change <userpath> to a local path  
        await textService.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  이 메서드를 호출 하는 `MenuItemCallback()` 메서드:  
  
    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        UseTextWriterAsync();  
    }  
  
    ```  
  
8.  솔루션을 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 되 면 이동는 **도구** 메뉴를 찾습니다는 **호출 TestAsyncCommand** 메뉴 항목입니다. 단추를 클릭 하는 경우에 TextWriterService 지정한 파일에 씁니다. (필요가 없습니다 솔루션을 열고 명령을 호출 또한을 사용 하면 패키지를 로드 하기 때문에.)  
  
## <a name="see-also"></a>참고 항목  
 [서비스 사용 및 제공](../extensibility/using-and-providing-services.md)
