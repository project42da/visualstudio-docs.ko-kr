---
title: "SuspendTracking | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "SuspendTracking"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "SuspendTracking"
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
caps.latest.revision: 3
caps.handback.revision: 3
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# SuspendTracking
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

현재 컨텍스트에서 추적을 일시 중단합니다.  
  
## 구문  
  
```  
HRESULT WINAPI SuspendTracking(void);  
```  
  
## 반환 값  
 추적이 중단된 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True)입니다.  
  
## 요구 사항  
 **헤더:** FileTracker.h  
  
## 참고 항목  
 [ResumeTracking](../msbuild/resumetracking.md)