---
title: "혼합된 모드 디버깅 프로세스 동안에 microsoft.net Framework 4를 사용 하 여 x64 이상을 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 37d5c52192c30ccc3b34bfa609c3f6a7ffb99566
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>x64 프로세스의 혼합 모드 디버깅은 Microsoft.NET Framework 4 이상을 사용할 때만 지원됩니다.
4 이전의 .NET Framework 버전에서는 x64 프로세스의 혼합 모드 디버깅을 지원하지 않습니다. 따라서 디버깅하는 동안 네이티브 코드에서 관리 코드로 또는 그 반대로 실행할 수 없습니다.  
  
### <a name="workarounds"></a>해결 방법  
  
-   Microsoft .NET Framework 4 이상을 사용하도록 프로젝트를 업데이트합니다.  
  
     또는  
  
     관리 코드와 네이티브 코드를 별도의 디버깅 세션에서 디버깅합니다.  
  
     또는  
  
     다음 절차에 설명된 대로 혼합 코드를 32비트 프로세스로 디버깅합니다.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>플랫폼을 32비트로 변경하려면(Visual Basic 또는 C#)  
  
1.  **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.  
  
2.  속성 페이지에서 클릭 된 **컴파일** 또는 **디버그** 탭 합니다.  
  
3.  클릭 **플랫폼** x86 플랫폼 목록에서 선택 합니다.  
  
     기본적으로 Visual Basic 및 C# 컴파일러에서는 모든 CPU에서 실행할 수 있는 코드를 생성합니다. 이러한 이진 코드는 64비트 컴퓨터에서 64비트 프로세스로 실행됩니다. 선택 해야 하는 32 비트 프로세스를 실행 하려면 **Win32**이 아니라 **AnyCPU**합니다.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>플랫폼을 32비트로 변경하려면(C/C++)  
  
1.  **솔루션 탐색기**, 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 **속성**합니다.  
  
2.  속성 페이지에서 클릭 **플랫폼** Win32 플랫폼 목록에서 선택 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   참조 [SQL 디버깅 설정](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [64비트 응용 프로그램 디버그](../debugger/debug-64-bit-applications.md)