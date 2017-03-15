---
title: "SccQueryChanges 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccQueryChanges"
helpviewer_keywords: 
  - "SccQueryChanges 함수"
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# SccQueryChanges 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 지정 된 콜백 함수를 통해 각 파일에 대 한 이름 변경에 대 한 정보를 제공 하는 파일 목록을 열거 합니다.  
  
## 구문  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nFiles  
 \[in\] 파일 수가 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 \[in\] 에 대 한 정보를 얻을 수 있는 파일 이름 배열입니다.  
  
 pfnCallback  
 \[in\] 콜백 함수를 목록에서 각 파일 이름에 대 한 호출 \(참조 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) 대 한 자세한 내용은\).  
  
 pvCallerData  
 \[in\] 콜백 함수에 전달 되는 값을 변경 되지 않습니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|쿼리 프로세스를 성공적으로 완료 합니다.|  
|SCC\_E\_PROJNOTOPEN|프로젝트 소스 제어에서 열리지 않았습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다.|  
|SCC\_E\_NONSPECIFICERROR|지정 되지 않은 또는 일반 오류가 발생 했습니다.|  
  
## 설명  
 네임 스페이스는 변경에 대 한 쿼리 중인: 특히, 이름 바꾸기, 추가 및 파일을 제거 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [오류 코드](../extensibility/error-codes.md)