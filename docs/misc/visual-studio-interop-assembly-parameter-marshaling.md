---
title: "Visual Studio Interop 어셈블리 매개 변수 마샬링 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio SDK interop 어셈블리 문제 해결"
  - "interop 어셈블리, 매개 변수 마샬링"
  - "interop 어셈블리, 문제 해결"
ms.assetid: 89123eae-0fef-46d5-bd36-3d2a166b14e3
caps.latest.revision: 24
caps.handback.revision: 24
manager: "douge"
---
# Visual Studio Interop 어셈블리 매개 변수 마샬링
관리 되는 코드로 작성 된 Vspackages를 호출 하거나 비관리 COM 코드가 호출할 수 할 수 있습니다.  일반적으로 메서드 인수를 변환 또는 자동으로 interop 마샬러에서 마샬링할.  그러나 경우에 따라 인수를 간단 하 게 변환할 수 없습니다.  그런 경우에 interop 어셈블리 메서드 프로토타입 매개 변수가 COM 함수 매개 변수를 최대한 근접 하 게 일치 하는 데 사용 됩니다.  자세한 내용은 [Interop 마샬링](../Topic/Interop%20Marshaling.md)를 참조하십시오.  
  
## 일반 제안 사항  
  
##### 참조 설명서  
 상호 운용성 문제를 감지 하는 효과적인 방법은 각 메서드에 대 한 참조 설명서를 참조입니다.  
  
 각 메서드에 대 한 참조 설명서 관련 절을 세 개 포함 되어 있습니다.  
  
-   [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] COM 함수 프로토타입이 있습니다.  
  
-   Interop 어셈블리 메서드 프로토타입입니다.  
  
-   COM 매개 변수에 대 한 간단한 설명을 각 목록.  
  
##### 두 프로토타입 간의 차이 찾습니다  
 특정 형식의 COM 인터페이스에서 정의와 같은 종류의 정의 사이 불일치에서 파생 하는 대부분의 상호 운용성 문제는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리입니다.  예를 들어 차이 전달 하는 기능을 고려는 `null` \[out\] 매개 변수 값입니다.  두 프로토타입 사이의 차이 확인 하 고 전달 되는 데이터에 대 한 자신의 문제를 고려해 야 합니다.  
  
##### 매개 변수 정의 읽기  
 매개 변수 정의 참조 하십시오.  COM 데이터의 단일 매개 변수에 여러 형식이 혼합 사용 하는 방법에 대 한 해당 공용 언어 런타임 \(CLR\) 보다 낮은 수준의입니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] COM 인터페이스 적용이 유연 하이 게 활용 합니다.  전달 하거나 사용할 수 없는 값 또는 상수 값 포인터 매개 변수를 같은 데이터 형식이 필요로 하는 모든 매개 변수 같은 설명서에 설명 해야 합니다.  
  
### IUnknown 개체 형식을 void \*\*으로 전달  
 \[Out\] 형식으로 정의 된 매개 변수 확인에 대 한 `void **` COM에서 인터페이스, 하지만는 다음과 같이 정의 `[``iid_is``]` 에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] il 메서드 프로토타입.  
  
 경우에 따라 COM 인터페이스를 생성 하는 `IUnknown` 개체 및 COM 인터페이스 후 전달 하며 형식으로 `void **`.  이러한 인터페이스는 특히 중요 하기 때문에 변수 같이 정의 됩니다 \[out\] IDL에 다음의 `IUnknown` 개체는 참조 횟수가 계산에 `AddRef` 메서드.  개체가 제대로 처리 되지 않은 경우 메모리 누수가 발생 합니다.  
  
> [!NOTE]
>  `IUnknown` COM 인터페이스에서 생성 하는 \[out\] 변수를 반환 하는 개체 명시적으로 해제 하는 경우 메모리 누수가 발생 합니다.  
  
 해야 이러한 개체를 처리 하는 관리 되는 메서드를 처리 <xref:System.IntPtr> 에 대 한 포인터는 `IUnknown` 개체를 하 고는 <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> 메서드는 개체를 가져올 수 있습니다.  그런 다음 호출자에 게 반환 값에 적합 한 어떤 종류를 캐스팅 해야 합니다.  개체가 더 이상 필요 없는 경우에 호출 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 를 해제 합니다.  
  
 다음 호출의 예입니다의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A> 메서드 및 처리는 `IUnknown` 제대로 개체:  
  
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
>  다음 메서드를 전달 하 라고 `IUnknown` 개체 포인터 형식으로 <xref:System.IntPtr>.  이 섹션에 설명 된 것 처럼 처리 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsOwnedProjectFactory.InitializeForOwner%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetNestedHierarchy%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution.CreateProject%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.QueryViewInterface%2A>  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>  
  
