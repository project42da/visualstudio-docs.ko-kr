---
title: "방법: AsyncPackage를 사용 하 여 백그라운드에서 Vspackage를 로드 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
---
# 방법: AsyncPackage를 사용 하 여 백그라운드에서 Vspackage를 로드 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

디스크 I\/O 로드 되 고 VS 패키지 초기화 될 수 있습니다. 이러한 I\/O는 UI 스레드에서 경우 응답성 문제가 발생할 수 있습니다. 이 문제를 해결 하려면 Visual Studio 2015 도입는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage> 클래스는 백그라운드 스레드에서 로드 수 있도록 합니다.  
  
## AsyncPackage 만들기  
 VSIX 프로젝트를 만들어서 시작할 수 있습니다 \(**파일 \/ 새 \/ 프로젝트 \/ Visual C\# \/ 확장성 \/ VSIX 프로젝트**\) VSPackage 프로젝트에 추가 하 고 \(프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **항목 추가\/새로 만들기 \/ C\# 항목\/확장성\/Visual Studio 패키지**\). 그런 다음 서비스 만들고 패키지에 해당 서비스를 추가할 수 있습니다.  
  
1.  패키지를 파생 시키는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage>합니다.  
  
2.  서비스를 쿼리 하는 패키지 로드를 발생할 수 있습니다 제공 하는 경우:  
  
     Visual Studio에 패키지 임을 나타내려면 백그라운드에 로드 하기에 안전 하 고이 동작을 선택 하 여 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 설정 해야 **AllowsBackgroundLoading** 속성을 특성 생성자에서 true로 합니다.  
  
    ```c#  
    [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]  
  
    ```  
  
     설정 해야 Visual Studio에는 것은 안전 백그라운드 스레드 서비스를 인스턴스화할 수에 대해서는 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> 속성을 true로는 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 생성자입니다.  
  
    ```c#  
    [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]  
  
    ```  
  
3.  UI 컨텍스트를 통해 로드 하는 경우 지정 해야 **PackageAutoLoadFlags.BackgroundLoad** 에 대 한는 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 또는 플래그에 값 \(0x2\) 패키지의 자동 로드 항목의 값이 기록 됩니다.  
  
    ```c#  
    [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]  
  
    ```  
  
4.  재정의 해야 할 일이 비동기 초기화를 설정한 경우 <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A>합니다. 제거는 **initialize \(\)** VSIX 서식 파일에서 제공 하는 방법입니다. \(의 **initialize \(\)** 메서드에서 **AsyncPackage** 는 봉인 클래스\). 모든 사용할 수는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> 비동기 서비스 패키지를 추가 하는 방법입니다.  
  
     참고: 호출할 **기본입니다. InitializeAsync\(\)**, 를 소스 코드를 변경할 수 있습니다.  
  
    ```c#  
    await base.InitializeAsync(cancellationToken, progress);  
    ```  
  
5.  주의 해야 Rpc \(제거 프로시저 호출\)를 만들지 않는 비동기 초기화 코드에서 \(에서 **InitializeAsync**\). 호출할 때 발생할 수 있습니다 이러한 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 직접 또는 간접적으로 합니다.  사용 하 여 UI 스레드는 차단 동기화 로드 필요한 경우 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>합니다. 기본 차단 모델 Rpc를 해제합니다. 이 비동기 작업에서 RPC를 사용 하려고 하면 하면 교착 상태가 UI 스레드는 자체 패키지를 로드할 때까지 대기 하는 경우를 의미 합니다. 일반적인 방법은 같이 사용 하 여 필요한 경우 코드를 UI 스레드로 마샬링하 **참가할 수 있는 작업 팩터리**의 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> 나 RPC를 사용 하지 않는 일부 다른 메커니즘입니다.  사용 하지 않는 **ThreadHelper.Generic.Invoke** 또는 일반적으로 UI 스레드를 얻기 위해 기다리는 호출 스레드를 차단 합니다.  
  
     참고: 사용 하지 않아야 **GetService** 또는 **QueryService** 에 프로그램 **InitializeAsync** 메서드. 역할을 사용 해야 할 경우에 먼저 UI 스레드로 전환 해야 합니다. 사용 하 여 다른 방법은 <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> 에서 프로그램 **AsyncPackage** \(캐스팅 하도록 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider>.\)  
  
 C\#의 경우는 AsyncPackage 만듭니다.  
  
```c#  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]       
[ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]   
public sealed class TestPackage : AsyncPackage   
{   
    protected override Task InitializeAsync(System.Threading.CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)   
    {               
        this.AddService(typeof(SMyTestService), CreateService, true);   
        return Task.FromResult<object>(null);   
    }   
}  
```  
  
## 기존 VSPackage AsyncPackage 변환  
 작업의 대부분은 새를 만드는 방법과 동일 **AsyncPackage**합니다. 1 ~ 5 위 단계를 수행 해야 합니다. 다음에 대해 특별 한 주의 수행 해야 합니다.  
  
1.  제거 하는 **초기화** 재정의에 패키지를 만들었습니다.  
  
2.  교착 상태 방지: 있을 수 Rpc 이제는 백그라운드 스레드에서 발생 하는 코드에서 숨겨집니다. 해야 하는 RPC를 하는 경우 \(예: **GetService**\) 중 하나 \(1\) 주 스레드로 전환 해야, 또는 \(2\) 사용 하 여 비동기 버전의 경우 API 존재 \(예: **GetServiceAsync**\).  
  
3.  스레드를 너무 자주 전환 마십시오. 백그라운드 스레드에서 발생할 수 있는 작업을 지역화 하려고 합니다. 이렇게 하면 로드 시간이 줄어듭니다.  
  
## AsyncPackage에서 서비스를 쿼리합니다.  
 **AsyncPackage** 수도 호출자에 따라 비동기적으로 로드 되지 않을 수 있습니다. 예를 들어,  
  
-   호출자가 호출 된 경우 **GetService** 또는 **QueryService** \(모두 동기 Api\) 또는  
  
-   호출자가 호출 된 경우 **IVsShell::LoadPackage** \(또는 **IVsShell5::LoadPackageWithContext**\) 또는  
  
-   로드 컨텍스트를 UI에 의해 트리거되는 했지만 UI 컨텍스트 메커니즘은 비동기적으로 로드할 수를 지정 하지 않은  
  
 그런 다음 패키지 동기적으로 로드 합니다.  
  
 해당 작업의 완료에 대 한 패키지 여전히는 영업 기회 \(비동기 초기화 단계\)에서 작업 수행 하 여 UI 스레드를 통해 UI 스레드를 차단 됩니다. 호출자에 게 사용 하는 경우 **IAsyncServiceProvider** 서비스에 대해 비동기적으로 쿼리를 다음 로드 및 초기화를 수행 하려면 결과 작업 개체에서 차단 즉시 하지 않도록 비동기적으로 가정 합니다.  
  
 C\#의 경우 서비스를 비동기적으로 쿼리 하는 방법:  
  
```c#  
using Microsoft.VisualStudio.Shell;   
using Microsoft.VisualStudio.Shell.Interop;   
  
IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;   
IMyTestService testService = await ayncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;  
```