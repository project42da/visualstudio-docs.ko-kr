---
title: "예외 후 실행 계속 | Microsoft Docs"
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
  - "디버거, 예외"
  - "예외 처리, 계속 실행"
  - "예외 대화 상자"
  - "예외, 계속 실행"
  - "실행, 예외 후에 계속하기"
  - "관리 코드, 예외 처리"
  - "관리되는 예외, 계속 실행"
  - "프로그램 실행"
  - "프로그램, 실행"
  - "스레딩[Visual Studio], 예외 후 실행 계속"
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 예외 후 실행 계속
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

예외로 인해 디버거에서 실행이 중단되면 대화 상자가 나타납니다.  Visual Basic 또는 C\#의 경우 기본적으로 [Exception Assistant](../Topic/Exception%20Assistant.md) 대화 상자가 열립니다.  C\+\+의 경우 이전의 **예외** 대화 상자가 표시됩니다.  Visual Basic 또는 C\#을 사용하면서 **옵션** 대화 상자에서 **예외 도우미**를 비활성화한 경우에는 **예외** 대화 상자가 표시됩니다.  
  
 **예외 도우미** 또는 **예외** 대화 상자가 나타나면 예외의 원인이 되는 문제를 해결할 수 있습니다.  
  
## 관리 코드  
 관리 코드에서는 처리되지 않은 예외가 발생한 후 같은 스레드에서 실행을 계속할 수 있습니다.  **예외 도우미**는 호출 스택을 해제하여 예외가 throw된 지점으로 되돌립니다.  
  
## 네이티브 코드  
 네이티브 C\/C\+\+에서는 두 가지 옵션이 있습니다.  
  
-   **중단**을 클릭하고 문제 해결을 시도할 수 있습니다.  중단 모드에서 작업하는 동안 **호출 스택** 창의 프레임을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **이 프레임으로 해제**를 선택하여 호출 스택을 해제할 수 있습니다.  문제가 해결되지 않은 상태에서 디버깅을 계속하면 **예외** 대화 상자가 다시 나타납니다.  문제가 해결된 경우에는 **예외** 대화 상자가 나타나지 않습니다.  
  
-   **계속**을 클릭하여 문제를 해결하지 않고 실행을 계속할 수 있습니다.  **예외** 대화 상자가 다시 나타납니다.  
  
## 혼합 코드  
 네이티브 및 관리 코드가 혼합된 코드를 디버깅하는 동안 처리되지 않은 예외가 발생하면 운영 체제 제한에 따라 호출 스택을 해제할 수 없습니다.  바로 가기 메뉴를 사용하여 호출 스택을 해제하려고 하면 혼합 코드 디버깅 중에 처리되지 않은 예외가 발생하면 디버거가 호출 스택을 해제할 수 없다는 내용의 오류 메시지가 나타납니다.  
  
## 참고 항목  
 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)