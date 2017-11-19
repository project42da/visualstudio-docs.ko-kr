---
title: "보고서 후크 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- hooks, report
- _CrtDbgReport function
- debugger, report hook functions
- memory allocation, debug heap
- debugging [C++], hook functions
- _CrtSetReportHook function
- report hook functions
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51fd8ce8618dfa7b3e8adcc7326c57905d325999
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="report-hook-functions"></a>보고서 후크 함수
보고서 후크 함수를 사용 하 여 설치 [_CrtSetReportHook](/cpp/c-runtime-library/reference/crtsetreporthook), 때마다 호출 됩니다 [_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) 디버그 보고서를 생성 합니다. 보고서 후크 함수를 사용하여 특정한 할당 형식에 맞게 보고서를 필터링할 수 있습니다. 보고서 후크 함수에는 다음과 같이 프로토타입이 있어야 합니다.  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 전달 하는 포인터 **_CrtSetReportHook** 유형의 **_CRT_REPORT_HOOK**CRTDBG에 정의 된 대로 합니다. H:  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 후크 함수를 호출 하는 런타임 라이브러리는 *nRptType* 보고서 범주를 포함 하는 인수 (**_CRT_WARN**, **_CRT_ERROR**, 또는 **_CRT _ASSERT**), *szMsg* 완벽 하 게 어셈블된 보고서 메시지 문자열에 대 한 포인터를 포함 하 고 *retVal* 지정 여부 `_CrtDbgReport` 정상적인 실행을 계속 해야 보고서 또는 디버거에서 시작을 생성 합니다. (A *retVal* 값이 0 이면 계속 실행 하 고 값이 1 디버거를 시작 합니다.)  
  
 반환 해야 하는 경우는 해당 메시지를 후크가 완전히 처리는 더 이상 보고 하지 않으려면 검사가 필요 하도록, **TRUE**합니다. 반환 하는 경우 **FALSE**, `_CrtDbgReport` 보고 메시지를 정상적으로 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 샘플](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)