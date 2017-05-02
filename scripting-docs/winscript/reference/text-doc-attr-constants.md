---
title: "TEXT_DOC_ATTR 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: TEXT_DOC_ATTR
apilocation: scrobj.dll
helpviewer_keywords: 
  - "TEXT_DOC_ATTR 상수"
ms.assetid: fd9c53a4-8f73-4c6a-abe5-6b831ecd5b1e
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# TEXT_DOC_ATTR 상수
문서의 특성을 설명 합니다.  
  
## 구문  
  
```  
typedef DWORD TEXT_DOC_ATTR;  
```  
  
## 상수  
  
|상수|값|설명|  
|--------|-------|--------|  
|TEXT\_DOC\_ATTR\_READONLY|0x00000001|문서가 읽기 전용입니다.|  
|TEXT\_DOC\_ATTR\_TYPE\_PRIMARY|0x00000002|문서가 문서 트리의 기본 파일입니다.|  
|TEXT\_DOC\_ATTR\_TYPE\_WORKER|0x00000004|문서 작업자입니다.|  
|TEXT\_DOC\_ATTR\_TYPE\_SCRIPT|0x00000008|문서에 있는 스크립트 파일입니다.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)