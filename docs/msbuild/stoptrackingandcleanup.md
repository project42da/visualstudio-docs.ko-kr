---
title: "StopTrackingAndCleanup | Microsoft Docs"
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
  - "StopTrackingAndCleanup"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "StopTrackingAndCleanup"
ms.assetid: 9f8c5994-2dfc-43c3-a5fb-89b2f8990429
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# StopTrackingAndCleanup
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모든 추적을 중지하고 추적 세션에서 사용되는 메모리를 해제합니다.  
  
## 구문  
  
```  
HRESULT WINAPI StopTrackingAndCleanup(void);  
```  
  
## 반환 값  
 추적이 중지된 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 상태에서 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True)를 반환합니다.  
  
## 요구 사항  
 **헤더:** FileTracker.h  
  
## 참고 항목  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)