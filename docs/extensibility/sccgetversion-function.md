---
title: "SccGetVersion 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGetVersion"
helpviewer_keywords: 
  - "SccGetVersion 함수"
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# SccGetVersion 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 플러그 인에서 지원 되는 소스 제어 플러그 인 API의 버전 번호를 가져옵니다.  
  
## 구문  
  
```cpp#  
LONG SccGetVersion(void);  
```  
  
#### 매개 변수  
 없음  
  
## 반환 값  
 A `LONG` 지원 되는 소스 제어 플러그 인 API의 버전 번호를 포함 하는 데이터 형식:  
  
|WORD|설명|  
|----------|--------|  
|HIWORD|주 버전|  
|LOWORD|부 버전|  
  
## 설명  
 예를 들어 소스 제어 플러그 인 버전 1.3의 소스 제어 플러그 인 API를 지 원하는 경우이 함수 0x0103를 반환 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)