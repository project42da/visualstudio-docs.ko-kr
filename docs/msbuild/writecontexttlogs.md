---
title: "WriteContextTLogs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "WriteContextTLogs"
apilocation: 
  - "filetracker.dll"
apitype: "COM"
helpviewer_keywords: 
  - "WriteContextTLogs"
ms.assetid: ffc6c7be-3f22-4624-9ffc-0122fe72b6ec
caps.latest.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 5
---
# WriteContextTLogs
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

현재 컨텍스트에 대한 로그 파일을 작성합니다.  
  
## 구문  
  
```  
HRESULT WINAPI WriteContextTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
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
 [WriteAllTLogs](../msbuild/writealltlogs.md)