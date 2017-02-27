---
title: "CRT 디버깅 기술 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime.debugging"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "CRT, 디버깅"
  - "디버깅[C++], CRT 디버그 지원"
  - "디버깅[CRT]"
ms.assetid: 9be561f6-14a8-44ff-925d-d911d5b8e6ff
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# CRT 디버깅 기술
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

C 런타임 라이브러리를 사용하는 프로그램을 디버깅할 경우 다음 디버깅 기술이 유용할 수 있습니다.  
  
## 단원 내용  
 [CRT 디버그 라이브러리 사용](../debugger/crt-debug-library-use.md)  
 C 런타임 라이브러리에서 지원하는 디버깅에 대해 설명하고 도구 액세스에 대한 지침을 제공합니다.  
  
 [보고서 매크로](../debugger/macros-for-reporting.md)  
 CRTDBG.H에 정의된 **\_RPTn**과 **\_RPTFn** 매크로에 대한 정보를 제공합니다. 디버깅에 이러한 매크로가 `printf` 문 대신 사용됩니다.  
  
 [힙 할당 함수의 디버그 버전](../debugger/debug-versions-of-heap-allocation-functions.md)  
 CRT에서 호출을 매핑하는 방법, CRT의 명시적 호출로 인한 장점, 변환을 피하는 방법, 클라이언트 블록에서 별도의 할당 형식 추적 및 \_DEBUG를 정의하지 않았을 때의 결과 등을 포함하여 힙 할당 함수의 특정 디버그 버전에 대해 설명합니다.  
  
 [CRT 디버그 힙 정보](../debugger/crt-debug-heap-details.md)  
 메모리 관리 및 디버그 힙, 디버그 힙의 블록 형식, 디버그 힙 사용, 힙 상태 보고 함수 및 힙 할당 요청 추적 등으로의 링크를 제공합니다.  
  
 [디버그 후크 함수 작성](../debugger/debug-hook-function-writing.md)  
 클라이언트 블록 후크 함수, 할당 후크 함수, 할당 후크 및 CRT 메모리 할당, 보고서 후크 함수 등으로의 링크를 제공합니다.  
  
 [CRT 라이브러리를 사용하여 메모리 누수 찾기](../debugger/finding-memory-leaks-using-the-crt-library.md)  
 디버거 및 C 런타임 라이브러리를 사용하여 메모리 누수를 탐지하고 격리하는 기술에 대해 설명합니다.  
  
## 관련 단원  
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)  
 C 및 C\+\+ 응용 프로그램의 몇 가지 일반적인 디버깅 문제와 기술에 대해 설명합니다.  
  
 [디버거 보안](../debugger/debugger-security.md)  
 보다 안전한 디버깅을 위한 지침을 제공합니다.