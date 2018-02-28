---
title: "방법: 서비스 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, troubleshooting
ms.assetid: 001551da-4847-4f59-a0b2-fcd327d7f5ca
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 71ac3cda8e3df935ab743fed7aa94a5152c152a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-troubleshoot-services"></a>방법: 서비스 문제 해결
서비스 가져오기 하려고 할 때 발생할 수 있는 몇 가지 일반적인 문제가 있습니다.  
  
-   서비스에 등록 되어 있지는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   인터페이스 유형 및로 서비스 유형별이 아닌 서비스 요청 됩니다.  
  
-   해당 서비스를 요청 하는 VSPackage 요소가 배치 된 되지 않습니다.  
  
-   잘못 된 서비스 공급자가 사용 됩니다.  
  
 경우 요청된 된 서비스를 가져올 수 없으며에 대 한 호출 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> null을 반환 합니다. 서비스를 요청 후 항상 null에 대 한 테스트 해야:  
  
```csharp  
IVsActivityLog log =   
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
if (log == null) return;  
```  
  
### <a name="to-troubleshoot-a-service"></a>서비스 문제를 해결 하려면  
  
1.  서비스가 올바르게 등록 되었는지 여부를 확인 하려면 시스템 레지스트리를 검사 합니다. 자세한 내용은 참조 [하는 방법: 서비스 제공](../extensibility/how-to-provide-a-service.md)합니다.  
  
     다음.reg 파일 조각은 고 서비스 수 등록 하는 방법을 보여 줍니다.  
  
    ```  
    [HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}]  
    @="{F5E7E720-1401-11d1-883B-0000F87579D2}"  
    "Name"="SVsTextManager"  
    ```  
  
     위의 예에서 버전 번호는 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]12.0 또는 14.0, {F5E7E71D-1401-11d1-883B-0000F87579D2} 키가 기본 값 {, SVsTextManager 서비스의 서비스 id (SID) 등 F5E7E720-1401-11d1-883B-0000F87579D2}는 텍스트 관리자는 서비스를 제공 하는 VSPackage의 패키지 GUID입니다.  
  
2.  GetService를 호출 하는 경우에 서비스 형식과 인터페이스 형식이 아닌을 사용 합니다. 서비스를 요청할 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], <xref:Microsoft.VisualStudio.Shell.Package> 형식에서 GUID를 추출 합니다. 다음 조건에 해당 하는 경우 서비스를 찾을 수 없습니다.  
  
    1.  인터페이스 형식 대신 서비스 유형을 GetService에 전달 됩니다.  
  
    2.  GUID가 인터페이스를 명시적으로 할당 됩니다. 따라서 시스템 필요에 따라 개체에 대 한 기본 GUID를 생성 합니다.  
  
3.  해당 서비스를 요청 하는 VSPackage 요소가 배치 된 확인 해야 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]VSPackage를 호출 하기 전에 및 것을 생성 한 후 사이트 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>합니다.  
  
     서비스를 필요로 하는 VSPackage 생성자에서 코드를 있는 경우 Initialize 메서드를 이동 합니다.  
  
4.  올바른 서비스 공급자를 사용 하 고 있는지 확인 해야 합니다.  
  
     모든 서비스 공급자는 유사 합니다. 서비스 공급자는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도구 창으로 전달 VSPackage에 전달 하는 것과에서 다릅니다. 도구 창 서비스 공급자에 대해 알고 <xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>을 알지 못하는 하지만 <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>합니다. 호출할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 도구 창 내에서 VSPackage 서비스 공급자를 얻으려고 합니다.  
  
     도구 창에서 사용자 정의 컨트롤 또는 다른 컨테이너 컨트롤을 호스트 하는 경우 컨테이너 Windows 구성 요소 모델에 의해 위치할 수 없으며,는에 대 한 액세스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 서비스입니다. 호출할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 컨트롤 컨테이너에서 VSPackage 서비스 공급자를 얻으려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용 가능한 서비스 목록](../extensibility/internals/list-of-available-services.md)   
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [서비스 필수 항목](../extensibility/internals/service-essentials.md)