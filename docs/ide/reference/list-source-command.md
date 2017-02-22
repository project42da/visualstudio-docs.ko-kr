---
title: "소스 목록 표시 명령 | Microsoft Docs"
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
  - "Debug.ListSource"
helpviewer_keywords: 
  - "Debug.ListSource 명령"
  - "소스 열거 명령"
  - "ListSource 명령"
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 소스 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 소스 코드 줄을 표시합니다.  
  
## 구문  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## 스위치  
 \/Count:`number`  
 선택적 요소.  표시할 줄 수를 지정합니다.  
  
 \/Current  
 선택적 요소.  현재 줄을 표시합니다.  
  
 \/File:`filename`  
 선택적 요소.  표시할 파일의 경로입니다.  파일 이름을 지정하지 않으면 현재 문의 줄에 대한 소스 코드가 표시됩니다.  
  
 \/Line:`number`  
 선택적 요소.  특정 줄 번호를 표시합니다.  
  
 \/ShowLineNumbers:`yes|no`  
 선택적 요소.  줄 번호를 표시할지 여부를 지정합니다.  
  
## 설명  
  
## 예제  
 다음 예제에서는 Form1.vb 파일의 줄 4부터 줄 번호를 표시하여 소스 코드를 나열합니다.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)