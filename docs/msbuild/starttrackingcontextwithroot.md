---
title: "StartTrackingContextWithRoot | Microsoft Docs"
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
  - "StartTrackingContextWithRoot"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "StartTrackingContextWithRoot"
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# StartTrackingContextWithRoot
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

루트 표식을 지정하는 응답 파일을 사용하여 추적 컨텍스트를 시작합니다.  
  
## 구문  
  
```  
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### 매개 변수  
 \[in\] `intermediateDirectory`  
 추적 로그를 저장할 디렉터리입니다.  
  
 \[in\] `taskName`  
 추적 컨텍스트를 식별합니다.  이 이름은 로그 파일 이름을 만드는 데 사용됩니다.  
  
 \[in\] `rootMarkerResponseFile`  
 루트 표식을 포함하는 응답 파일의 경로명입니다.  루트 이름은 컨텍스트에 대한 모든 추적을 그룹화하는 데 사용됩니다.  
  
## 반환 값  
 추적 컨텍스트가 만들어진 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True).  
  
## 요구 사항  
 **헤더:** FileTracker.h  
  
## 참고 항목  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)