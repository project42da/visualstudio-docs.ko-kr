---
title: "보고서 후크 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.hooks"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "_CrtDbgReport 함수"
  - "_CrtSetReportHook 함수"
  - "디버거, 보고서 후크 함수"
  - "디버깅[C++], 후크 함수"
  - "후크, 보고서"
  - "메모리 할당, 디버그 힙"
  - "보고서 후크 함수"
ms.assetid: 1854bca7-d7eb-4502-89bf-b1ee64cb50ef
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 보고서 후크 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[\_CrtSetReportHook](/visual-cpp/c-runtime-library/reference/crtsetreporthook)를 사용하여 설치한 보고서 후크 함수는 [\_CrtDbgReport](/visual-cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw)가 디버그 보고서를 생성할 때마다 호출됩니다.  보고서 후크 함수를 사용하여 특정한 할당 형식에 맞게 보고서를 필터링할 수 있습니다.  보고서 후크 함수에는 다음과 같이 프로토타입이 있어야 합니다.  
  
```  
int YourReportHook(int nRptType, char *szMsg, int *retVal);  
```  
  
 **\_CrtSetReportHook** 에 전달한 포인터는 CRTDBG.H에 정의된 대로 **\_CRT\_REPORT\_HOOK** 형식입니다.  
  
```  
typedef int (__cdecl *_CRT_REPORT_HOOK)(int, char *, int *);  
```  
  
 런타임 라이브러리가 후크 함수를 호출하면, *nRptType* 인수는 보고서의 범주\(**\_CRT\_WARN**, **\_CRT\_ERROR** 또는 **\_CRT\_ASSERT**\)를 포함하고, *szMsg*는 완전히 어셈블된 보고서 메시지 문자열에 대한 포인터를 포함하며, *retVal*은 보고서 생성 후에 `_CrtDbgReport`가 계속 정상적으로 실행되어야 할 것인지 또는 디버거를 시작해야 할 것인지 지정합니다. *retVal* 값이 0이면 계속 실행하고 값이 1이면 디버거를 시작합니다.  
  
 요청한 메시지를 후크가 완전히 처리하여 더 이상 보고할 필요가 없으면 **TRUE**를 반환해야 합니다.  **FALSE**를 반환하면 `_CrtDbgReport`가 정상적으로 메시지를 보고합니다.  
  
## 참고 항목  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt\_dbg2 Sample](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167)