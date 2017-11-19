---
title: "보안 문제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8061c419f81493e56a58df8fefbe4d3362d43e46
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="security-issues"></a>보안 문제
Visual Studio를 사용 하는 프로그램을 디버깅 하려면 권한만 필요한 프로그램을 실행 하는 개발자가 알아야 하는 것과 같은 됩니다. 대부분의 경우 (인터넷 정보 서비스 같은 다른 서비스와 관련 된 경우가 더 높은 수준의 권한 요구할 수 있음)에 대 한 원격 디버깅 포함 됩니다.  
  
 Visual Studio를 실행 하는 동안 프로세스 디버그 관리자 (PDM) 로컬 컴퓨터에서 디버그 프로세스를 추적 합니다. 원격으로 msvsmon.exe 이라는 프로그램 원격 디버깅을 처리 하 고는 PDM를 사용할 수 있도록 하는 개발자가 시작 됩니다. (해당 msvsmon.exe는 서비스가 해당 컴퓨터에서 원격 디버깅을 사용 하려면 수동으로 시작 해야 note). Visual Studio (또는 msvsmon.exe)를 실행 하지 않는 프로세스 없음 디버깅에 대 한 추적 됩니다.  
  
 즉, 개발자가 특별 한 권한이 없어도 시작 프로그램을 디버깅할 수 있습니다. 개발자는 다른 사용자가 동일한 보안 그룹의 멤버인 경우 다른 사용자에 의해 시작 된 프로세스를 디버깅할도 수 있습니다. 원격 디버깅을 사용 하려면 반드시 필요한 복사할 파일을 원격 컴퓨터 및 msvsmon.exe를 시작 하 고 (참조 [원격 디버깅](../../debugger/remote-debugging.md) 자세한 세부 정보에 대 한).  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)   
 [디버그 프로세스 관리자](../../extensibility/debugger/process-debug-manager.md)   
 [원격 디버깅](../../debugger/remote-debugging.md)