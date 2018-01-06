---
title: "방법: 네이티브 코드에 스레드 이름 설정 | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], threads
- SetThreadName function
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c85d0968-9f22-4d69-87f4-acca2ae777b8
caps.latest.revision: "37"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 34340fc1a56c3b35c626cbd48157b1b09d0cd91d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-thread-name-in-native-code"></a>방법: 네이티브 코드에 스레드 이름 설정
스레드 명명 기능은 Visual Studio의 모든 버전에서 사용할 수 있습니다. 스레드 명명 기능은에서 스레드를 추적할 때 유용는 **스레드** 창.

프로그램의 스레드 이름을 설정하려면 다음 코드 예제와 같이 `SetThreadName` 함수를 사용합니다. `threadName` 매개 변수에 대한 메모리가 해제될 수 있도록 스레드 이름이 스레드에 복사됩니다.  
  
## <a name="example"></a>예  
  
```C++  
//  
// Usage: SetThreadName ((DWORD)-1, "MainThread");  
//  
#include <windows.h>  
const DWORD MS_VC_EXCEPTION = 0x406D1388;  
#pragma pack(push,8)  
typedef struct tagTHREADNAME_INFO  
{  
    DWORD dwType; // Must be 0x1000.  
    LPCSTR szName; // Pointer to name (in user addr space).  
    DWORD dwThreadID; // Thread ID (-1=caller thread).  
    DWORD dwFlags; // Reserved for future use, must be zero.  
 } THREADNAME_INFO;  
#pragma pack(pop)  
void SetThreadName(DWORD dwThreadID, const char* threadName) {  
    THREADNAME_INFO info;  
    info.dwType = 0x1000;  
    info.szName = threadName;  
    info.dwThreadID = dwThreadID;  
    info.dwFlags = 0;  
#pragma warning(push)  
#pragma warning(disable: 6320 6322)  
    __try{  
        RaiseException(MS_VC_EXCEPTION, 0, sizeof(info) / sizeof(ULONG_PTR), (ULONG_PTR*)&info);  
    }  
    __except (EXCEPTION_EXECUTE_HANDLER){  
    }  
#pragma warning(pop)  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [방법: 관리 코드에 스레드 이름 설정](../debugger/how-to-set-a-thread-name-in-managed-code.md)