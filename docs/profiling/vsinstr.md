---
title: "VSInstr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "성능 도구, 계측"
  - "계측, VSInstr 도구"
  - "프로파일링 도구, VSInstr"
  - "명령줄 도구, 계측"
  - "명령줄, 도구"
  - "VSInstr"
  - "VSInstr 도구"
  - "성능 도구, VSInstr 도구"
ms.assetid: 7b1334f7-f9b0-4a82-a145-d0607bfa8467
caps.latest.revision: 44
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 44
---
# VSInstr
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSInstr 도구는 이진을 계측하는 데 사용됩니다.  이 도구는 다음 구문을 사용하여 호출합니다.  
  
```  
VSInstr [/U] filename [/options]  
```  
  
 다음 표에서는 VSInstr 도구 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**Help** 또는 **?**|도움말을 표시합니다.|  
|**U**|리디렉션된 콘솔 출력을 유니코드로 씁니다.  이 옵션을 가장 먼저 지정해야 합니다.|  
|`@filename`|각 줄에 하나의 명령 옵션을 포함하는 응답 파일의 이름을 지정합니다.  물음표는 사용하지 마십시오.|  
|**OutputPath** `:path`|계측된 이미지의 대상 디렉터리를 지정합니다.  출력 경로를 지정하지 않으면 원래 이진 파일의 이름에 "Orig"가 추가되어 동일한 디렉터리에 저장되고, 계측에는 이진 파일의 복사본이 사용됩니다.|  
|**Exclude** `:funcspec`|프로브에 의한 계측에서 제외할 함수 사양을 지정합니다.  함수에 프로파일링 프로브를 삽입하였을 때 예측하지 못한 결과나 원치 않은 결과가 발생한 경우 유용합니다.<br /><br /> 동일한 이진 파일의 함수를 참조하는 **Exclude** 및 **Include** 옵션은 사용하지 마십시오.<br /><br /> 별도의 **Exclude** 옵션을 사용하여 여러 개의 함수 사양을 지정할 수 있습니다.<br /><br /> `funcspec`은 다음과 같이 정의됩니다.<br /><br /> \[namespace\<separator1\>\] \[class\<separator2\>\]function<br /><br /> \<separator1\>은 네이티브 코드의 경우 `::`이고 `.`이고, 관리 코드의 경우 입니다.<br /><br /> \<separator2\>는 항상 `::`입니다.<br /><br /> **Exclude**는 코드 검사에서 지원됩니다.<br /><br /> 와일드카드 문자 \*가 지원됩니다.  예를 들어, 네임스페이스의 모든 함수를 제외하려면 다음과 같이 사용합니다.<br /><br /> MyNamespace::\*<br /><br /> **VSInstr \/DumpFuncs**를 사용하여 지정된 이진 파일에 있는 함수의 전체 이름을 나열할 수 있습니다.|  
|**Include** `:funcspec`|프로브로 계측할 이진 파일의 함수 사양을 지정합니다.  이진 파일의 다른 모든 함수는 계측되지 않습니다.<br /><br /> 별도의 **Include** 옵션을 사용하여 여러 개의 함수 사양을 지정할 수 있습니다.<br /><br /> 동일한 이진 파일의 함수를 참조하는 **Include** 및 **Exclude** 옵션은 사용하지 마십시오.<br /><br /> **Include**는 코드 검사에서 지원되지 않습니다.<br /><br /> `funcspec`은 다음과 같이 정의됩니다.<br /><br /> \[namespace\<separator1\>\] \[class\<separator2\>\]function<br /><br /> \<separator1\>은 네이티브 코드의 경우 `::`이고 `.`이고, 관리 코드의 경우 입니다.<br /><br /> \<separator2\>는 항상 `::`입니다.<br /><br /> 와일드카드 문자 \*가 지원됩니다.  예를 들어, 네임스페이스의 모든 함수를 포함하려면 다음과 같이 사용합니다.<br /><br /> MyNamespace::\*<br /><br /> **VSInstr \/DumpFuncs**를 사용하여 지정된 이진 파일에 있는 함수의 전체 이름을 나열할 수 있습니다.|  
|**DumpFuncs**|지정된 이미지 내의 함수를 나열합니다.  계측이 수행되지 않습니다.|  
|**ExcludeSmallFuncs**|작은 함수는 제외합니다. 작은 함수는 계측에서 함수를 호출하지 않는 간단한 함수입니다.  **ExcludeSmallFuncs** 옵션을 사용하면 계측 오버헤드가 줄어들어 계측 속도가 향상됩니다.<br /><br /> 작은 함수를 제외하면 분석에 필요한 .vsp 파일 크기와 시간도 줄어듭니다.|  
|**Mark:**{**Before** `&#124;`  **After** `&#124;`  **Top** `&#124;` **Bottom**}`,funcname,markid`|.vsp 보고서 파일에서 데이터 범위의 시작 또는 끝을 식별하는 데 사용할 수 있는 프로필 표시\(보고서에서 데이터를 구분하는 데 사용되는 식별자\)를 삽입합니다.<br /><br /> **Before**  ``  \- 대상 함수의 시작 직전입니다.<br /><br /> **After**  ``  \- 대상 함수의 종료 직후입니다.<br /><br /> **Top**  ``  \- 대상 함수의 시작 직후입니다.<br /><br /> **Bottom**  ``  \- 대상 함수에서 각 반환 직전입니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.<br /><br /> `Markid` \- 프로필 표시의 식별자로 사용할 양의 정수\(long\)입니다.|  
|**Coverage**|검사 계측을 수행합니다.  다음 옵션과 함께만 사용할 수 있습니다: **Verbose**, **OutputPath**, **Exclude** 및 **Logfile**..|  
|**Verbose**|**Verbose** 옵션은 계측 프로세스에 대한 세부 정보를 보는 데 사용됩니다.|  
|**NoWarn** `[:[Message Number[;Message Number]]]`|모든 경고나 특정 경고를 표시하지 않습니다.<br /><br /> `Message Number` \- 경고 번호입니다.  `Message Number`를 생략하면 모든 경고가 표시되지 않습니다.<br /><br /> 자세한 내용은 [VSInstr 경고](../profiling/vsinstr-warnings.md)을 참조하십시오.|  
|**Control** `:{` **Thread** `&#124;`  **Process** `&#124;` **Global** `}`|다음 VSInstr 데이터 수집 제어 옵션의 프로파일링 수준을 지정합니다.<br /><br /> **Start**<br /><br /> **StartOnly**<br /><br /> **Suspend**<br /><br /> **StopOnly**<br /><br /> **SuspendOnly**<br /><br /> **ResumeOnly**<br /><br /> **Thread**  ``  \- 스레드 수준의 데이터 수집 제어 함수를 지정합니다.  프로파일링은 현재 스레드에 대해서만 시작 또는 중지됩니다.  다른 스레드의 프로파일링 상태에는 영향이 없습니다.  기본값은 스레드입니다.<br /><br /> **Process**  ``  \- 프로세스 수준의 프로파일링 데이터 수집 제어 함수를 지정합니다.  프로파일링은 현재 프로세스의 모든 스레드에 대해 시작 또는 중지됩니다.  다른 프로세스의 프로파일링 상태에는 영향이 없습니다.<br /><br /> **Global**  ``  \- 전역 수준\(크로스 프로세스\)의 데이터 수집 제어 함수를 지정합니다.<br /><br /> 프로파일링 수준을 지정하지 않으면 오류가 발생합니다.|  
|**Start** `:{` **Inside** `&#124;` **Outside** `},funcname`|데이터 수집을 대상 함수 및 해당 함수에서 호출한 자식 함수로 제한합니다.<br /><br /> **Inside**  ``  \- 대상 함수의 시작 직후에 StartProfile 함수를 삽입합니다.  대상 함수의 각 반환 직전에 StopProfile 함수를 삽입합니다.<br /><br /> **Outside**  ``  \- 대상 함수의 각 호출 직전에 StartProfile 함수를 삽입합니다.  대상 함수의 각 호출 직후에 StopProfile 함수를 삽입합니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.|  
|**Suspend** `:{` **Inside** `&#124;` **Outside** `},funcname`|대상 함수 및 해당 함수가 호출한 자식 함수에 대해 데이터 수집을 제외합니다.<br /><br /> **Inside**  ``  \- 대상 함수의 시작 직후에 SuspendProfile 함수를 삽입합니다.  대상 함수의 각 반환 직전에 ResumeProfile 함수를 삽입합니다.<br /><br /> **Outside**  ``  \- 대상 함수의 시작 직전에 SuspendProfile 함수를 삽입합니다.  대상 함수의 종료 직후에 ResumeProfile 함수를 삽입합니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.<br /><br /> 대상 함수에 StartProfile 함수가 포함된 경우, 그 앞에 SuspendProfile 함수가 삽입됩니다.  대상 함수에 StopProfile 함수가 포함된 경우, 그 뒤에 ResumeProfile 함수가 삽입됩니다.|  
|**StartOnly:** `{` **Before** `&#124;`  **After** `&#124;`  **Top** `&#124;` **Bottom** `},funcname`|프로파일링을 실행하는 동안 데이터 수집을 시작합니다.  지정된 위치에 StartProfile API 함수를 삽입합니다.<br /><br /> **Before**  `` \- 대상 함수의 시작 직전입니다.<br /><br /> **After**  `` \- 대상 함수의 종료 직후입니다.<br /><br /> **Top**  `` \- 대상 함수의 시작 직후입니다.<br /><br /> **Bottom**  `` \- 대상 함수의 각 반환 직전입니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.|  
|**StopOnly:**{**Before** `&#124;`  **After** `&#124;`  **Top** `&#124;` **Bottom**}`,funcname`|프로파일링을 실행하는 동안 데이터 수집을 중단합니다.  지정된 위치에 StopProfile 함수를 삽입합니다.<br /><br /> **Before**  `` \- 대상 함수의 시작 직전입니다.<br /><br /> **After**  `` \- 대상 함수의 종료 직후입니다.<br /><br /> **Top**  `` \- 대상 함수의 시작 직후입니다.<br /><br /> **Bottom**  `` \- 대상 함수의 각 반환 직전입니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.|  
|**SuspendOnly:**{**Before** `&#124;`  **After** `&#124;`  **Top** `&#124;` **Bottom**}`,funcname`|프로파일링을 실행하는 동안 데이터 수집을 중단합니다.  지정된 위치에 SuspendProfile API를 삽입합니다.<br /><br /> **Before**  `` \- 대상 함수의 시작 직전입니다.<br /><br /> **After**  `` \- 대상 함수의 종료 직후입니다.<br /><br /> **Top**  `` \- 대상 함수의 시작 직후입니다.<br /><br /> **Bottom**  `` \- 대상 함수의 각 반환 직전입니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.<br /><br /> 대상 함수에 StartProfile 함수가 포함된 경우, 그 앞에 SuspendProfile 함수가 삽입됩니다.|  
|**ResumeOnly:**{**Before** `&#124;`  **After** `&#124;`  **Top** `&#124;` **Bottom**}`,funcname`|프로파일링을 실행하는 동안 데이터 수집을 시작하거나 다시 시작합니다.<br /><br /> 일반적으로 **SuspendOnly** 옵션이 프로파일링을 중지한 후 프로파일링을 시작하는 데 사용됩니다.  지정된 위치에 ResumeProfile API를 삽입합니다.<br /><br /> **Before**  `` \- 대상 함수의 시작 직전입니다.<br /><br /> **After**  `` \- 대상 함수의 종료 직후입니다.<br /><br /> **Top**  `` \- 대상 함수의 시작 직후입니다.<br /><br /> **Bottom**  `` \- 대상 함수의 각 반환 직전입니다.<br /><br /> `funcname` \- 대상 함수의 이름입니다.<br /><br /> 대상 함수에 StopProfile 함수가 포함된 경우, 그 뒤에 ResumeProfile 함수가 삽입됩니다.|  
  
## 참고 항목  
 [VSPerfMon](../profiling/vsperfmon.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [VSPerfReport](../profiling/vsperfreport.md)   
 [VSInstr 경고](../profiling/vsinstr-warnings.md)   
 [프로파일링 도구 보고서 뷰](../profiling/performance-report-views.md)