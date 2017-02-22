---
title: "SetThreadCount | Microsoft Docs"
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
  - "SetThreadCount"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "SetThreadCount"
ms.assetid: 335335a5-8ca0-4e18-95f5-62aa6a691386
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# SetThreadCount
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

전역 스레드 수를 설정하고 해당 수를 현재 스레드에 할당합니다.  
  
## 구문  
  
```  
HRESULT WINAPI SetThreadCount(int threadCount);  
```  
  
#### 매개 변수  
 \[in\] `threadCount`  
 사용할 스레드 수입니다.  
  
## 반환 값  
 스레드 수가 업데이트된 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True)입니다.  
  
## 요구 사항  
 **헤더:** FileTracker.h