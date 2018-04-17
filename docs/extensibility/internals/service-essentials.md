---
title: Essentials 서비스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- services, essentials
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c5a9858109c9fe0d8af0d00621b717417a0c0e53
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="service-essentials"></a>서비스 Essentials
서비스는 두 개의 Vspackage 사이의 계약입니다. 하나의 VSPackage를 사용할 다른 VSPackage에 대 한 인터페이스의 특정 집합을 제공 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다른 Vspackage에 서비스를 제공 하는 Vspackage의 수집 됩니다.  
  
 예를 들어 활동 로그에 쓰는 데 사용할 수 있는 IVsActivityLog 인터페이스를 가져오지 SVsActivityLog 서비스를 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: 작업 로그를 사용 하 여](../../extensibility/how-to-use-the-activity-log.md)합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 또한 등록 된 일부 기본 제공 서비스를 제공 합니다. Vspackage는 서비스 재정의 제공 하 여 기본 제공 또는 다른 서비스를 바꿀 수 있습니다. 단 하나의 서비스 재정의 모든 서비스에 대 한 허용 됩니다.  
  
 서비스에는 없는 검색 기능을 해야합니다. 따라서에 라이브러리에 사용 하려는 서비스의 서비스 id (SID)를 알고 있어야 하 고 제공 하는 인터페이스를 알아야 합니다. 서비스에 대 한 참조 설명서는이 정보를 제공합니다.  
  
-   서비스를 제공 하는 Vspackage는 서비스 공급자 라고 합니다.  
  
-   다른 Vspackage에 제공 되는 서비스는 글로벌 서비스 라고 합니다.  
  
-   구현 하는 VSPackage 또는, 개체에만 사용할 수 있는 서비스는 로컬 서비스 라고 합니다.  
  
-   기본 제공 서비스 또는 다른 패키지에서 제공 하는 서비스를 대체 하는 서비스는 서비스 재정의 라고 합니다.  
  
-   서비스 또는 서비스 재정의 필요할 때 로드, 다른 VSPackage에서 요청 하는 서비스를 제공 하는 경우 서비스 공급자가 로드 즉, 합니다.  
  
-   요청 시 로드를 지원 하려면 서비스 공급자는 글로벌 서비스를 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [하는 방법: 서비스 제공](../../extensibility/how-to-provide-a-service.md)합니다.  
  
-   사용 하 여 서비스를 가져온 후 [QueryInterface](/cpp/atl/queryinterface) (비관리 코드) 또는 인터페이스를 가져오려면 원하는, 예를 들어 캐스팅 (관리 코드):  
  
    ```vb  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```csharp  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    ```  
  
-   관리 코드는 비관리 코드는 서비스 GUID에 의해 참조 되지만 해당 형식 사용 하 여 서비스를 가리킵니다.  
  
-   때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 글로벌 서비스에 VSPackage 액세스할 수 있도록 하기 위해 VSPackage를 서비스 공급자에 전달 VSPackage 로드 합니다. VSPackage "사이 팅" 라고 합니다.  
  
-   Vspackage를 만들 개체에 대 한 서비스 공급자 수 있습니다. 예를 들어 폼 색 서비스에 대 한 요청 요청을 전달할 수 있는 해당 프레임에 보낼 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   여러 층으로 중첩 추가 되거나 전혀 없거나 관리 되는 개체를 호출할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 글로벌 서비스에 대 한 직접 액세스 합니다.   
  
<a name="how-to-use-getglobalservice"></a>  
  
## <a name="use-getglobalservice"></a>GetGlobalService 사용  
  
경우에 따라 도구 창에서 서비스 가져오기 또는 컨테이너를 배치 하지 않습니다. 그렇지 않으면 원하는 서비스에 대해 알지 못하는 서비스 공급자에 배치 된 제어를 할 수 있습니다. 예를 들어 다음 컨트롤 내에서 작업 로그에 작성 하는 것이 좋습니다. 이러한 오류 코드 및 다른 시나리오에 대 한 자세한 내용은 참조 [하는 방법: 서비스 문제 해결](../../extensibility/how-to-troubleshoot-services.md)합니다.  
  
정적을 호출 하 여 대부분 Visual Studio 서비스를 가져올 수 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 메서드.  
  
<xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 캐시 된 서비스 패키지에서 파생 된 모든 VSPackage 처음으로 초기화 된 공급자가 배치 되어 있습니다. 이 조건을 충족 됩니다. 그렇지 않으면 null 서비스에 대 한 준비를 보장 해야 합니다.  
  
다행히 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 대부분의 경우 올바르게 작동 합니다.  
  
-   다른 VSPackage 에게만 알려지므로 호출자는 서비스를 제공 하는 VSPackage를 하는 경우 해당 서비스를 요청 하는 VSPackage는 서비스가 로드를 제공 하는 VSPackage 하기 전에 배치 됩니다.  
  
-   VSPackage에서 도구 창을 만들 도구 창이 생성 되기 전에 VSPackage 배치 됩니다.  
  
-   컨트롤 컨테이너에는 VSPackage에서 만든 도구 창에서 호스트 될 경우 컨트롤 컨테이너를 만들기 전에 VSPackage 배치 됩니다.  
  
### <a name="to-get-a-service-from-within-a-tool-window-or-control-container"></a>도구 창 또는 컨트롤 컨테이너 내에서 서비스를 가져오는  
  
-   생성자, 도구 창 또는 컨트롤 컨테이너에이 코드를 삽입 합니다.  
  
    ```csharp  
    IVsActivityLog log = Package.GetGlobalService(typeof(SVsActivityLog)) as IVsActivityLog;
        if (log == null) return;
    ```  
    ```vb  
    Dim log As IVsActivityLog = TryCast(Package.GetGlobalService(GetType(SVsActivityLog)), IVsActivityLog)
    If log Is Nothing Then
        Return
    End If
    ```  
    
    이 코드는 SVsActivityLog 서비스 가져오고 활동 로그에 쓰는 데 사용할 수 있는 IVsActivityLog 인터페이스로 캐스팅 합니다. 예를 들어 참조 [하는 방법: 작업 로그를 사용 하 여](../../extensibility/how-to-use-the-activity-log.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용 가능한 서비스 목록](../../extensibility/internals/list-of-available-services.md)   
 [사용 하 고 서비스를 제공 합니다.](../../extensibility/using-and-providing-services.md)   
 [캐스팅 및 형식 변환](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)   
 [캐스팅](/cpp/cpp/casting)