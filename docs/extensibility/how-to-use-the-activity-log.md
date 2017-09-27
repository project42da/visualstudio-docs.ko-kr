---
title: "방법: 작업 로그를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: 29
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: a1ddf51d02d9e20f6806f8bc202f8a08166876d6
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="how-to-use-the-activity-log"></a>방법: 작업 로그를 사용 하 여
Vspackage 활동 로그에 메시지를 쓸 수 있습니다. 이 기능은 특히 소매 환경에서 Vspackage를 디버깅 하는 데 유용 합니다.  
  
> [!TIP]
>  항상 작업 로그 켜져 있습니다. Visual Studio는 1 백 마지막 항목 뿐만 아니라 일반 구성 정보를 포함 하는 처음 10 개 항목의 롤링 버퍼를 유지 합니다.  
  
### <a name="to-write-an-entry-to-the-activity-log"></a>작업 로그에 항목을 기록 하려면  
  
1.  이 코드를 삽입 하는 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드 또는 VSPackage 생성자를 제외한 다른 방법:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     이 코드는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> 으로 캐스팅 하 고 서비스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> 인터페이스입니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A>현재 문화권 컨텍스트를 사용 하 여 활동 로그에 정보 항목을 씁니다.  
  
2.  (일반적으로 하는 경우 명령을 호출 하는 창이 열릴 또는) VSPackage 로드 되 면 텍스트 작업 로그에 기록 됩니다.  
  
### <a name="to-examine-the-activity-log"></a>작업 로그를 검사 하려면  
  
1.  Visual Studio 데이터에 대 한 활동 로그 하위 폴더에서 찾을: *% AppData %*\Microsoft\VisualStudio\15.0\ActivityLog.XML...  
  
2.  텍스트 편집기로 활동 로그를 엽니다. 다음은 일반적인 항목이입니다.  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 작업 로그 서비스 때문에 작업 로그 VSPackage 생성자에서 사용할 수 없는 경우  
  
 에 쓰기 전에 방금 활동 로그를 가져와야 합니다. 캐시 하거나 나중에 사용에 대 한 활동 로그를 저장 하지 마십시오.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Vspackage를 문제 해결](../extensibility/troubleshooting-vspackages.md)   
 [VSPackage](../extensibility/internals/vspackages.md)

