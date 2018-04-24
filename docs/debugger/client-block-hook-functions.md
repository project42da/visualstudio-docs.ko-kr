---
title: 클라이언트 블록 후크 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- client blocks, validating and reporting data
- debugging [C++], hook functions
- _CrtSetDumpClient function
- client blocks, hook functions
- hooks, client block
ms.assetid: f21c197e-565d-4e3f-9b27-4c018c9b87fc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: eccc1781174394da333d2fc703fec0b4d31e522a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="client-block-hook-functions"></a>클라이언트 블록 후크 함수
적절한 함수를 작성하여 `_CLIENT_BLOCK` 블록에 저장되는 데이터 내용을 보고하거나 그 유효성을 검사할 수 있습니다. CRTDBG.H에 정의된 대로 다음과 같은 프로토타입을 가진 함수를 작성해야 합니다.  
  
```  
void YourClientDump(void *, size_t)  
  
```  
  
 즉, 후크 함수를 승인할지는 **void** 함께 할당 블록의 시작 부분에 대 한 포인터는 **size_t** 할당 크기를 나타내는 값을 입력 하 고 반환`void`. 그 외에도 원하는 내용을 추가할 수 있습니다.  
  
 사용 하 여 후크 함수를 설치 했으면 [_CrtSetDumpClient](/cpp/c-runtime-library/reference/crtsetdumpclient), 될 때마다 호출 됩니다는 `_CLIENT_BLOCK` 블록을 덤프할 합니다. 사용할 수 있습니다 [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype) 형식이 나 덤프 한 블록의 하위 형식에 대 한 정보를 얻을 수 있습니다.  
  
 전달 하는 함수에 포인터 `_CrtSetDumpClient` 유형의 **_CRT_DUMP_CLIENT**CRTDBG에 정의 된 대로 합니다. H:  
  
```  
typedef void (__cdecl *_CRT_DUMP_CLIENT)  
   (void *, size_t);  
```  
  
## <a name="see-also"></a>참고 항목  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)   
 [crt_dbg2 샘플](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)   
 [_CrtReportBlockType](/cpp/c-runtime-library/reference/crtreportblocktype)