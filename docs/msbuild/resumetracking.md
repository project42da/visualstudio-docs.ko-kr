---
title: "ResumeTracking | Microsoft Docs"
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
  - "ResumeTracking"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "ResumeTracking"
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# ResumeTracking
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

현재 컨텍스트에서 추적을 다시 시작합니다.  
  
## 구문  
  
```  
HRESULT WINAPI ResumeTracking();  
```  
  
## 반환 값  
 추적이 다시 시작된 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True)입니다.  [E\_FAIL](assetId:///E_FAIL?qualifyHint=False&autoUpgrade=True)는 컨텍스트를 사용할 수 없기 때문에 추적을 다시 시작할 수 없는 경우에 반환됩니다.  
  
## 요구 사항  
 **헤더:** FileTracker.h  
  
## 참고 항목  
 [SuspendTracking](../msbuild/suspendtracking.md)