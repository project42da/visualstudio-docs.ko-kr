---
title: "연습: 디자인 타임에 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "중단점, 디자인 타임 디버깅"
  - "디버깅[Visual Studio], 디자인 타임"
  - "디자인 타임 디버깅"
  - "직접 실행 창, 디자인 타임 디버깅"
ms.assetid: 35bfdd2c-6f60-4be1-ba9d-55fce70ee4d8
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 연습: 디자인 타임에 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio **직접 실행** 창을 사용하면 응용 프로그램이 실행되지 않는 상태에서도 함수나 서브루틴을 실행할 수 있습니다.  함수나 서브루틴에 중단점이 포함되어 있으면 Visual Studio는 적절한 지점에서 실행을 중단합니다.  그런 다음 디버거 창을 사용하여 프로그램 상태를 검사할 수 있습니다.  이 기능을 디자인 타임 디버깅이라고 합니다.  
  
 다음 절차에서는 이 기능을 사용하는 방법을 보여 줍니다.  
  
### 직접 실행 창에서 중단점에 도달하려면  
  
1.  Visual Basic 콘솔 응용 프로그램에 다음 코드를 붙여넣습니다.  
  
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
  
2.  `s="Add BreakPoint Here"`라는 줄에 중단점을 설정합니다.  
  
3.  **직접 실행** 창에 `?MyFunction<enter>`을 입력합니다.  
  
4.  중단점에 도달했는지 확인하고 호출 스택이 정확한지 확인합니다.  
  
5.  **디버그** 메뉴에서 **계속**을 클릭하고 현재 모드가 아직 디자인 모드인지 확인합니다.  
  
6.  **직접 실행** 창에 `?MyFunction<enter>`을 입력합니다.  
  
7.  **직접 실행** 창에 `?MySub<enter>`를 입력합니다.  
  
8.  중단점에 도달했는지 확인하고 **지역** 창에서 정적 변수 `i`의 값을 검사합니다.  이 값은 3이어야 합니다.  
  
9. 호출 스택이 정확한지 확인합니다.  
  
10. **디버그** 메뉴에서 **계속**을 클릭하고 현재 모드가 아직 디자인 모드인지 확인합니다.  
  
## 참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [디버거 기본 사항](../debugger/debugger-basics.md)