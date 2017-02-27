---
title: "PROFILE_CURRENTID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PROFILE_CURRENTID"
ms.assetid: 55ccf665-a05e-48c3-adf7-7714c0a9aaef
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# PROFILE_CURRENTID
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

PROFILE\_CURRENTID는 NameProfile, StartProfile, StopProfile, SuspendProfile 및 ResumeProfile에 대한 호출에서 스레드 ID 또는 프로세스 ID에 대해 의사\(pseudo\) 토큰을 반환합니다.  이를 사용하면 구체적으로 지정된 스레드나 프로세스 대신 현재 스레드나 프로세스에 대해 함수가 실행됩니다.  
  
## 예제  
 PROFILE\_CURRENTID는 VSPerf.h에 다음과 같이 정의됩니다.  
  
```  
static const unsigned int PROFILE_CURRENTID = (unsigned int)-1;  
```  
  
## 예제  
 다음 예제에서는 PROFILE\_CURRENTID를 보여 줍니다.  이 예제에서는 [StartProfile](../profiling/startprofile.md) 함수에 대한 호출의 현재 스레드를 식별하는 매개 변수로 PROFILE\_CURRENTID를 사용합니다.  
  
```  
void ExerciseProfileCurrentID()  
{  
    // Declare ProfileOperationResult enumeration   
    // to hold return value of a call to StartProfile.  
    PROFILE_COMMAND_STATUS profileResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    profileResult = StartProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("StartProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## 참고 항목  
 [Visual Studio 프로파일러 API 참조\(네이티브\)](../profiling/visual-studio-profiler-api-reference-native.md)   
 [NameProfile](../profiling/nameprofile.md)   
 [ResumeProfile](../profiling/resumeprofile.md)   
 [StartProfile](../profiling/startprofile.md)   
 [StopProfile](../profiling/stopprofile.md)   
 [SuspendProfile](../profiling/suspendprofile.md)