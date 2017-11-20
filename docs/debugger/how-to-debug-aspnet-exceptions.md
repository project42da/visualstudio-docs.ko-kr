---
title: "방법: ASP.NET 예외 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
- debugging [Visual Studio], ASP.NET exceptions
- ASP.NET, exceptions
- exceptions, ASP.NET
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba38521b8d3d224d6544d95b947d5f0e29727c0a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-aspnet-exceptions"></a>방법: ASP.NET 예외 디버깅
예외 디버깅은 강력한 개발의 중요 한 부분이 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램입니다. 예외를 디버깅 하는 방법에 대 한 일반 정보는 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)합니다.  
  
 처리 되지 않은 디버깅 하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 예외를 제외 해야 하며 디버거에서 중지 하도록 합니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 런타임에는 최상위 예외 처리기가 있습니다. 따라서 디버거는 처리되지 않은 예외에서 기본적으로 중단되지 않습니다. 예외가 throw 될 때 디버거를 중단을을 선택 해야 **예외가 발생 하는 경우 중단: Throw 됩니다** 에서 특정 예외에 대 한 설정의 **예외** 대화 상자.  
  
 내 코드만 사용 하는 경우 **예외가 발생 하는 경우 중단: Throw 됩니다** .NET Framework 메서드 또는 다른 시스템 코드에서 예외가 throw 되 면 즉시 중단 하도록 디버거를 일으키지 않습니다. 이러한 경우 디버거의 실행은 비시스템 코드를 적중해야 중단됩니다. 그러므로 예외가 발생할 때 시스템 코드를 단계별로 수행할 필요가 없습니다.  
  
 내 코드만 훨씬 더 유용할 수 있는 다른 옵션을 제공: **예외가 발생 하는 경우 중단: 사용자가 처리**합니다. 예외에 대해 이 설정을 선택하면 디버거는 사용자 코드에서 예외를 catch하여 처리하지 않는 경우에 한해서만 사용자 코드에서 실행을 중단합니다. 이렇게 설정할 경우 최상위 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 예외 처리기가 사용자가 작성하지 않은 코드에 있기 때문에 해당 처리기의 결과가 무시됩니다.  
  
### <a name="to-enable-debugging-of-aspnet-exceptions-with-just-my-code"></a>내 코드만 옵션을 사용하여 ASP.NET 예외 디버깅을 설정하려면  
  
1.  에 **디버그** 메뉴를 클릭 하 여 **예외**합니다.  
  
     **예외** 대화 상자가 나타납니다.  
  
2.  에 **공용 언어 런타임 예외** 행, **throw 됨** 또는 **사용자가 처리**합니다.  
  
     사용 하는 **사용자가 처리** 설정을 **내 코드만** 활성화 해야 합니다.  
  
### <a name="to-use-best-practices-for-aspnet-exception-handling"></a>최상의 방법으로 ASP.NET 예외 처리를 수행하려면  
  
-   예측 가능하며 처리 방법을 알고 있는 예외를 throw할 수 있는 코드의 바깥쪽에 `try ... catch` 블록을 배치합니다. 예를 들어 응용 프로그램이 SQL Server에 직접 또는 XML 웹 서비스를 호출 하는, 해당 코드에 있어야 **try … catch** 발생할 수 있는 다양 한 예외가 때문에 차단 합니다.

## <a name="see-also"></a>참고 항목
[ASP.NET 응용 프로그램 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)