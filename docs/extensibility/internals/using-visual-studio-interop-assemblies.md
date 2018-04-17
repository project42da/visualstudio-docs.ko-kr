---
title: Visual Studio Interop 어셈블리를 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, interop assemblies
- interop assemblies, Visual Studio
- managed VSPackages, interop assemblies
ms.assetid: 1043eb95-4f0d-4861-be21-2a25395b3b3c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ca0ff9a75d72bc723b767a43f12123094a520644
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="using-visual-studio-interop-assemblies"></a>Visual Studio Interop 어셈블리를 사용 하 여
Visual Studio interop 어셈블리는 Visual Studio 확장성을 제공 하는 COM 인터페이스를 액세스 하는 관리 되는 응용 프로그램을 허용 합니다. 직선 COM 인터페이스 및 해당 interop 버전 간의 차이가 있습니다. 예를 들어 Hresult int 값으로 표시 일반적으로 되 고 동일한 방식으로 예외를 처리 해야 및 (특히 out 매개 변수) 매개 변수는 다르게 처리 됩니다.  
  
## <a name="handling-hresults-returned-to-managed-code-from-com"></a>COM에서 관리 코드로 반환되는 HRESULT 처리  
 관리 코드에서 COM 인터페이스를 호출하는 경우 HRESULT 값을 검사하고 필요에 따라 예외를 발생시킵니다. <xref:Microsoft.VisualStudio.ErrorHandler> 클래스에 포함 되어는 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> HRESULT의 값에 따라 COM 예외를 throw 하는 메서드를 전달 합니다.  
  
 기본적으로 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 0 보다 작은 값을 가진 HRESULT가 전달 될 때마다 예외를 throw 합니다. 이러한 Hresult가 허용 되는 값이 없고 없는 예외를 throw 해야 경우에 추가 HRESULT 값에 전달 해야 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 후의 값이 테스트 됩니다. 테스트 중인 HRESULT에 명시적으로 전달 된 HRESULT 값과 일치 하는 경우 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>, 예외가 throw 되지 않습니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.VSConstants> 클래스 일반적인 HRESULT에 대 한 예를 들어 상수를 포함 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 및 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>, 및 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] HRESULT, 예를 들어 <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA> 및 <xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>합니다. <xref:Microsoft.VisualStudio.VSConstants> 또한 제공 된 <xref:Microsoft.VisualStudio.ErrorHandler.Succeeded%2A> 및 <xref:Microsoft.VisualStudio.ErrorHandler.Failed%2A> COM.의 SUCCEEDED 및 FAILED 매크로에 해당 하는 방법  
  
 예를 들어 다음 함수 호출은는 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> 은 허용 가능한 반환 값 이지만 다른 HRESULT는 오류를 나타내는 0 보다 작은 합니다.  
  
 [!code-vb[VSSDKHRESULTInformation#1](../../extensibility/internals/codesnippet/VisualBasic/using-visual-studio-interop-assemblies_1.vb)]
 [!code-csharp[VSSDKHRESULTInformation#1](../../extensibility/internals/codesnippet/CSharp/using-visual-studio-interop-assemblies_1.cs)]  
  
 가 있는 경우 여러 개 사용할 수 있는 반환 값 추가 HRESULT 값만 추가할 수 있는 목록에 대 한 호출에서 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>합니다.  
  
 [!code-vb[VSSDKHRESULTInformation#2](../../extensibility/internals/codesnippet/VisualBasic/using-visual-studio-interop-assemblies_2.vb)]
 [!code-csharp[VSSDKHRESULTInformation#2](../../extensibility/internals/codesnippet/CSharp/using-visual-studio-interop-assemblies_2.cs)]  
  
## <a name="returning-hresults-to-com-from-managed-code"></a>관리 코드에서 COM으로 HRESULT 반환  
 예외가 발생 하는 경우 관리 코드 반환 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 를 호출한 COM 함수에 있습니다. COM interop는 관리 코드에서 강력한 형식의 일반적인 예외를 지원합니다. 허용 되지 않는 수신 하는 메서드가 예를 들어 `null` 인수 throw는 <xref:System.ArgumentNullException>합니다.  
  
 에서는 COM에 반환 하려면 확실 하지 않은 예외를 발생 시켜야 하지만 HRESULT를 알고 있는 경우는 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 메서드 적절 한 예외를 throw 합니다. 예를 들어 비표준 오류 된 경우에 작동 <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>합니다. <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> HRESULT를 매핑하려고 하기에 강력한 형식의 예외를 전달 합니다. 매핑할 수 없는 경우 대신 일반 COM 예외를 발생시킵니다. 최종 결과를 전달 하는 HRESULT는 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 관리 코드에서 호출한 COM 함수에 반환 됩니다.  
  
> [!NOTE]
>  예외가 발생하면 성능이 저하되며 비정상적인 프로그램 상태를 나타냅니다. 자주 발생하는 상태는 예외를 발생시키는 대신 인라인으로 처리해야 합니다.  
  
## <a name="iunknown-parameters-passed-as-type-void"></a>형식이 void * * 변수로 IUnknown 매개 변수 전달  
 [Out] 형식으로 정의 하는 매개 변수를 찾아보십시오 `void **` 으로 있었으나 인터페이스를 COM에 정의 `[``iid_is``]` 에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입 합니다.  
  
 COM 인터페이스를 생성 하는 경우에 따라는 `IUnknown` 개체 및 COM 인터페이스 다음으로 전달 형식 `void **`합니다. 이러한 인터페이스는 특히 중요 하기 때문에 변수로 정의 된 경우 [out]는 IDL에는 다음 `IUnknown` 개체는 참조 횟수가 계산 된는 `AddRef` 메서드. 메모리 누수 개체가 제대로 처리 되지 않은 경우에 발생 합니다.  
  
> [!NOTE]
>  `IUnknown` 개체는 COM 인터페이스에서 생성 되 고 [out] 변수의 반환 명시적으로 해제 되지 않으면 메모리 누수 발생 합니다.  
  
 이러한 개체를 처리 하는 관리 되는 메서드를 처리 해야 <xref:System.IntPtr> 에 대 한 포인터로 `IUnknown` 개체를 호출 하 고 <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> 개체를 얻는 메서드를 합니다. 호출자에 게 반환 값을 형식에 관계 없이 적절 한 캐스팅 한 다음 해야 합니다. 개체가 더 이상 필요 하 고, 호출 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 분리 합니다.  
  
 다음은 호출의 예는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A> 메서드 및 처리는 `IUnknown` 올바르게 개체:  
  
```  
MyClass myclass;  
Object object;  
IntPtr pObj;  
Guid iid = Typeof(MyClass).Guid;  
int hr = windowFrame.QueryViewInterface(ref iid, out pObj);     
if (NativeMethods.Succeeded(hr))   
{  
    try   
    {  
        object = Marshal.GetObjectForIUnknown(pObj);  
        myclass = object;  
    }  
    finally   
    {  
        Marshal.Release(pObj);  
    }  
}  
else   
{  
    // error calling QueryViewInterface  
}  
```  
  
> [!NOTE]
>  다음 방법으로 전달 알려진 `IUnknown` 포인터 형식으로 개체 <xref:System.IntPtr>합니다. 이 섹션에 설명 된 대로 처리 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>  
  
## <a name="optional-out-parameters"></a>[Out] 매개 변수 (옵션)  
 [Out]로 정의 된 매개 변수를 찾고 데이터 형식 (`int`, `object`등)에서 동일한 데이터 형식의 배열로 있었으나 인터페이스를 COM에 정의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입 합니다.  
  
 와 같은 일부 COM 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A>, [out] 매개 변수가 선택적으로 처리 합니다. 이러한 COM 인터페이스를 반환 하는 경우 개체 필요 하지 않은 한 `null` [out] 개체를 만드는 대신 해당 매개 변수의 값으로 포인터입니다. 이것은 의도적인 것입니다. 이러한 인터페이스에 대 한 `null` 포인터는 VSPackage의 올바른 동작의 일부로 간주 되며 고 없음 오류가 반환 됩니다.  
  
 CLR에서 사용할 수 있는 [out] 매개 변수 값을 허용 하지 않으므로 `null`, 이러한 인터페이스의 디자인 된 동작의 일부는 관리 코드 내에서 직접 사용할 수 없습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 영향을 받는 인터페이스에 대 한 interop 어셈블리 메서드 CLR의 통과 허용 하기 때문에 배열로 관련 매개 변수를 정의 하 여 문제 해결 `null` 배열입니다.  
  
 이러한 메서드의 관리 되는 구현 넣어야는 `null` 반환할이 없을 경우 매개 변수 배열입니다. 올바른 형식의 요소가 하나인 배열 만들고 그렇지 않은 경우 반환 값 배열에 배치 합니다.  
  
 관리 되는 선택적 [out] 사용 하는 인터페이스에서 정보를 수신 하는 메서드 매개 변수를 배열로 매개 변수를 수신 합니다. 배열의 첫 번째 요소 값을 확인만 합니다. 없는 경우 `null`, 첫 번째 요소를 원래 매개 변수 있는 것 처럼 처리 합니다.  
  
## <a name="passing-constants-in-pointer-parameters"></a>포인터 매개 변수에서 전달 상수  
 [In] COM 인터페이스에 대 한 포인터 정의 되어 있지만로 정의 된 매개 변수에 대 한 조회는 <xref:System.IntPtr> 에 입력는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입 합니다.  
  
 도 유사한 문제가 발생 하는 COM 인터페이스 0,-1 또는-2는 개체 포인터 대신 같은 특수 한 값을 전달할 때 발생 합니다. 와 달리 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]를 CLR 개체로 캐스팅 하는 상수를 허용 하지 않습니다. 대신,는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 으로 매개 변수를 정의 하는 interop 어셈블리는 <xref:System.IntPtr> 유형입니다.  
  
 이러한 메서드의 관리 되는 구현 취해야 사실 활용 하는 <xref:System.IntPtr> 클래스 둘 다에 `int` 및 `void *` 를 만드는 생성자는 <xref:System.IntPtr> 개체 또는 정수 상수에서 적절 하 게 합니다.  
  
 관리 되는 수신 하는 메서드 <xref:System.IntPtr> 이 형식의 매개 변수를 사용할지는 <xref:System.IntPtr> 결과 처리 하는 변환 연산자를 입력 합니다. 먼저 변환는 <xref:System.IntPtr> 를 `int` 및 관련 정수 상수에 대해 테스트 합니다. 일치 하는 값이 없는 경우 필요한 형식의 개체로 변환할 하 고 계속 합니다.  
  
 이 예 참조 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>합니다.  
  
## <a name="ole-return-values-passed-as-out-parameters"></a>OLE 반환 값이 전달 [out] 매개 변수  
 이 있는 메서드는 `retval` 있었으나 COM 인터페이스의 반환 값이 될는 `int` 반환 값과 추가 [out] 배열 매개 변수에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입 합니다. 이러한 방법 때문에 특별 한 처리가 필요 하 고 명확 해야는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입 COM 인터페이스의 두 방법 보다 더 많은 매개 변수 하나를 사용할 합니다.  
  
 에 저장 하 고 호출 프로그램에 다시 OLE 상태에 대 한 정보를 송신 하는 OLE 활동을 처리 하는 많은 COM 인터페이스는 `retval` 인터페이스의 값을 반환 합니다. 해당 반환 값을 사용 하는 대신 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 [out]에 저장 하 고 호출 프로그램을 다시 보냅니다 배열 매개 변수입니다.  
  
 이러한 메서드의 관리 되는 구현 [out] 매개 변수와 동일한 형식의 단일 요소 배열을 만들고 매개 변수에서 저장 해야 합니다. 배열 요소의 값으로 적절 한 COM 동일 해야 `retval`합니다.  
  
 이 형식의 인터페이스를 호출 하는 관리 되는 메서드 [out] 배열에서 첫 번째 요소에 포함 되어야 합니다. 이 요소 처럼 처리할 수는 `retval` 해당 하는 COM 인터페이스에서 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비관리 코드와의 상호 운용](/dotnet/framework/interop/index)