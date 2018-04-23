---
title: 디버거 외부에서 프로그램을 실행하는 경우 액세스 위반을 어떻게 디버깅할 수 있습니까? | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47941b2d98029c6466451fb947e31e71d14e6c57
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>디버거 외부에서 프로그램을 실행하는 경우 액세스 위반을 어떻게 디버깅할 수 있습니까?
## <a name="problem-description"></a>문제 설명  
 프로그램이 Visual Studio 환경에서 올바르게 실행됩니다. 그러나 Windows 운영 체제에서 독립 실행형으로 실행하면 액세스 위반이 발생합니다. 이 문제를 어떻게 디버깅할 수 있습니까?  
  
## <a name="solution"></a>솔루션  
 설정의 [Just in time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md) 옵션 및 액세스 위반이 발생할 때까지 독립 실행형 프로그램을 실행 합니다. 그런 다음는 **액세스 위반** 대화 상자를 클릭할 수 있는 **취소** 디버거를 시작 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버깅 Faq](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)