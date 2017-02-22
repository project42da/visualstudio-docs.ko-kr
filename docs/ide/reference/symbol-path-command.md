---
title: "기호 경로 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.symbolpath"
helpviewer_keywords: 
  - "Debug.SymbolPath 명령"
  - "기호 경로 명령"
  - "SymbolPath 명령"
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 기호 경로 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거에서 기호를 검색할 디렉터리 목록을 설정합니다.  
  
## 구문  
  
```  
Debug.SymbolPath pathname1;pathname2;... pathnameN  
```  
  
## 인수  
 `pathname`  
 선택 사항입니다.  디버거에서 기호를 검색할 경로를 세미콜론으로 구분한 목록입니다.  
  
## 설명  
 `pathname`을 지정하지 않으면 명령에서 현재 기호 경로를 나열합니다.  
  
## 예제  
 다음 예제에서는 기호 디렉터리 목록에 두 개의 경로를 추가합니다.  
  
```  
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2  
```  
  
## 예제  
 다음 예제에서는 현재 기호 경로를 세미콜론으로 구분한 목록을 표시합니다.  
  
```  
Debug.SymbolPath  
```  
  
## 참고 항목  
 [명령 창](../../ide/reference/command-window.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)