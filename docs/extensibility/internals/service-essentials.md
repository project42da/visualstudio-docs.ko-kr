---
title: "Essentials 서비스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, essentials
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
caps.latest.revision: 13
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
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 8ff357d7ed3542a01cf8d98e36b9d0e99a122864
ms.lasthandoff: 04/05/2017

---
# <a name="service-essentials"></a>서비스 Essentials
서비스는 두 개의 Vspackage 사이의 계약입니다. 하나의 VSPackage를 사용할 다른 VSPackage에 대 한 인터페이스의 특정 집합을 제공 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]다른 Vspackage에 서비스를 제공 하는 Vspackage의 수집 됩니다.  
  
 예를 들어 활동 로그에 쓰는 데 사용할 수 있는 IVsActivityLog 인터페이스를 가져오지 SVsActivityLog 서비스를 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: 작업 로그를 사용 하 여](../../extensibility/how-to-use-the-activity-log.md)합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]또한 등록 된 일부 기본 제공 서비스를 제공 합니다. Vspackage는 서비스 재정의 제공 하 여 기본 제공 또는 다른 서비스를 바꿀 수 있습니다. 단 하나의 서비스 재정의 모든 서비스에 대 한 허용 됩니다.  
  
 서비스에는 없는 검색 기능을 해야합니다. 따라서에 라이브러리에 사용 하려는 서비스의 서비스 id (SID)를 알고 있어야 하 고 제공 하는 인터페이스를 알아야 합니다. 서비스에 대 한 참조 설명서는이 정보를 제공합니다.  
  
-   서비스를 제공 하는 Vspackage는 서비스 공급자 라고 합니다.  
  
-   다른 Vspackage에 제공 되는 서비스는 글로벌 서비스 라고 합니다.  
  
-   구현 하는 VSPackage 또는, 개체에만 사용할 수 있는 서비스는 로컬 서비스 라고 합니다.  
  
-   기본 제공 서비스 또는 다른 패키지에서 제공 하는 서비스를 대체 하는 서비스는 서비스 재정의 라고 합니다.  
  
-   서비스 또는 서비스 재정의 필요할 때 로드, 다른 VSPackage에서 요청 하는 서비스를 제공 하는 경우 서비스 공급자가 로드 즉, 합니다.  
  
-   요청 시 로드를 지원 하려면 서비스 공급자는 글로벌 서비스를 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [서비스 등록](../../misc/registering-services.md)합니다.  
  
-   사용 하 여 서비스를 가져온 후 [QueryInterface](/cpp/atl/queryinterface) (비관리 코드) 또는 인터페이스를 가져오려면 원하는, 예를 들어 캐스팅 (관리 코드):  
  
    ```vb#  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```c#  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
  
    ```  
  
-   관리 코드는 비관리 코드는 서비스 GUID에 의해 참조 되지만 해당 형식 사용 하 여 서비스를 가리킵니다.  
  
-   때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 글로벌 서비스에 VSPackage 액세스할 수 있도록 하기 위해 VSPackage를 서비스 공급자에 전달 VSPackage 로드 합니다. VSPackage "사이 팅" 라고 합니다.  
  
-   Vspackage를 만들 개체에 대 한 서비스 공급자 수 있습니다. 예를 들어 폼 색 서비스에 대 한 요청 요청을 전달할 수 있는 해당 프레임에 보낼 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   여러 층으로 중첩 추가 되거나 전혀 없거나 관리 되는 개체를 호출할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A>글로벌 서비스에 대 한 직접 액세스 합니다.</xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 자세한 내용은 참조 [하는 방법: GetGlobalService 사용](../../misc/how-to-use-getglobalservice.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용 가능한 서비스 목록](../../extensibility/internals/list-of-available-services.md)   
 [사용 하 고 서비스를 제공 합니다.](../../extensibility/using-and-providing-services.md)   
 [캐스팅 및 형식 변환](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)   
 [캐스팅](/cpp/cpp/casting)
