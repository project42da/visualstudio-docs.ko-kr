---
title: "StartTrackingContext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "StartTrackingContext"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "StartTrackingContext"
ms.assetid: 720cd295-38e7-4974-86db-b8106b1207ba
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# StartTrackingContext
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

추적 컨텍스트를 시작합니다.  
  
## 구문  
  
```  
HRESULT WINAPI StartTrackingContext(LPCTSTR intermediateDirectory, LPCTSTR taskName);  
```  
  
#### 매개 변수  
 \[in\] `intermediateDirectory`  
 추적 로그를 저장할 디렉터리입니다.  
  
 \[in\] `taskName`  
 추적 컨텍스트를 식별합니다.  이 이름은 로그 파일 이름을 만드는 데 사용됩니다.  
  
## 반환 값  
 추적 컨텍스트가 만들어진 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True).  
  
## 요구 사항  
 **헤더:** FileTracker.h