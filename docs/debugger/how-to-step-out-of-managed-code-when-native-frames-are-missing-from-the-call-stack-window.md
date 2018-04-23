---
title: '방법: 네이티브 프레임이 호출 스택 창에서 없을 때 관리 코드를 나가기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e21d45cd65fc6bc6a66f2f7c698952f0cdd788b9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>방법: 호출 스택 창에 네이티브 프레임이 없을 때 관리 코드에서 나가기
코드에 네이티브 프레임에 표시 되는 경우는 **호출 스택** 창, 관리 코드에서 나가면 예기치 않은 결과가 발생할 수 있습니다. 이 문제를 해결 대신 중단점을 사용 하면 **나가기**합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>네이티브 프레임이 호출 스택 화면에서 없어질 때 관리 코드에 대해 프로시저 나가기를 수행하려면  
  
1.  네이티브 코드에서 호출 후의 위치 중단점을 관리 코드로 설정합니다.  
  
2.  에 **디버그** 메뉴 선택 **계속**합니다.  
  
     관리되는 호출이 완료되면 네이티브 코드의 중단점에서 실행이 중지됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 호출 스택 창 사용](../debugger/how-to-use-the-call-stack-window.md)