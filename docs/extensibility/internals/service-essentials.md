---
title: "서비스 Essentials | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서비스, essentials"
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# 서비스 Essentials
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

서비스는 두 개의 Vspackage 간의 계약입니다. 하나의 VSPackage를 사용 하는 다른 VSPackage에 대 한 인터페이스의 특정 집합을 제공 합니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다른 Vspackage에 서비스를 제공 하는 Vspackage의 컬렉션 됩니다.  
  
 예를 들어 작업 로그에 쓰는 데 사용할 수 있는 IVsActivityLog 인터페이스를 가져오지 SVsActivityLog 서비스를 사용할 수 있습니다. 자세한 내용은 [방법: 작업 로그를 사용 하 여](../../extensibility/how-to-use-the-activity-log.md)을 참조하십시오.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 또한 등록 되지 않은 몇 가지 기본 제공 서비스를 제공 합니다. Vspackage는 서비스 재정의 제공 하 여 기본 제공 또는 다른 서비스를 대체할 수 있습니다. 모든 서비스에 대 한 재정의 서비스 하나만 허용 됩니다.  
  
 이러한 서비스에는 없는 검색 기능이 있습니다. 따라서, 사용 하려는 서비스의 서비스 id \(SID\)를 알고 있어야 하 고 제공 하는 인터페이스를 알아야 합니다. 서비스에 대 한 참조 설명서는이 정보를 제공합니다.  
  
-   Vspackage 서비스를 제공 하는 서비스 공급자 라고 합니다.  
  
-   다른 Vspackage에 제공 되는 서비스에는 글로벌 서비스 라고 합니다.  
  
-   구현 하는 VSPackage 또는 만들 모든 개체에만 사용할 수 있는 서비스는 로컬 서비스 라고 합니다.  
  
-   기본 제공 서비스 또는 다른 패키지에서 제공 하는 서비스를 대체 하는 서비스는 서비스 재정의 라고 합니다.  
  
-   다른 VSPackage에서 제공 하는 서비스를 요청할 때는 서비스 공급자가 로드 즉,에 서비스 또는 서비스 재정의 주문형 로드 됩니다.  
  
-   요청 시 로드를 지원 하려면 서비스 공급자는 글로벌 서비스를 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 [서비스 등록](../../misc/registering-services.md)을 참조하세요.  
  
-   사용 하 여 서비스를 가져온 후 [QueryInterface](/visual-cpp/atl/queryinterface) \(비관리 코드\) 또는 예를 들어 원하는 인터페이스를 가져올 캐스팅 \(관리 코드\):  
  
    ```vb#  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```c#  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
  
    ```  
  
-   관리 코드는 비관리 코드 해당 GUID로 서비스를 가리키는 반면 해당 형식 사용 하 여 서비스를 가리킵니다.  
  
-   때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 글로벌 서비스에 VSPackage 액세스할 수 있도록 VSPackage를 서비스 공급자에 전달 VSPackage 로드 합니다. VSPackage "사이 팅" 라고 합니다.  
  
-   Vspackage 만든 개체에 대 한 서비스 공급자 수 있습니다. 예를 들어 폼 컬러 서비스에 대 한 요청 요청을 전달할 수 있는 해당 프레임에 보낼 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   여러 층으로 중첩 된 추가 되거나 전혀 없거나 관리 되는 개체를 호출할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 글로벌 서비스에 대 한 직접 액세스 합니다. 자세한 내용은 [방법: GetGlobalService 사용](../../misc/how-to-use-getglobalservice.md)을 참조하세요.  
  
## 참고 항목  
 [사용 가능한 서비스 목록](../../extensibility/internals/list-of-available-services.md)   
 [사용 하 고 서비스를 제공 합니다.](../../extensibility/using-and-providing-services.md)   
 [캐스팅 및 형식 변환\(C\#\)](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)   
 [캐스팅](/visual-cpp/cpp/casting)