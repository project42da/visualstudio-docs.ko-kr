---
title: "연습: 디자인 타임에 디버깅 | Microsoft Docs"
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
- JScript
helpviewer_keywords:
- debugging [Visual Studio], design-time
- breakpoints, design-time debugging
- Immediate window, design-time debugging
- design-time debugging
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d497535f8511c3f9e6c55e80157507ed36184b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-debugging-at-design-time"></a>연습: 디자인 타임에 디버깅
Visual Studio를 사용 하 여 **직접 실행** 응용 프로그램은 실행 되지 않을 때 함수 또는 서브루틴을 실행 하는 창입니다. 함수 또는 서브루틴에 중단점을이 있으면 Visual Studio는 해당 시점에서 실행을 중단 합니다. 그런 다음 프로그램 상태를 검사 하는 디버거 창에 사용할 수 있습니다. 이 기능을 디자인 타임에 디버깅 라고 합니다.  
  
 다음 절차에서는이 기능을 사용 하는 방법을 보여 줍니다.  
  
### <a name="to-hit-breakpoints-from-the-immediate-window"></a>직접 실행 창에서 중단점을 적중 횟수  
  
1.  Visual Basic 콘솔 응용 프로그램에 다음 코드를 붙여 넣습니다.  
  
    ```  
    Module Module1  
  
        Sub Main()  
            MySub()  
        End Sub  
  
        Function MyFunction() As Decimal  
            Static i As Integer  
            i = i + 1  
            Dim s As String  
  
            s = "Add Breakpoint here"  
            Return 4  
        End Function  
  
        Sub MySub()  
            MyFunction()  
        End Sub  
    End Module  
    ```  
  
2.  읽기, 줄에 중단점을 설정 `s="Add BreakPoint Here"`합니다.  
  
3.  다음을 입력 하 고 **직접 실행** 창:`?MyFunction<enter>`  
  
4.  중단점이 적중 된 호출 스택의 정확한 지 확인 합니다.  
  
5.  에 **디버그** 메뉴를 클릭 **계속**, 디자인 모드에 있는지 확인 합니다.  
  
6.  다음을 입력 하 고 **직접 실행** 창:`?MyFunction<enter>`  
  
7.  다음을 입력 하 고 **직접 실행** 창:`?MySub<enter>`  
  
8.  중단점에 도달 하 고 정적 변수의 값을 검사 확인 `i` 에 **지역** 창. 값 3 필요 합니다.  
  
9. 호출 스택의 정확한 지 확인 합니다.  
  
10. 에 **디버그** 메뉴를 클릭 **계속**, 디자인 모드에 있는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [디버거 기본 사항](../debugger/debugger-basics.md)