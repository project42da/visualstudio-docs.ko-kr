---
title: "웹 브라우저 표시 명령 | Microsoft Docs"
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
  - "view.showwebbrowser"
helpviewer_keywords: 
  - "ShowWebBrowser 명령"
  - "View.ShowWebBrowser 명령"
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 웹 브라우저 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

IDE\(통합 개발 환경\) 내부 또는 외부에 있는 웹 브라우저 창에 지정된 URL을 표시합니다.  
  
## 구문  
  
```  
View.ShowWebBrowser URL [/new][/ext]  
```  
  
## 인수  
 `URL`  
 필수 요소.  웹 사이트에 대한 URL\(Uniform Resource Locator\)입니다.  
  
## 스위치  
 \/new 또는 \/새브라우저창열기  
 선택적 요소.  해당 페이지가 새 웹 브라우저의 인스턴스에 표시되도록 지정합니다.  
  
 \/ext 또는 \/외부기본브라우저에서열기  
 선택적 요소.  통합 개발 환경\(IDE\) 외부의 기본 웹 브라우저에 페이지가 표시되도록 지정합니다.  
  
## 설명  
 **ShowWebBrowser** 명령의 별칭은 **navigate** 또는 **nav**입니다.  
  
## 예제  
 다음 예제에서는 개발 환경 외부에 있는 웹 브라우저에 MSDN Online 홈 페이지를 표시합니다.  웹 브라우저의 인스턴스가 이미 열려 있으면 사용 중임을 의미하며, 닫혀 있으면 새 인스턴스가 시작됩니다.  
  
```  
>View.ShowWebBrowser http://msdn.microsoft.com /ext  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)