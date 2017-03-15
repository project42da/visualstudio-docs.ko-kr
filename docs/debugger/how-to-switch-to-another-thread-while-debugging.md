---
title: "방법: 디버깅 중 다른 스레드로 전환 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "스레드, 전환[디버깅]"
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: 26
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 26
---
# 방법: 디버깅 중 다른 스레드로 전환
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다중 스레드 응용 프로그램을 디버깅하는 경우 작업 중인 스레드에서 다른 스레드로 컨텍스트를 전환하는 여러 가지 방법 중 하나를 사용할 수 있습니다.  
  
### 스레드 창에 나타나는 스레드로 전환하려면  
  
-   스레드를 두 번 클릭합니다.  
  
### 소스 창에서 스레드를 전환하려면  
  
-   왼쪽 제본용 여백에서 스레드 표시기를 마우스 단추로 클릭하고 **전환**을 가리킨 다음 전환할 스레드의 이름을 클릭합니다.  특정 위치의 스레드만 바로 가기 메뉴에 표시됩니다.  
  
     표시기가 나타나지 않으면 **스레드** 창을 마우스 오른쪽 단추로 클릭하여 **소스의 스레드 표시**가 선택되어 있는지 확인합니다.  
  
### 디버그 위치 도구 모음에서 스레드로 전환하려면  
  
1.  **디버그 위치** 도구 모음에서 **스레드** 상자를 클릭합니다.  
  
2.  목록에서 전환할 스레드를 클릭합니다.  
  
## 참고 항목  
 [다중 스레드 응용 프로그램 디버깅](../debugger/debug-multithreaded-applications-in-visual-studio.md)