### \[Out\] 매개 변수 \(옵션\)  
 \[Out\]으로 정의 된 매개 변수를 찾습니다 데이터 형식 \(`int`, `object`등\) COM에서 인터페이스, 하지만는 다음과 같이 정의에 같은 데이터 형식의 배열에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입.  
  
 같은 일부 COM 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgs%2A>, \[out\] 매개 변수를 선택적으로 처리 합니다.  이러한 COM 인터페이스 반환 개체가 필요 하지 않습니다 경우는 `null` \[out\] 개체를 만드는 대신 해당 매개 변수의 값으로 포인터.  이는 의도된 것입니다.  이러한 인터페이스에 대 한 `null` 포인터 있는 Vspackage의 정확한 동작의 일부로 간주 되 고 오류가 반환 됩니다.  
  
 CLR에 대 한 \[out\] 매개 변수 값을 허용 하지 않으므로 `null`, 디자인 된 동작을 이러한 인터페이스에 속하지 않은 관리 되는 코드에서 직접 사용할 수 있습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 영향을 받는 인터페이스에 대 한 interop 어셈블리 방법 CLR의 전달을 허용 하기 때문에 관련 된 매개 변수 배열로 정의 하 여이 문제를 해결 작업 `null` 배열.  
  
 이러한 메서드의 관리 되는 구현 해야 합니다 넣을 `null` 에 아무 것도 반환 될 때 매개 변수 배열입니다.  그렇지 않으면 올바른 형식의 요소가 하나인 배열을 만들고 반환 값을 배열에 배치 합니다.  
  
 선택적 \[out\] 인터페이스 로부터 정보를 수신 하는 메서드를 관리 되는 매개 변수를 매개 변수 배열로 받을.  바로 배열의 첫 번째 요소 값을 검사 합니다.  그렇지 않은 경우 `null`, 첫 번째 요소는 원래 매개 변수 처럼 취급 합니다.  
  
### 상수 포인터 매개 변수 전달  
 매개 변수가 \[in\] 포인터는 COM 인터페이스에 정의 되어 있지만로 정의 되어 있는지 확인 한 <xref:System.IntPtr> 입력은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입.  
  
 COM 인터페이스 0,\-1,\-2 개체 포인터 대신 같은 특수 한 값을 전달 하면 유사한 문제가 발생 합니다.  달리 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)], CLR 개체로 사용할 수 있는 상수를 허용 하지 않습니다.  대신에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리 매개 변수로 정의 <xref:System.IntPtr> 형식입니다.  
  
 이러한 메서드의 관리 되는 구현 해야 이용할 사실에는 <xref:System.IntPtr> 클래스에 모두 `int` 및 `void *` 를 만드는 생성자는 <xref:System.IntPtr> 개체 또는 정수인 상수에서 적절 한.  
  
 수신 하는 메서드를 관리 되는 <xref:System.IntPtr> 이 형식의 매개 변수를 사용 해야 하는 <xref:System.IntPtr> 결과 처리 하는 변환 연산자를 입력 합니다.  먼저 변환 하는 <xref:System.IntPtr> 에 `int` 와 관련 된 정수 상수에 대해 테스트 합니다.  값이 일치 하면 필요한 형식의 개체로 변환 하 고 계속 합니다.  
  
 이 예제를 보려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>.  
  
### OLE 반환 값은 전달로 \[out\] 매개 변수  
 메서드를 찾습니다는 `retval` COM 인터페이스를 있지만 있는에서 반환 값은 `int` 반환 값 및 \[out\] 배열 매개 변수에 추가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 프로토타입.  이러한 방법 때문에 특수 한 처리가 필요한 것이 확실 해야는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리의 메서드 프로토타입은 COM 인터페이스 방법 보다 더 많은 매개 변수가 하나 있습니다.  
  
 OLE 작업을 처리 하는 많은 COM 인터페이스 OLE 상태 정보 저장 호출 프로그램으로 보내기는 `retval` 인터페이스의 값을 반환 합니다.  해당 하는 반환 값을 사용 하는 대신 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] interop 어셈블리 메서드 저장 된 \[out\] 호출 프로그램에 정보를 보낼 매개 변수 배열입니다.  
  
 이러한 메서드의 관리 되는 구현 된 단일 요소 배열을 \[out\] 매개 변수와 같은 형식의 만들고 매개 변수에 해야 합니다.  적절 한 COM와 배열 요소의 값을 같아야 `retval`.  
  
 이러한 종류의 인터페이스를 호출 하는 관리 되는 메서드는 \[out\] 배열의 첫 번째 요소를 문서가 포함 되어야 합니다.  이 있는 것 처럼이 요소를 처리할 수 있습니다는 `retval` 반환 값을 해당 하는 COM 인터페이스입니다.  
  
## 참고 항목  
 [Interop Marshaling](http://msdn.microsoft.com/ko-kr/a95fdb76-7c0d-409e-a77e-0349b1ea1490)   
 [Interop 마샬링](../Topic/Interop%20Marshaling.md)   
 [Troubleshooting Interoperability](/dotnet/visual-basic/programming-guide/com-interop/troubleshooting-interoperability)   
 [관리되는 VSPackage](../misc/managed-vspackages.md)