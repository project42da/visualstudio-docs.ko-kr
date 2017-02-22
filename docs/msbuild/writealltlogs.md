---
title: "WriteAllTLogs | Microsoft Docs"
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
  - "WriteAllTLogs"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "WriteAllTLogs"
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# WriteAllTLogs
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모든 스레드 및 컨텍스트에 대한 추적 로그를 씁니다.  
  
## 구문  
  
```  
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### 매개 변수  
 \[in\] `intermediateDirectory`  
 추적 로그를 저장할 디렉터리입니다.  
  
 \[in\] `tlogRootName`  
 로그 파일 이름의 루트 이름입니다.  
  
## 반환 값  
 추적 컨텍스트가 만들어진 경우 [SUCCEEDED](assetId:///SUCCEEDED?qualifyHint=False&autoUpgrade=True) 비트가 설정된 [HRESULT](assetId:///HRESULT?qualifyHint=False&autoUpgrade=True).  
  
## 요구 사항  
 **헤더:** FileTracker.h  
  
## 참고 항목  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)