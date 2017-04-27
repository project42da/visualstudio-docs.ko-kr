---
title: "할당 후크 함수 | Microsoft Docs"
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
  - "_CrtSetAllocHook 함수"
  - "할당 후크"
  - "디버깅[C++], 후크 함수"
  - "후크, 할당"
  - "부족한 메모리"
  - "메모리 할당, 할당 정보 로깅"
ms.assetid: 6bfbdb65-8cb1-4c21-8c45-7194a2b77c1e
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# 할당 후크 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[\_CrtSetAllocHook](/visual-cpp/c-runtime-library/reference/crtsetallochook)를 사용하여 설치한 할당 후크 함수는 메모리를 할당하거나 다시 할당하거나 해제할 때마다 호출됩니다.  이러한 후크 형식은 여러 가지 목적으로 사용할 수 있습니다.  예를 들어, 메모리가 부족할 때 응용 프로그램이 이 상황을 어떻게 처리하는지 테스트하거나 할당 패턴을 검사하거나 나중에 분석하기 위해 할당 정보를 기록하는 데 사용할 수 있습니다.  
  
> [!NOTE]
>  [할당 후크 및 C 런타임 메모리 할당](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)을 참조하여 할당 후크 함수에 C 런타임 라이브러리 함수를 사용할 때의 제한 사항에 대해 잘 알아두십시오.  
  
 할당 후크 함수에는 다음과 같은 프로토타입이 있어야 합니다.  
  
```  
int YourAllocHook(int nAllocType, void *pvData,  
        size_t nSize, int nBlockUse, long lRequest,  
        const unsigned char * szFileName, int nLine )  
```  
  
 [\_CrtSetAllocHook](/visual-cpp/c-runtime-library/reference/crtsetallochook)에 전달한 포인터는 CRTDBG.H에 정의된 대로 **\_CRT\_ALLOC\_HOOK** 형식입니다.  
  
```  
typedef int (__cdecl * _CRT_ALLOC_HOOK)  
    (int, void *, size_t, int, long, const unsigned char *, int);  
```  
  
 런타임 라이브러리가 후크를 호출하면 *nAllocType* 인수는 수행할 할당 작업\(예: **\_HOOK\_ALLOC**, **\_HOOK\_REALLOC** 또는 **\_HOOK\_FREE**\)을 표시합니다.  해제하거나 다시 할당할 경우에는 해제할 블록의 사용자 항목에 대한 포인터가 `pvData`에 포함됩니다.  그러나, 할당할 경우에는 할당이 아직 발생하지 않았기 때문에 이 포인터가 null입니다.  해당 할당 크기, 블록 형식, 연결되어 있는 다음 요청 번호, 할당이 이루어진 파일 이름과 줄 번호에 대한 포인터\(있을 경우\) 등은 나머지 인수에 포함되어 있습니다.  후크 함수는 지정된 모든 분석과 작업을 수행한 다음, 할당 작업을 계속할 수 있음을 나타내는 **TRUE** 또는 작업을 중지해야 함을 나타내는 **FALSE**를 반환해야 합니다.  이 간단한 형식의 후크가 이제까지 할당된 메모리 양을 확인하고, 그 양이 한계를 약간이라도 초과하는 경우에는 **FALSE**를 반환할 수 있습니다.  그러면 사용할 수 있는 메모리가 부족한 경우에만 주로 발생하는 할당 오류가 응용 프로그램에 발생합니다.  좀 더 복잡한 후크는 할당 패턴을 추적하거나 메모리 사용을 분석하거나 특정 상황이 발생하는 때를 보고할 수 있습니다.  
  
## 참고 항목  
 [할당 후크 및 C 런타임 메모리 할당](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)   
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt\_dbg2 Sample](http://msdn.microsoft.com/ko-kr/21e1346a-6a17-4f57-b275-c76813089167)