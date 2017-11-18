---
title: "할당 후크 및 C 런타임 메모리 할당 | Microsoft Docs"
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
- debugging [C++], hook functions
- memory allocation, troubleshooting allocation hooks
- allocation hooks
- hooks, allocation
ms.assetid: cc34ee96-3d91-41bd-a019-aa3759139e7e
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62a8be3b1a1c98a330efeb26d9a84e74f2334423
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="allocation-hooks-and-c-run-time-memory-allocations"></a>할당 후크 및 C 런타임 메모리 할당
할당 후크 함수가 내부 메모리를 할당하는 C 런타임 라이브러리 함수를 호출하는 경우, C 런타임 라이브러리 함수가 내부적으로 만든 메모리 할당인 `_CRT_BLOCK` 블록을 명시적으로 무시한다는 점은 매우 중요한 제한입니다. 할당 후크 함수의 처음에 다음과 같은 코드를 포함하여 `_CRT_BLOCK` 블록을 무시할 수 있습니다.  
  
```  
if ( nBlockUse == _CRT_BLOCK )  
    return( TRUE );  
```  
  
 할당 후크가 `_CRT_BLOCK` 블록을 무시하지 않으면 후크에서 호출한 모든 C 런타임 라이브러리 함수는 무한 루프에서 프로그램을 트래핑할 수 있습니다. 예를 들어, `printf`는 내부 할당을 만듭니다. 후크 코드가 호출 `printf`, 결과 할당 후크가 다시 호출 수는 것으로 인해 **printf** 다시 그에 스택 오버플로가 발생할 때까지 합니다. `_CRT_BLOCK` 할당 작업을 보고해야 할 경우, 이러한 제한을 피하려면 형식 지정과 출력에 C 런타임 함수 대신 Windows API 함수를 사용해야 합니다. Windows API는 C 런타임 라이브러리 힙을 사용하지 않기 때문에 무한 루프에서 할당 후크를 트래핑하지 않습니다.  
  
 나타납니다 런타임 라이브러리 소스 파일을 검사 하면 기본 할당 후크 함수는 **CrtDefaultAllocHook** (만 반환 **TRUE**), 자체적으로 별도 파일에 위치 DBGHOOK 합니다. 3. 응용 프로그램 먼저 실행 되는 실행 시간 시작 코드가 생성 된 할당에 대해서도 호출 될 할당 후크 하려는 경우 **주** 함수 대신 고유한 중 하나가 지정 된이 기본 함수를 바꿀 수 있습니다 사용 하 여 [_CrtSetAllocHook](/cpp/c-runtime-library/reference/crtsetallochook)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 샘플](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)