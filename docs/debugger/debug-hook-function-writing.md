---
title: 디버그 후크 함수 작성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.hooks
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], CRT debug support
- debug hook functions
- hooks, debug
- hooks
- debugging [CRT], debug hook functions
ms.assetid: 5510635f-cf69-4907-b72d-ae27af1f19af
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 788f340d72bfea0f3ee1dbdd38dc939d7bb374ca
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-hook-function-writing"></a>디버그 후크 함수 작성
이 단원에서는 디버거의 표준 처리 과정에서 미리 정의된 특정 지점에 코드를 삽입하기 위해 작성할 수 있는 여러 가지 사용자 지정 디버그 후크 함수에 대해 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [클라이언트 블록 후크 함수](../debugger/client-block-hook-functions.md)  
 _CLIENT_BLOCK 블록에 저장되는 데이터의 내용을 보고하거나 그 유효성을 검사하는 함수의 프로토타입과 작성 지침을 제공합니다.  
  
 [할당 후크 함수](../debugger/allocation-hook-functions.md)  
 할당 후크 함수를 정의하고 여러 가지 용도를 파악하고 제한 사항을 알아 보며 프로토타입을 제공합니다.  
  
 [할당 후크 및 CRT 메모리 할당](../debugger/allocation-hooks-and-c-run-time-memory-allocations.md)  
 내부 메모리를 할당하는 C 런타임 라이브러리 함수를 호출할 때 `_CRT_BLOCK` 블록을 명시적으로 무시하는 할당 후크 함수에 대한 제한 사항에 대해 설명합니다. 이 항목의 결과 할당 후크 무시 하지 않으면도 나열 되어 `_CRT_BLOCK` 블록 (예제) 및 기본 할당을 변경 하는 방법에 대 한 후크 함수 **CrtDefaultAllocHook**합니다.  
  
 [보고서 후크 함수](../debugger/report-hook-functions.md)  
 특정 형식의 할당에 맞게 보고서를 필터링하는 데 사용할 수 있는 `_CrtSetReportHook` 함수에 대해 설명하고 프로토타입을 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [CRT 디버깅 기술](../debugger/crt-debugging-techniques.md)  
 CRT 디버그 라이브러리 사용, 보고서 매크로, `malloc`과 `_malloc_dbg`의 차이, 디버그 후크 함수 작성, CRT 디버그 힙 등과 같은 C 런타임 라이브러리의 디버깅 기술에 대해 설명합니다.