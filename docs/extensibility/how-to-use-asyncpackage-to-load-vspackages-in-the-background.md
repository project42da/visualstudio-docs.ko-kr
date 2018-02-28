---
title: "방법: 백그라운드에서 Vspackage를 로드 하려면 AsyncPackage 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.technology: vs-ide-sdk
ms.assetid: dedf0173-197e-4258-ae5a-807eb3abc952
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
ms.workload:
- vssdk
ms.openlocfilehash: 97f21f75020e77cf6780fa71c21eae827940d9ec
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2018
---
# <a name="how-to-use-asyncpackage-to-load-vspackages-in-the-background"></a>방법: AsyncPackage를 사용 하 여 백그라운드에서 Vspackage를 로드 합니다.
디스크 I/O 로드 되 고 VS 패키지 초기화 될 수 있습니다. UI 스레드에서 오류가 발생 해도 이러한 I/O 응답성 문제가 발생할 수 있습니다. 이 문제를 해결 하려면 Visual Studio 2015 도입는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage> 백그라운드 스레드에서 로드 수 있는 클래스입니다.  
  
## <a name="creating-an-asyncpackage"></a>AsyncPackage 만들기  
 VSIX 프로젝트를 만들어서 시작할 수 있습니다 (**파일 > 새로 만들기 > 프로젝트 > Visual C# > 확장성 > VSIX 프로젝트**) VSPackage 프로젝트에 추가 하 고 (프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가/새 항목 / C# 항목 / Extensibility/Visual Studio 패키지**). 그런 다음 서비스 만들고 패키지에 해당 서비스를 추가할 수 있습니다.  
  
1.  패키지를 파생 <xref:Microsoft.VisualStudio.Shell.AsyncPackage>합니다.  
  
2.  서비스를 쿼리 하는 패키지 로드를 발생할 수 있습니다 제공 하는 경우:  
  
     Visual studio 패키지 임을 나타내려면 백그라운드에 로드 하기에 안전 하 고이 동작을 선택 하 여 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 설정 해야 **AllowsBackgroundLoading** 속성을 특성 생성자에서 true로 합니다.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]  
  
    ```  
  
     안전 백그라운드 스레드 서비스를 인스턴스화하는 Visual Studio를 준비 하려면 설정 해야는 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttributeBase.IsAsyncQueryable%2A> 속성을 true로는 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> 생성자입니다.  
  
    ```csharp  
    [ProvideService(typeof(SMyTestService), IsAsyncQueryable = true)]  
  
    ```  
  
3.  UI 컨텍스트를 통해 로드 하는 경우 지정 해야 **PackageAutoLoadFlags.BackgroundLoad** 에 대 한는 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 또는 플래그에 값 (0x2) 패키지의 자동 로드 항목의 값으로 작성 합니다.  
  
    ```csharp  
    [ProvideAutoLoad(UIContextGuid, PackageAutoLoadFlags.BackgroundLoad)]  
  
    ```  
  
4.  재정의 해야 비동기 초기화 작업을 수행 해야 하는 경우 <xref:Microsoft.VisualStudio.Shell.AsyncPackage.InitializeAsync%2A>합니다. 제거는 **initialize ()** VSIX 서식 파일에서 제공 하는 메서드. (의 **initialize ()** 에서 메서드 **AsyncPackage** 는 봉인 클래스). 하나를 사용할 수는 <xref:Microsoft.VisualStudio.Shell.AsyncPackage.AddService%2A> 비동기 서비스 패키지에 추가 하는 방법입니다.  
  
     참고: 호출할 **기본 합니다. InitializeAsync()**, 소스 코드를 변경할 수 있습니다.  
  
    ```csharp  
    await base.InitializeAsync(cancellationToken, progress);  
    ```  
  
5.  주의 해야 Rpc (원격 프로시저 호출)를 만들지 않는 비동기 초기화 코드에서 (에서 **InitializeAsync**). 호출 하는 경우 발생할 수 있습니다 이러한 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 직접 또는 간접적으로 합니다.  UI 스레드를 사용 하 여 호출이 차단 됩니다 동기화 로드 필요할 때 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>합니다. 기본 차단 모델 Rpc를 해제합니다. 이 비동기 작업에서 RPC를 사용 하려고 하면 교착 상태가 UI 스레드는 자체 패키지를 로드할 때까지 대기 하는 경우를 의미 합니다. 다음과 같이 사용 하 여 필요한 경우을 UI 스레드에 코드를 마샬링하는 대신 사용 하는 일반 **참가할 수 있는 작업 팩터리**의 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> 나 RPC를 사용 하지 않는 일부 다른 메커니즘입니다.  사용 하지 마십시오 **ThreadHelper.Generic.Invoke** 또는 일반적으로 호출을 UI 스레드에 얻기 위해 기다리는 스레드를 차단 합니다.  
  
     참고: 사용 하지 않아야 **GetService** 또는 **QueryService** 에 프로그램 **InitializeAsync** 메서드. 역할을 사용 해야 할 경우 먼저 UI 스레드로 전환 해야 합니다. 사용 하는 대체 항목은 <xref:Microsoft.VisualStudio.Shell.AsyncServiceProvider.GetServiceAsync%2A> 에서 프로그램 **AsyncPackage** (로 캐스팅 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IAsyncServiceProvider>.)  
  
 C#의 경우 AsyncPackage 만듭니다.:  
  
```csharp  
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
  
