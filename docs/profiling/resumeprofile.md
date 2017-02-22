---
title: "ResumeProfile | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ResumeProfile"
ms.assetid: 876f145b-ec07-4240-ade6-4f6e44baadce
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# ResumeProfile
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`ResumeProfile` 메서드는 지정된 프로파일링 수준에 대해 Suspend\/Resume 카운터를 감소시킵니다.  
  
## 구문  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI ResumeProfile(  
                       PROFILE_CONTROL_LEVEL Level,   
                       unsigned int dwId);  
```  
  
#### 매개 변수  
 `Level`  
  
 성능 데이터 수집이 적용될 수 있는 프로필 수준을 나타냅니다.  다음 **PROFILE\_CONTROL\_LEVEL** 열거자를 사용하여 성능 데이터 수집이 적용될 수 있는 세 가지 수준 중 하나를 나타낼 수 있습니다.  
  
|열거자|설명|  
|---------|--------|  
|PROFILE\_GLOBALLEVEL|전역 수준 설정은 프로파일링 실행의 모든 프로세스와 스레드에 적용됩니다.|  
|PROFILE\_PROCESSLEVEL|프로세스 수준 설정은 지정된 프로세스의 일부인 모든 스레드에 적용됩니다.|  
|PROFILE\_THREADLEVEL|스레드 프로파일링 수준 설정은 지정된 스레드에 적용됩니다.|  
  
 `dwId`  
  
 시스템에 의해 생성된 프로세스 또는 스레드 식별자입니다.  
  
## 속성 값\/반환 값  
 이 함수는 **PROFILE\_COMMAND\_STATUS** 열거형을 사용하여 성공 또는 실패를 나타냅니다.  반환 값은 다음 중 하나일 수 있습니다.  
  
|열거자|설명|  
|---------|--------|  
|PROFILE\_ERROR\_ID\_NOEXIST|프로파일링 요소 ID가 없습니다.|  
|PROFILE\_ERROR\_LEVEL\_NOEXIST|지정한 프로파일링 수준이 없습니다.|  
|PROFILE\_ERROR\_MODE\_NEVER|함수가 호출될 때 프로파일링 모드가 NEVER로 설정되어 있었습니다.|  
|PROFILE\_ERROR\_NOT\_YET\_IMPLEMENTED|프로파일링 함수 호출, 프로파일링 수준 또는 호출과 수준의 조합이 아직 구현되지 않았습니다.|  
|PROFILE\_OK|호출을 완료했습니다.|  
  
## 설명  
 Suspend\/Resume 카운터의 초기 값은 0입니다.  SuspendProfile을 호출할 때마다 Suspend\/Resume 카운트가 1씩 증가하고 ResumeProfile을 호출할 때마다 1씩 감소합니다.  
  
 Suspend\/Resume 카운터가 0보다 큰 경우, 해당 수준의 Suspend\/Resume 상태는 OFF입니다.  카운트가 0보다 작거나 같은 경우, Suspend\/Resume 상태는 ON입니다.  
  
 Start\/Stop 상태와 Suspend\/Resume 상태가 모두 ON인 경우, 해당 수준의 프로파일링 상태는 ON입니다.  프로파일링될 스레드의 경우, 해당 스레드에 대한 전역, 프로세스, 스레드 수준 상태는 모두 ON이어야 합니다.  
  
## 해당 .NET Framework 항목  
 Microsoft.VisualStudio.Profiler.dll  
  
## 함수 정보  
 헤더: VSPerf.h에 선언됨  
  
 가져오기 라이브러리: VSPerf.lib  
  
## 예제  
 다음 예제에서는 ResumeProfile 함수를 보여 줍니다.  이 예제에서는 [PROFILE\_CURRENTID](../profiling/profile-currentid.md)로 지정한 동일 프로세스나 스레드에 대해 SuspendProfile 메서드를 호출한 것으로 가정합니다.  
  
```  
void ExerciseResumeProfile()  
{  
    // The initial value of the Suspend/Resume counter is 0.   
    // Each call to SuspendProfile adds 1 to the Suspend/Resume   
    // count; each call to ResumeProfile subtracts 1.   
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold result of call to ResumeProfile  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = ResumeProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("ResumeProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## 참고 항목  
 [Visual Studio 프로파일러 API 참조\(네이티브\)](../profiling/visual-studio-profiler-api-reference-native.md)