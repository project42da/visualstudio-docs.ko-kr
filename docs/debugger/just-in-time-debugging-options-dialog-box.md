---
title: Just-in-time, 디버깅, 옵션 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Debugger.JIT
- vs.debug.options.JIT
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Just-In-Time debugging, setting options
- Options dialog box, debugging
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7be7dacbe7b3b89b8bdc09515c23d7597e7e55e5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="just-in-time-debugging-options-dialog-box"></a>옵션 대화 상자, 디버깅, Just-In-Time
에 액세스 하려면는 **Just In Time** 페이지에는 **도구** 메뉴 **옵션**합니다. 에 **옵션** 대화 상자에서 **디버깅** 노드 선택한 **Just In Time**합니다. 이 페이지에서는 관리 코드, 네이티브 코드 및 스크립트에 대해 Just-In-Time 디버깅을 사용하도록 설정할 수 있습니다. 자세한 내용은 참조 [Just-In-Time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md)합니다.  
  
 다음과 같은 프로그램 유형에 대해 Just-In-Time 디버깅을 사용하도록 설정할 수 있습니다.  
  
-   관리  
  
-   네이티브  
  
-   스크립트  
  
 Just-In-Time 디버깅은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 외부에서 시작된 프로그램을 디버깅하는 기술입니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경 외부에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 만든 프로그램을 실행할 수 있습니다. Just-in-time 디버깅을 사용하도록 설정한 상태에서 프로그램이 충돌하면 디버깅할지 여부를 묻는 대화 상자가 표시됩니다.  
  
## <a name="associated-warnings"></a>관련된 경고  
 이 페이지를 방문 하는 경우는 **옵션** 대화 상자에서 다음과 같은 경고 메시지가 표시 될 수 있습니다.  
  
 **다른 디버거가으로 시간에만 등록 되어 디버거 합니다. 를 복구 하려면 Just In Time 디버깅 하거나 Visual Studio 복구를 실행을 사용 하도록 설정 합니다.**  
  
 이 메시지는 다른 디버거(예: 이전 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거)가 Just-In-Time 디버거로 설정되어 있는 경우에 발생합니다.  
  
 다음과 같은 다른 메시지가 표시될 수도 있습니다.  
  
 **Just-in-time 디버깅 등록 오류가 발견 되었습니다. 를 복구 하려면 Just In Time 디버깅 하거나 Visual Studio 복구를 실행을 사용 하도록 설정 합니다.**  
  
 표시 되 면 이러한 경고가 Just In Time 사용 하 여 디버깅 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 문제를 해결할 때까지 관리자 권한이 필요 합니다. 이러한 상황에서 관리자 이외의 권한으로 Just-In-Time 디버깅을 사용하도록 설정하려고 하면 다음과 같은 오류 메시지가 표시됩니다.  
  
 **액세스가 거부 되었습니다. 관리자가 사용 Just In Time 디버깅, 없거나 Visual Studio의 설치를 복구 합니다.**  
  
## <a name="see-also"></a>참고 항목  
 [옵션 대화 상자, 디버깅](../debugger/debugging-options-dialog-box.md)   
 [방법: 디버거 설정 지정](../debugger/how-to-specify-debugger-settings.md)