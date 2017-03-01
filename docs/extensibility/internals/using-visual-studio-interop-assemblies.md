---
title: "Visual Studio Interop 어셈블리를 사용 하 여 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, interop assemblies
- interop assemblies, Visual Studio
- managed VSPackages, interop assemblies
ms.assetid: 1043eb95-4f0d-4861-be21-2a25395b3b3c
caps.latest.revision: 33
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 9762ba0404e739c167cadc3e9d3106c7f3ee14e8
ms.lasthandoff: 02/22/2017

---
# <a name="using-visual-studio-interop-assemblies"></a>Visual Studio Interop 어셈블리를 사용 하 여
Visual Studio interop 어셈블리는 Visual Studio 확장성을 제공 하는 COM 인터페이스에 액세스 하는 관리 되는 응용 프로그램을 허용 합니다. 직선 COM 인터페이스 및 해당 interop 버전 간의 차이가 있습니다. 예를 들어 Hresult int 값으로 표시 일반적으로 되 고 동일한 방식으로 예외를 처리 해야 하 고 (특히 out 매개 변수) 매개 변수는 다르게 처리 됩니다.  
  
## <a name="handling-hresults-returned-to-managed-code-from-com"></a>COM에서 관리 코드로 반환되는 HRESULT 처리  
 관리 코드에서 COM 인터페이스를 호출하는 경우 HRESULT 값을 검사하고 필요에 따라 예외를 발생시킵니다. <xref:Microsoft.VisualStudio.ErrorHandler>클래스에 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>전달 합니다. HRESULT의 값에 따라 COM 예외를 throw 하는 메서드를</xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 포함</xref:Microsoft.VisualStudio.ErrorHandler>  
  
 기본적으로 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>0 보다 작은 값이 있는 HRESULT를 전달 될 때마다 예외를 throw 합니다.</xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 여기에서 이러한 Hresult는 사용할 수 있는 값 하 고 예외가 throw 되지는 해야의 경우 추가 HRESULT의 값에 전달 해야 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>값은 테스트 후.</xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 테스트 되는 HRESULT에 명시적으로 전달 하는 HRESULT 값과 일치 하는 경우 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>, 예외가 throw 되지 않습니다.</xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.VSConstants>클래스 일반적인 HRESULT에 대 한 예를 들어 상수를 포함 <xref:Microsoft.VisualStudio.VSConstants.S_OK>및 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>, 및 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] HRESULT, 예를 들어 <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>및 <xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>.</xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT> </xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA> </xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL> </xref:Microsoft.VisualStudio.VSConstants.S_OK> </xref:Microsoft.VisualStudio.VSConstants> <xref:Microsoft.VisualStudio.VSConstants>또한 제공 <xref:Microsoft.VisualStudio.ErrorHandler.Succeeded%2A>및 <xref:Microsoft.VisualStudio.ErrorHandler.Failed%2A>COM.의 성공 및 실패를 매크로에 해당 하는 메서드</xref:Microsoft.VisualStudio.ErrorHandler.Failed%2A> </xref:Microsoft.VisualStudio.ErrorHandler.Succeeded%2A></xref:Microsoft.VisualStudio.VSConstants>  
  
 예를 들어 다음 함수 호출은는 <xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>는 적절 한 반환 값 이지만 다른 HRESULT&0; 보다 작은 오류를 나타냅니다.</xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>  
  
 [!code-vb[#1 VSSDKHRESULTInformation](../../extensibility/internals/codesnippet/VisualBasic/using-visual-studio-interop-assemblies_1.vb) ] 
 [!code-cs [VSSDKHRESULTInformation&#1;](../../extensibility/internals/codesnippet/CSharp/using-visual-studio-interop-assemblies_1.cs)]  
  
 HRESULT 값을 추가 <xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>.</xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A> 에 대 한 호출에 목록에 추가 수 있으면 여러 개 사용할 수 있는 반환 값  
  
 [!code-vb[#2 VSSDKHRESULTInformation](../../extensibility/internals/codesnippet/VisualBasic/using-visual-studio-interop-assemblies_2.vb) ] 
 [!code-cs [VSSDKHRESULTInformation&#2;](../../extensibility/internals/codesnippet/CSharp/using-visual-studio-interop-assemblies_2.cs)]  
  
## <a name="returning-hresults-to-com-from-managed-code"></a>관리 코드에서 COM으로 HRESULT 반환  
 관리 코드를 <xref:Microsoft.VisualStudio.VSConstants.S_OK>호출 합니다. COM 함수로</xref:Microsoft.VisualStudio.VSConstants.S_OK> 반환 예외가 발생 하는 경우 COM interop는 관리 코드에서 강력한 형식의 일반적인 예외를 지원합니다. 예를 들어 받는 메서드를 부적절 한 `null` 인수 <xref:System.ArgumentNullException>.</xref:System.ArgumentNullException> 를 throw 합니다.  
  
 에서는 COM에 반환 하려면 확실 하지 않은 예외를 throw 하 고, HRESULT를 알고 있는 경우는 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>메서드를 적절 한 예외를 throw 합니다.</xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 이 작동 하는 비표준 오류가 있어도 예를 들어 <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>.</xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA> <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>시도 된 HRESULT에 매핑할 것에 강력한 형식의 예외를 전달 합니다.</xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 매핑할 수 없는 경우 대신 일반 COM 예외를 발생시킵니다. 최종 결과 HRESULT에 전달 하는 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>관리 코드에서 돌아갑니다 COM 함수를 호출 합니다.</xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>  
  
> [!NOTE]
>  예외가 발생하면 성능이 저하되며 비정상적인 프로그램 상태를 나타냅니다. 자주 발생하는 상태는 예외를 발생시키는 대신 인라인으로 처리해야 합니다.  
  
## <a name="iunknown-parameters-passed-as-type-void"></a>형식 void * *으로 IUnknown 매개 변수 전달  
 [Out] 형식으로 정의 되는 매개 변수를 찾고 `void **` 으로 하지만 인터페이스를 COM에 정의 `[``iid_is``]` 에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입을 합니다.  
  
 COM 인터페이스를 생성 하는 경우에 따라는 `IUnknown` 개체 및 COM 인터페이스 다음 전달 형식으로 `void **`합니다. 이러한 인터페이스는 특히 중요 하기 때문에 변수로 정의 된 경우 [out]는 IDL에는 `IUnknown` 개체와 참조 횟수가 계산 되는 `AddRef` 메서드 합니다. 메모리 누수 개체가 올바르게 처리 되지 않은 경우에 발생 합니다.  
  
> [!NOTE]
>  `IUnknown` 개체는 COM 인터페이스에서 생성 및 [out] 변수에 반환 명시적으로 해제 되지 않으면 메모리 누수가 발생 합니다.  
  
 이러한 개체를 처리 하는 관리 되는 메서드를 처리 해야 <xref:System.IntPtr>에 대 한 포인터로 `IUnknown` 개체를 호출 하는 <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A>메서드 개체를 가져오려면.</xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> </xref:System.IntPtr> 호출자는 반환 값을 형식에 관계 없이 적절 한 캐스팅 다음 해야 합니다. 개체는 더 이상 필요 없는, 호출 <xref:System.Runtime.InteropServices.Marshal.Release%2A>를 해제 합니다.</xref:System.Runtime.InteropServices.Marshal.Release%2A>  
  
 다음은 호출의 예는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>메서드 및 처리는 `IUnknown` 올바르게 개체:</xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>  
  
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
>  다음 방법을 전달 것으로 알려진 `IUnknown` <xref:System.IntPtr>.</xref:System.IntPtr> 형식으로 포인터를 개체 이 섹션에 설명 된 대로 처리 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.CreateProject%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A></xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>  
  
## <a name="optional-out-parameters"></a>[Out] 매개 변수는 선택 사항  
 [Out]로 정의 된 매개 변수를 찾고 데이터 형식 (`int`, `object`등)에서 동일한 데이터 형식의 배열로 하지만 인터페이스를 COM에 정의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 메서드 프로토타입을 interop 어셈블리입니다.  
  
 와 같은 일부 COM 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A>, [out] 매개 변수 선택 항목으로 처리 합니다.</xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A> 이러한 COM 인터페이스를 반환 하는 경우 개체 필요 하지 않은 한 `null` [out] 개체를 만드는 대신 해당 매개 변수의 값으로 포인터입니다. 이것은 의도적인 것입니다. 이러한 인터페이스에 대 한 `null` 포인터는는 VSPackage의 올바른 동작의 일부로 간주 되며 오류가 반환 되지 않습니다.  
  
 CLR에서 되도록 [out] 매개 변수 값을 허용 하지 않으므로 `null`, 이러한 인터페이스의 디자인 된 동작의 일부는 관리 코드 내에서 직접 사용할 수 없습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 영향을 받는 인터페이스에 대 한 interop 어셈블리 메서드는 CLR에 전달 하는 허용 하기 때문에 배열로 관련 매개 변수를 정의 하 여 문제 해결 `null` 배열입니다.  
  
 이러한 메서드의 관리 되는 구현 넣어야는 `null` 반환할이 없을 경우 매개 변수 배열입니다. 그렇지 않은 경우 올바른 형식의 요소가 하나인 배열을 만들고 반환 값은 배열에 배치 합니다.  
  
 관리 되는 선택적 [out] 인터페이스에서 정보를 수신 하는 메서드 매개 변수는 배열 매개 변수를 수신 합니다. 방금 배열의 첫 번째 요소 값을 검사 합니다. 없는 경우 `null`, 원래 매개 변수가 마치 첫 번째 요소를 처리 합니다.  
  
## <a name="passing-constants-in-pointer-parameters"></a>포인터 매개 변수에서 전달 상수  
 으로 [in] COM 인터페이스에 대 한 포인터 정의 되어 있지만로 정의 된 매개 변수에 대 한 조회는 <xref:System.IntPtr>입력는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입을.</xref:System.IntPtr>  
  
 다른 사람도 비슷한 문제는 COM 인터페이스에는 0,-1 또는-2는 개체 포인터 대신 같은 특수 한 값을 전달 될 때 발생 합니다. 와 달리 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]를 CLR 개체로 캐스팅 되어야 하는 상수를 허용 하지 않습니다. 대신,는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 으로 매개 변수를 정의 하는 interop 어셈블리는 <xref:System.IntPtr>유형.</xref:System.IntPtr>  
  
 이러한 메서드의 관리 되는 구현 취해야 사실 활용 하는 <xref:System.IntPtr>클래스에는 둘 다 `int` 및 `void *` 를 만들려면 생성자는 <xref:System.IntPtr>개체 또는 정수 상수를 적절 하 게.</xref:System.IntPtr> </xref:System.IntPtr>  
  
 관리 되는 수신 하는 메서드 <xref:System.IntPtr>이러한 종류의 매개 변수를 사용 해야는 <xref:System.IntPtr>결과 처리 하는 변환 연산자를 입력 합니다.</xref:System.IntPtr> </xref:System.IntPtr> 먼저 변환 하는 <xref:System.IntPtr>를 `int` 및 관련 된 정수 상수에 대해 테스트 합니다.</xref:System.IntPtr> 값이 없는 일치 하는 필요한 형식의 개체로 변환 하 고 계속 합니다.  
  
 이 예제를 보려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>.</xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A> </xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 를 참조 하십시오.  
  
## <a name="ole-return-values-passed-as-out-parameters"></a>OLE 반환 값이 전달 [out] 매개 변수  
 있는 메서드에 대 한 조회는 `retval` 있지만 COM 인터페이스의 반환 값을 가질는 `int` 반환 값과 추가 [out] 배열 매개 변수에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 메서드 프로토타입을 interop 어셈블리입니다. 이러한 방법 때문에 특별 한 처리가 필요 하 고 명확 해야는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 메서드 프로토타입을 interop 어셈블리에는 COM 인터페이스 메서드를 사용 하는 보다 더 많은 매개 변수가 하나 있습니다.  
  
 에 저장 된 호출 프로그램에 다시 OLE 상태에 대 한 정보를 송신 하는 OLE 활동을 처리 하는 대부분 COM 인터페이스는 `retval` 인터페이스의 값을 반환 합니다. 해당 반환 값을 사용 하는 대신 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 호출 [out]에 저장 된 프로그램을 다시 보냅니다 배열 매개 변수입니다.  
  
 이러한 메서드의 관리 되는 구현 [out] 매개 변수와 같은 형식의 단일 요소 배열이 만들고 매개 변수에서 저장 해야 합니다. 배열 요소의 값으로 적절 한 COM 동일 해야 `retval`합니다.  
  
 이 형식의 인터페이스를 호출 하는 관리 되는 메서드 [out] 배열에서 첫 번째 요소에 포함 되어야 합니다. 이 요소는 마치 처리 될 수는 `retval` 해당 하는 COM 인터페이스에서 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비관리 코드와의 상호 운용](http://msdn.microsoft.com/Library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)
