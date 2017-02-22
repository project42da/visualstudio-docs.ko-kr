---
title: "네이티브 코드의 스레드 디버깅 팁 | Microsoft Docs"
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
helpviewer_keywords: 
  - "디버깅[Visual Studio], 스레드"
  - "스레딩[Visual Studio], 디버깅"
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 네이티브 코드의 스레드 디버깅 팁
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음은 네이티브 코드에서 스레드를 디버깅할 때 사용할 수 있는 몇 가지 팁입니다.  
  
-   **조사식** 창이나 **간략한 조사식** 대화 상자에 `@TIB`를 입력하면 스레드 정보 블록의 내용이 표시됩니다.  
  
-   **조사식** 창이나 **간략한 조사식** 대화 상자에 `@Err`을 입력하면 현재 스레드의 마지막 오류 코드가 표시됩니다.  
  
-   CRT\(C Run\-Time Libraries\) 함수는 다중 스레드 응용 프로그램을 디버깅하는 데 유용합니다.  자세한 내용은 [\_malloc\_dbg](/visual-cpp/c-runtime-library/reference/malloc-dbg)를 참조하십시오.  
  
## 참고 항목  
 [다중 스레드 응용 프로그램 디버깅](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)