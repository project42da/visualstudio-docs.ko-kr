---
title: "EndTrackingContext | Microsoft Docs"
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
  - "EndTrackingContext"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "EndTrackingContext"
ms.assetid: c2c5d794-8dc8-4594-8717-70dc79a0e75d
caps.latest.revision: 3
caps.handback.revision: 3
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# EndTrackingContext
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

현재 추적 컨텍스트를 끝냅니다.  
  
## 구문  
  
```  
HRESULT WINAPI EndTrackingContext();  
```  
  
## 반환 값  
 추적 컨텍스트가 종료된 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True)입니다.  
  
## 요구 사항  
 **헤더:** FileTracker.h  
  
## 참고 항목  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)