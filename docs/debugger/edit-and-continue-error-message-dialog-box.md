---
title: "편집하며 계속하기 오류 메시지 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.ENC.SupportedButNotAvaiable"
  - "vs.debug.ENC.CannotEditWhileException"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "편집하며 계속하기 오류 메시지 대화 상자"
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 편집하며 계속하기 오류 메시지 대화 상자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 대화 상자는 편집하며 계속하기를 지원하는 언어에서 디버깅하고 있는 경우 **편집하며 계속하기**를 적용할 수 없는 유형의 코드 변경 작업을 했을 때 표시됩니다.  대화 상자 안의 오류 메시지에서 보다 자세한 설명을 제공합니다.  이 대화 상자가 표시될 수 있는 원인은 다음과 같습니다.  
  
-   관리되지 않는 디버깅을 사용하도록 설정된 상태에서 관리 코드를 편집하려고 한 경우.  편집하며 계속하기는 혼합 모드 디버깅에서 작동하지 않습니다.  
  
-   SQL Server 코드를 편집하려고 한 경우  
  
-   Dr. Watson 덤프를 디버깅하는 동안 코드를 편집하려고 한  경우  
  
-   "**처리되지 않은 예외에 대한 호출 스택 해제**" 옵션이 선택되지 않은 상태에서 처리되지 않은 예외가 발생한 후 코드를 편집하려고 한 경우  
  
-   포함된 런타임 응용 프로그램을 디버깅하는 동안 코드를 편집하려고 한 경우  
  
-   **디버그** 메뉴에서 시작하지 않고 연결되어 있는 프로그램에서 코드를 편집하려고 한 경우  
  
-   최적화된 코드를 편집하려고 한 경우  
  
-   대상이 64비트 응용 프로그램일 때 관리 코드를 편집하려고 한 경우.  편집하며 계속하기를 사용하려면 대상을 x86으로 설정해야 합니다. \(**고급 컴파일러** 설정, **컴파일** 탭, *Project* **속성**\)  
  
-   디버깅하는 동안 수정하여 다시 로드한 어셈블리의 코드를 편집하려고 한 경우  
  
-   로드하지 않은 어셈블리의 코드를 편집하려고 한 경우  
  
-   새 버전에 빌드 오류가 있으므로 이전 버전의 응용 프로그램을 디버깅하기 시작한 경우  
  
-   실행되고 있는 코드를 편집하려고 한 경우  
  
## UI 요소 목록  
 **OK**  
 대화 상자를 종료하고 바로 전에 시도한 편집을 취소합니다.  
  
## 참고 항목  
 [지원되는 코드 변경 및 제한\(C\+\+\)](../debugger/supported-code-changes-cpp.md)