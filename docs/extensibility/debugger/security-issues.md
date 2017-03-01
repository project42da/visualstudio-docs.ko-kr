---
title: "보안 문제 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 98a4c85118fc836e1f8922a24700036c9d4837cb
ms.openlocfilehash: fcc65d94f8348674110db6cc0a87e0e3020a4683
ms.lasthandoff: 02/22/2017

---
# <a name="security-issues"></a>보안 문제
Visual Studio를 사용 하는 프로그램을 디버깅 하려면 권한만 필요한 프로그램을 실행 하는 개발자가 알아야 하는 것과 같은 됩니다. 대부분의 경우 (일부 상황에서 인터넷 정보 서비스 등의 다른 서비스는 더 높은 수준의 권한 요구할 수 있음)에 대 한 원격 디버깅 포함 됩니다.  
  
 Visual Studio를 실행 하는 동안 프로세스 디버그 관리자 (PDM) 로컬 컴퓨터에서 디버그 프로세스를 추적 합니다. 원격으로 msvsmon.exe를 호출 하는 프로그램 개발자가 원격 디버깅을 처리 하 고는 PDM를 사용할 수 있도록 하기 위해 시작 됩니다. (해당 msvsmon.exe는 서비스가 해당 컴퓨터에서 원격 디버깅을 사용 하도록 수동으로 시작 해야 note). Visual Studio (또는 msvsmon.exe)를 실행 하지 않는 경우 프로세스가 디버깅을 위해 추적 됩니다.  
  
 즉, 개발자가 자신이 특별 한 권한이 없어도 시작 프로그램을 디버깅할 수 있습니다. 개발자는 다른 사용자가 동일한 보안 그룹의 멤버인 경우 다른 사용자에 의해 시작 된 프로세스를 디버깅할 수도 수 있습니다. 원격 디버깅을 사용 하려면이 필요한 필요한 복사 하는 원격 컴퓨터 파일과 msvsmon.exe를 시작 하 고 (참조 [원격 디버깅](../../debugger/remote-debugging.md) 대 한 자세한 내용은).  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)   
 [디버그 프로세스 관리자](../../extensibility/debugger/process-debug-manager.md)   
 [원격 디버깅](../../debugger/remote-debugging.md)
