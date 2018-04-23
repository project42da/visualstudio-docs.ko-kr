---
title: Win32 오류 코드를 어디에서 찾을 수 있습니까? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81d919733f1caf654460cf342da05f2549dfa167
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="where-can-i-look-up-win32-error-codes"></a>Win32 오류 코드를 어디에서 찾을 수 있습니까?
기본 시스템 설치의 INCLUDE 디렉터리에 있는 WINERROR.H에는 Win32 API 함수에 대한 오류 코드 정의가 포함되어 있습니다.  
  
 코드를 입력 하 여 오류 코드를 조회할 수 있습니다는 **조사식** 창 또는 **간략 한 조사식** 대화 상자. 예를 들어:  
  
```  
0x80000004,hr  
```  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버깅 Faq](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)