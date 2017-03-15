---
title: "NameProfile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "NameProfile"
  - "NameProfileA"
ms.assetid: 1bb05441-c4ff-4323-9fef-f3924fba4430
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# NameProfile
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`NameProfile` 함수는 지정된 프로세스나 스레드에 문자열을 할당합니다.  
  
 NameProfile API는 계측 프로파일링에만 사용할 수 있습니다.  샘플링 프로파일링에서는 NameProfile API가 지원되지 않습니다.  
  
## 구문  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI NameProfile(  
                                   LPCTSTR pszName,   
                                   PROFILE_CONTROL_LEVEL Level,  
                                   unsigned int dwId);  
```  
  
#### 매개 변수  
 `pszName`  
  
 프로파일링 요소의 이름입니다.  다음과 같은 경우에는 이름이 유효하지 않습니다. 이 경우 NameProfileA에서 NAME\_ERROR\_INVALID\_NAME을 반환합니다.  
  
-   NameProfileA에 전달된 포인터가 NULL 값인 경우  
  
-   pszName의 문자열 데이터가 숫자로 시작되는 경우  
  
-   pszName의 문자열 데이터에 공백이 들어 있는 경우  
  
-   pszName의 문자열 데이터에 ,;.\`~\!@\#$%^&\*\(\)\=\[\]{}&#124;\\?\/\<\> 문자 중 하나를 포함합니다.  
  
 `Level`  
  
 성능 데이터 수집이 적용될 수 있는 프로필 수준을 나타냅니다.  다음 **PROFILE\_CONTROL\_LEVEL** 값을 사용하여 성능 데이터 수집이 적용될 수 있는 세 가지 수준 중 하나를 나타낼 수 있습니다.  
  
|열거자|설명|  
|---------|--------|  
|PROFILE\_GLOBALLEVEL|전역 수준 설정은 프로파일링 실행의 모든 프로세스와 스레드에 적용됩니다.|  
|PROFILE\_PROCESSLEVEL|프로세스 수준 설정은 지정된 프로세스의 일부인 모든 스레드에 적용됩니다.|  
|PROFILE\_THREADLEVEL|스레드 프로파일링 수준 설정은 지정된 스레드에 적용됩니다.|  
  
 `dwId`  
  
 프로파일링 수준 식별자입니다.  시스템에 의해 생성된 프로세스 또는 스레드 식별자를 사용합니다.  
  
## 속성 값\/반환 값  
 이 함수는 **PROFILE\_COMMAND\_STATUS** 열거형을 사용하여 성공 또는 실패를 나타냅니다.  반환 값은 다음 중 하나일 수 있습니다.  
  
|열거자|설명|  
|---------|--------|  
|NAME\_ERROR\_ID\_NOEXIST|지정한 프로파일링 요소가 없습니다.|  
|NAME\_ERROR\_INVALID\_NAME|이름이 잘못되었습니다.|  
|NAME\_ERROR\_LEVEL\_NOEXIST|지정한 프로필 수준이 없습니다.|  
|NAME\_ERROR\_NO\_SUPPORT|지정한 작업이 지원되지 않습니다.|  
|NAME\_ERROR\_OUTOFMEMORY|메모리에 이벤트를 기록할 수 없습니다.|  
|NAME\_ERROR\_REDEFINITION|프로필 요소에 이름이 이미 할당되어 있습니다.  이 함수의 이름은 무시됩니다.|  
|NAME\_ERROR\_TEXTTRUNCATED|이름 텍스트가 32자를 초과\(null 문자 포함\)하므로 이름이 잘렸습니다.|  
|NAME\_OK|이름이 성공적으로 등록되었습니다.|  
  
## 설명  
 각 프로세스나 스레드에는 하나의 이름만 할당할 수 있습니다.  프로파일링 요소에 이름을 지정한 뒤에는 해당 요소의 NameProfile에 대한 이후 호출은 무시됩니다.  
  
 다른 스레드나 프로세스에 같은 이름이 지정되면 해당 이름의 해당 수준에 있는 모든 요소의 데이터가 보고서에 포함됩니다.  
  
 현재 프로세스 또는 스레드가 아닌 프로세스 또는 스레드를 지정할 경우, 해당 프로세스 또는 스레드가 초기화되었고 실행이 시작되었는지 확인한 후에 이름을 지정해야 합니다.  그렇지 않으면 NameProfile 메서드는 실패합니다.  
  
> [!IMPORTANT]
>  CreateProcess\(\) 및 CreateThread\(\) API 함수는 스레드나 프로세스가 초기화되기 전에 반환할 수 있습니다.  
  
## 해당 .NET Framework 항목  
 Microsoft.VisualStudio.Profiler.dll  
  
## 함수 정보  
  
|||  
|-|-|  
|**Header**|VSPerf.h 포함|  
|**라이브러리**|VSPerf.lib 사용|  
|**유니코드\(Unicode\)**|`NameProfileW` \(유니코드\) 및 `NameProfileA`\(ANSI\)로 구현됩니다.|  
  
## 예제  
 다음 코드에서는 NameProfile 함수 호출의 예를 보여 줍니다.  이 예제에서는 Win32 문자열 매크로와 ANSI 컴파일러 설정을 사용하여 코드가 ANSI 지원 함수를 호출하는지 여부를 확인하는 것으로 가정합니다.  
  
```  
void ExerciseNameProfile()  
{  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Create and initialize variables to pass to   
    // ExerciseNameProfile.  The value of this   
    // parameter is based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variable is assigned an arbitrary value.  
    TCHAR * profileName = TEXT("ExerciseNameProfile");  
  
    // Declare enumeration to hold result of call to   
    // ExerciseNameProfle.  
    PROFILE_COMMAND_STATUS nameResult;  
  
    nameResult =  NameProfile(  
        profileName,  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("NameProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, nameResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## 참고 항목  
 [Visual Studio 프로파일러 API 참조\(네이티브\)](../profiling/visual-studio-profiler-api-reference-native.md)