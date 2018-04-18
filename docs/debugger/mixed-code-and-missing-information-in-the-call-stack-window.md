---
title: 혼합 코드 및 호출 스택 창에 누락 된 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 580fc3b87173a120480f708e8b349fbb6942bbdb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>호출 스택 창의 혼합 코드 및 누락된 정보
관리 코드에 대한 호출 스택과 네이티브 코드에 대한 호출 스택은 서로 다르기 때문에 코드 형식이 혼합된 경우 디버거에서 전제 호출 스택이 표시되지 않을 수 있습니다. 네이티브 코드가 관리 코드를 호출 하는 경우 다음과 같이 변경 변경 될 수 있습니다는 **호출 스택** 창:  
  
-   관리 되는 코드 바로 위의 네이티브 프레임이 없을 수 있습니다는 **호출 스택** 창. 자세한 내용은 참조 [하는 방법: 네이티브 프레임이 호출 스택 창에서 없을 때 관리 코드를 나가기](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)합니다.  
  
-   디버거, 외부에서 실행 하는 혼합 모드 응용 프로그램에 대 한는 **호출 스택** 창에는 관리 코드에만 표시 될 수 있으며 네이티브 프레임은 표시 되지 것입니다.  
  
 두 경우 모두 아주 드문 경우입니다. 관리 코드에 대한 대부분의 네이티브 호출에서는 호출 스택이 올바르게 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 호출 스택 창 사용](../debugger/how-to-use-the-call-stack-window.md)