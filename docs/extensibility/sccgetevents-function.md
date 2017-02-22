---
title: "SccGetEvents 함수 | Microsoft Docs"
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
  - "SccGetEvents"
helpviewer_keywords: 
  - "SccGetEvents 함수"
ms.assetid: 32f8147d-6dcc-465e-b07b-42da5824f9b0
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# SccGetEvents 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 큐에 대기 중인된 상태 이벤트를 가져옵니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccGetEvents (  
   LPVOID pvContext,  
   LPSTR  lpFileName,  
   LPLONG lpStatus,  
   LPLONG pnEventsRemaining  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 lpFileName  
 \[에서, out\] 소스 제어 플러그 인에서 반환된 된 파일 이름 \(최대 \_MAX\_PATH 자\)를 배치 하는 위치를 버퍼링 합니다.  
  
 lpStatus  
 \[에서, out\] 상태 코드 반환 \(참조 [파일 상태 코드](../extensibility/file-status-code-enumerator.md) 가능한 값에 대 한\).  
  
 pnEventsRemaining  
 \[에서, out\] 이 호출 후에 큐에 남아 있는 항목 수를 반환 합니다. 호출자를 호출 하도록 결정할 수 있습니다이 수가 큰 경우는 [SccQueryInfo](../extensibility/sccqueryinfo-function.md) 모든 정보를 한 번에 얻을 수 있습니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|성공 이벤트를 가져옵니다.|  
|SCC\_E\_OPNOTSUPPORTED|이 함수는 지원 되지 않습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 이 함수를 소스 제어에서 파일에 대 한 상태 업데이트 되었는지를 보려면 유휴 처리 하는 동안 호출 됩니다. 소스 제어 플러그 인을 알고 있는 모든 파일의 상태를 유지 관리 하 고 변경 될 때마다 상태를 기록 플러그 인, 상태 및 관련된 파일 큐에 저장 됩니다. 때 `SccGetEvents` 호출 되는 상위 큐의 요소로 검색 되 고 반환 합니다. 이 유일한 이전에 캐시 된 정보를 반환 하는 제한 된 함수와 매우 신속 하 게 처리할 \(즉, 없음 디스크의 읽기 또는 상태에 대 한 소스 제어 시스템에 대 한 요청\) 있어야 합니다. 그렇지 않으면 IDE의 성능 저하를 시작할 수 있습니다.  
  
 소스 제어 플러그 인은가 가리키는 버퍼에 빈 문자열을 저장 하는 보고서에 상태 업데이트가 없는 경우 `lpFileName`합니다. 그렇지 않은 경우 플러그 인 보관 파일의 전체 경로 이름에 상태 정보가 변경 된 반환 하는 적절 한 상태 코드 \(에 자세히 설명 하는 값 중 하나 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)\).  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)