## <a name="convert-an-existing-vspackage-to-asyncpackage"></a>기존 VSPackage AsyncPackage 변환  
 작업의 대부분은 새 만들기와 동일 **AsyncPackage**합니다. 위의 1 ~ 5 단계를 수행 해야 합니다. 다음에서 좀 더 주의 수행 해야 합니다.  
  
1.  제거 해야는 **초기화** 패키지에서 제공 되었던 재정의 합니다.  
  
2.  교착 상태 방지: 있을 수 이제는 백그라운드 스레드에서 발생 하는 사용자 코드에서 Rpc 숨겨져 있습니다. RPC 하는 경우 했는지 확인 해야 할 (예: **GetService**) 중 하나 (1) 주 스레드로 전환 해야 할 또는 (2) 사용 하 여 비동기 버전의 경우 API가 있습니다 (예: **GetServiceAsync**).  
  
3.  너무 자주 스레드 간에 전환 하지 마십시오. 백그라운드 스레드에서 발생할 수 있는 작업 필드를 지역화 하려고 합니다. 이렇게 하면 로드 시간이 줄어듭니다.  
  
## <a name="querying-services-from-asyncpackage"></a>AsyncPackage에서 서비스 쿼리  
 **AsyncPackage** 되었거나 호출자에 따라 비동기적으로 로드 되지 않을 수 있습니다. 예를 들어,  
  
-   호출자에 게 메서드를 호출 하면 **GetService** 또는 **QueryService** (둘 다 동기 Api) 또는  
  
-   호출자에 게 메서드를 호출 하면 **IVsShell::LoadPackage** (또는 **IVsShell5::LoadPackageWithContext**) 또는  
  
-   부하 UI 컨텍스트에 의해 트리거되는 하지만 UI 컨텍스트 메커니즘 비동기적으로 있습니다 로드할 수를 지정 하지 않습니다.  
  
 그런 다음 패키지는 동기적으로 로드 됩니다.  
  
 참고는 패키지에에서 남아 있을 수 있는 기회 (비동기 초기화 단계) UI 스레드에서 작업을 수행할 수 있지만 해당 작업의 완료에 대 한 UI 스레드가 차단 됩니다. 호출자에 게 사용 하는 경우 **IAsyncServiceProvider** 서비스에 대 한 비동기적으로 쿼리를 다음 로드 및 초기화 수행 됩니다 비동기적으로 결과 작업 개체에서 즉시 차단 하지 않는 것으로 가정 합니다.  
  
 C#의 경우 서비스를 비동기적으로 쿼리 하는 방법:  
  
```csharp  
using Microsoft.VisualStudio.Shell;   
using Microsoft.VisualStudio.Shell.Interop;   
  
IAsyncServiceProvider asyncServiceProvider = Package.GetService(typeof(SAsyncServiceProvider)) as IAsyncServiceProvider;   
IMyTestService testService = await asyncServiceProvider.GetServiceAsync(typeof(SMyTestService)) as IMyTestService;  
```
  
