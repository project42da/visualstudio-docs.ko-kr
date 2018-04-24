---
title: DebugBreak 및 __debugbreak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- DebugBreak
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], DebugBreak function
- DebugBreak function
- breakpoints, DebugBreak function
ms.assetid: 9787c795-df94-4f48-bc8d-3bf899b67421
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5eda428410733bf72174676f5a2303a7f625aa7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="debugbreak-and-debugbreak"></a>DebugBreak 및 __debugbreak
DebugBreak Win32 함수를 호출할 수 있습니다 또는 [__debugbreak](/cpp/intrinsics/debugbreak) 코드에서 언제 든 지 내장 함수입니다. `DebugBreak` 및 `__debugbreak`는 해당 위치에 중단점을 설정하는 것과 같은 효과가 있습니다.  
  
 `DebugBreak`는 시스템 함수에 대한 호출이므로 중단 후 올바른 호출 스택 정보가 표시되도록 하려면 시스템 디버그 기호를 설치해야 합니다. 이렇게 하지 않으면 디버거에서 표시하는 호출 스택 정보가 한 프레임씩 차이가 날 수 있습니다. `__debugbreak`를 사용하는 경우에는 기호가 필요하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](/cpp/intrinsics/compiler-intrinsics)   
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [기호 (.pdb)을 지정 하 고 소스 파일](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)