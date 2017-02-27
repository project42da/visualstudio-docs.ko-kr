---
title: "방법: 작업 로그를 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage, 디버깅"
  - "Vspackage, 문제 해결"
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: 29
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: 작업 로그를 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Vspackage 메시지 활동 로그에 쓸 수 있습니다. 이 기능은 Vspackage 소매 환경에서 디버깅 하는 데 특히 유용 합니다.  
  
> [!TIP]
>  작업 로그는 항상 켜져 있습니다. Visual Studio는 롤링 버퍼의 마지막 100 개의 항목 뿐 아니라 일반 구성 정보가 있는 처음 10 개의 항목을 유지 합니다.  
  
### 작업 로그에 항목을 기록 하려면  
  
1.  이 코드에 삽입 하는 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드 또는 VSPackage 생성자를 제외 하 고 다른 메서드에서:  
  
    ```c#  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     이 코드를 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> 서비스와 캐스팅는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> 인터페이스입니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> 현재 문화적 컨텍스트를 사용 하 여 작업 로그에 정보 항목을 씁니다.  
  
2.  VSPackage \(일반적으로 때나 명령을 호출 하는 창이 열릴\) 로드 되 면 텍스트 작업 로그에 쓰여집니다.  
  
### 작업 로그를 검사 하려면  
  
1.  Visual Studio 데이터에 대 한 작업 로그 하위 폴더에서 찾을: *% AppData %*\\Microsoft\\VisualStudio\\14.0\\ActivityLog.XML...  
  
2.  작업 로그에서 원하는 텍스트 편집기로 엽니다. 다음은 일반적인 항목이입니다.  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## 강력한 프로그래밍  
 작업 로그 서비스 이기 때문에 작업 로그를 VSPackage 생성자에서 사용할 수 없는 경우  
  
 작업 로그에 쓰기 전에 방금 가져와야 합니다. 캐시 하거나 나중에 사용에 대 한 작업 로그를 저장 하지 마십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Vspackage 문제 해결](../extensibility/troubleshooting-vspackages.md)   
 [Vspackage](../extensibility/internals/vspackages.md)