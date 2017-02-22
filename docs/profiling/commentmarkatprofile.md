---
title: "CommentMarkAtProfile | Microsoft Docs"
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
  - "CommentMarkAtProfile"
  - "CommentMarkAtProfileA"
ms.assetid: 04294ca3-bf9c-4c76-86f1-898c2140de27
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# CommentMarkAtProfile
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`CommentMarkAtProfile` 메서드는 .vsp 파일에 타임스탬프 값, 숫자 표시 및 주석 문자열을 삽입합니다.  타임스탬프 값은 외부 이벤트의 동기화에 사용할 수 있습니다.  표시와 주석을 삽입하려면 CommentMarkAtProfile 함수가 포함된 스레드의 프로파일링이 ON이어야 합니다.  
  
## 구문  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkAtProfile (  
                                   __int64 dnTimestamp,  
                                   long lMarker,  
                                   LPCTSTR szComment);  
```  
  
#### 매개 변수  
 `dnTimestamp`  
  
 타임스탬프 값을 나타내는 64비트 정수입니다.  
  
 `lMarker`  
  
 삽입할 숫자 마커입니다.  마커는 0보다 크거나 같아야 합니다.  
  
 `szComment`  
  
 삽입할 텍스트 문자열에 대한 포인터입니다.  문자열은 NULL 종결자를 포함하여 256자 미만이어야 합니다.  
  
## 속성 값\/반환 값  
 이 함수는 **PROFILE\_COMMAND\_STATUS** 열거형을 사용하여 성공 또는 실패를 나타냅니다.  반환 값은 다음 중 하나일 수 있습니다.  
  
|열거자|설명|  
|---------|--------|  
|MARK\_ERROR\_MARKER\_RESERVED|매개 변수는 0 보다 작거나 같습니다.  이러한 값은 예약되어 있습니다.  표시와 주석이 기록되지 않습니다.|  
|MARK\_ERROR\_MODE\_NEVER|함수가 호출될 때 프로파일링 모드가 NEVER로 설정되어 있었습니다.  표시와 주석이 기록되지 않습니다.|  
|MARK\_ERROR\_MODE\_OFF|함수가 호출될 때 프로파일링 모드가 OFF로 설정되어 있었습니다.  표시와 주석이 기록되지 않습니다.|  
|MARK\_ERROR\_NO\_SUPPORT|이 컨텍스트에서는 표시가 지원되지 않습니다.  표시와 주석이 기록되지 않습니다.|  
|MARK\_ERROR\_OUTOFMEMORY|메모리에 이벤트를 기록할 수 없습니다.  표시와 주석이 기록되지 않습니다.|  
|MARK\_TEXTTOOLONG|문자열이 최대값인 256자를 초과합니다.  주석 문자열이 잘리고 표시와 주석이 기록됩니다.|  
|MARK\_OK|MARK\_OK는 성공을 나타내기 위해 반환됩니다.|  
  
## 설명  
 Mark 명령 또는 API 함수\(CommentMarkAtProfile, CommentMarkProfile 또는 MarkProfile\)로 표시와 주석을 삽입할 때는 표시 프로필 함수가 포함된 스레드의 프로파일링 상태가 ON이어야 합니다.  프로필 표시는 범위에서 전역적입니다.  예를 들어, 한 스레드에 삽입된 프로필 표시를 사용하여 .vsp 파일의 임의 스레드에 있는 데이터 세그먼트의 시작 또는 끝을 표시할 수 있습니다.  
  
> [!IMPORTANT]
>  CommentMarkAtProfile 메서드는 계측에만 사용해야 합니다.  
  
## 해당 .NET Framework 항목  
 Microsoft.VisualStudio.Profiler.dll  
  
## 함수 정보  
  
|||  
|-|-|  
|**Header**|VSPerf.h 포함|  
|**라이브러리**|VSPerf.lib 사용|  
|**유니코드\(Unicode\)**|CommentMarkAtProfileW\(유니코드\) 및 CommentMarkAtProfileA\(ANSI\)로 구현됩니다.|  
  
## 예제  
 다음 코드에서는 CommentMarkAtProfile 제네릭 함수 호출의 사용 예를 보여 줍니다.  이 예제에서는 Win32 문자열 매크로와 ANSI 컴파일러 설정을 사용하여 코드가 ANSI 지원 함수를 호출하는지 여부를 확인하는 것으로 가정합니다.  
  
```  
void ExerciseCommentMarkAtProfile(void)  
{  
    // Declare and initalize variables to pass to   
    // CommentMarkAtProfile.  The values of these   
    // parameters are assigned based on the needs   
    // of the code; and for the sake of simplicity  
    // in this example, the variables are assigned  
    // arbitrary values.  
    int64 timeStamp = 0x1111;  
    long markId = 01;  
    TCHAR * markText = TEXT("Exercising CommentMarkAtProfile...");  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare MarkOperationResult Enumerator.    
    // Holds return value from call to CommentMarkAtProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    markResult = CommentMarkAtProfile(  
        timeStamp,  
        markId,  
        markText);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("CommentMarkAtProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
    pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## 참고 항목  
 [Visual Studio 프로파일러 API 참조\(네이티브\)](../profiling/visual-studio-profiler-api-reference-native.md)