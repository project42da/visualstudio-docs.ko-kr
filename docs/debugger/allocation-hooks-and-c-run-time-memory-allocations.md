---
title: "할당 후크 및 C 런타임 메모리 할당 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "할당 후크"
  - "디버깅[C++], 후크 함수"
  - "후크, 할당"
  - "메모리 할당, 할당 후크 문제 해결"
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# 할당 후크 및 C 런타임 메모리 할당
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

할당 후크 함수가 내부 메모리를 할당하는 C 런타임 라이브러리 함수를 호출하는 경우, C 런타임 라이브러리 함수가 내부적으로 만든 메모리 할당인 `_CRT_BLOCK` 블록을 명시적으로 무시한다는 점은 매우 중요한 제한입니다.  할당 후크 함수의 처음에 다음과 같은 코드를 포함하여 `_CRT_BLOCK` 블록을 무시할 수 있습니다.  
  
```  
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 할당 후크가 `_CRT_BLOCK` 블록을 무시하지 않으면 후크에서 호출한 모든 C 런타임 라이브러리 함수는 무한 루프에서 프로그램을 트래핑할 수 있습니다.  예를 들어, `printf`는 내부 할당을 만듭니다.  후크 코드가 `printf`를 호출하면 결과 할당으로 인해 후크가 다시 호출되어 **printf**를 다시 호출하고 스택에 오버플로가 발생할 때까지 이 과정이 계속됩니다.  `_CRT_BLOCK` 할당 작업을 보고해야 할 경우, 이러한 제한을 피하려면 형식 지정과 출력에 C 런타임 함수 대신 Windows API 함수를 사용해야 합니다.  Windows API는 C 런타임 라이브러리 힙을 사용하지 않기 때문에 무한 루프에서 할당 후크를 트래핑하지 않습니다.  
  
 런타임 라이브러리 소스 파일을 검사하면 기본 할당 후크 함수 **CrtDefaultAllocHook**\(**TRUE**만 반환\)가 자체 별도 파일인 DBGHOOK.C에 있음을 알 수 있습니다.  응용 프로그램의 **main** 함수보다 먼저 실행되는 런타임 시작 코드가 만든 할당에 대해서도 할당 후크를 호출하려면 [\_CrtSetAllocHook](/visual-cpp/c-runtime-library/reference/crtsetallochook)를 사용하지 말고 사용자의 함수로 이 기본 함수를 대체하십시오.  
  
## 참고 항목  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt\_dbg2 Sample](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167)