---
title: "IA64 프로세스에 대해서는 혼합 모드 디버깅을 수행할 수 없습니다. | Microsoft Docs"
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
  - "vs.debug.error.interop_unsupported_ia64"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 20bc1e38-049b-4388-87c4-936815d85b46
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IA64 프로세스에 대해서는 혼합 모드 디버깅을 수행할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에서는 IA64 프로세스에서 관리 코드와 네이티브 코드의 혼합 모드 디버깅을 지원하지 않습니다.  따라서 디버깅하는 동안 네이티브 코드에서 관리 코드로 또는 그 반대로 실행할 수 없습니다.  
  
### 해결 방법  
  
-   관리 및 네이티브 코드를 별도의 디버깅 세션에서 디버깅합니다.  
  
     \-또는\-  
  
     다음 절차에 설명된 대로 혼합 코드를 32비트 프로세스로 디버깅합니다.  
  
### 플랫폼을 32비트로 변경하려면\(Visual Basic 또는 C\#\)  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **속성**을 클릭합니다.  
  
2.  속성 페이지에서 **컴파일** 또는 **디버그** 탭을 클릭합니다.  
  
3.  **플랫폼**을 클릭하고 플랫폼 목록에서 x86을 선택합니다.  
  
     기본적으로 Visual Basic 및 C\# 컴파일러에서는 모든 CPU에서 실행할 수 있는 코드를 생성합니다.  이러한 이진 코드는 64비트 컴퓨터에서 64비트 프로세스로 실행됩니다.  32비트 프로세스에서 실행하려면 **AnyCPU** 대신 **Win32**를 선택해야 합니다.  
  
### 플랫폼을 32비트로 변경하려면\(C\/C\+\+\)  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **속성**을 클릭합니다.  
  
2.  속성 페이지에서 **플랫폼**을 클릭하고 플랫폼 목록에서 Win32를 선택합니다.  
  
## 참고 항목  
 [64비트 응용 프로그램 디버그](../debugger/debug-64-bit-applications.md)