---
title: Microsoft Visual Studio Debugger (예외 Throw) 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- vs.debug.exceptions.thrown
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Microsoft Visual Studio Debugger (Exception Thrown) dialog box
- exception handling, during debugging
- debugger, exceptions
- throwing exceptions, during debugging
ms.assetid: 1fe98d10-c8f9-4b39-a920-99169bfd542e
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1020711c21fb7171a8f7f8b87296d300f53b78b1
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2018
---
# <a name="microsoft-visual-studio-debugger-exception-thrown-dialog-box"></a>Microsoft Visual Studio Debugger(예외 throw) 대화 상자
프로그램에 예외가 발생하면 나타나는 대화 상자입니다. 이 대화 상자는 throw된 예외의 종류를 보고합니다. 코드를 통해 이 예외를 처리해야 합니다. 선택할 수 있는 예외 처리 옵션은 다음과 같습니다.  
  
 **Break**  
 프로그램의 실행을 중단하고 디버거를 시작합니다. 실행을 중단하기 전에는 예외 처리기가 호출되지 않습니다. 중단 위치에서 실행을 계속하면 예외 처리기가 호출됩니다.  
  
 **Continue**  
 실행을 계속하여 예외 처리기에 예외를 처리할 기회를 줍니다. 특정 유형의 예외에는 이 옵션을 사용할 수 없습니다. **계속** 하면 응용 프로그램을 계속 합니다. 네이티브 응용 프로그램에서는 예외가 다시 throw됩니다. 관리되는 응용 프로그램에서는 프로그램이 종료되거나 호스팅 응용 프로그램에서 예외를 처리합니다.  
  
> [!NOTE]
>  관리 코드에서는 처리되지 않은 예외가 발생한 후 실행을 계속할 수 없습니다. 선택 **계속** 후 관리 되는 코드에서 처리 되지 않은 예외 발생 하면 디버깅이 중지 합니다.  
  
 **무시**  
 예외 처리기를 호출하지 않고 실행을 계속합니다. 예외 처리기가 호출되지 않으므로 추가적인 예외 및 오류를 비롯한 후속 결과가 발생할 수 있습니다. 특정 유형의 예외에는 이 옵션을 사용할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)   
 [예외에 대한 모범 사례](/dotnet/standard/exceptions/best-practices-for-exceptions)   
 [예외 처리](/cpp/windows/exception-handling-cpp-component-extensions)