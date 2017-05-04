---
title: "IActiveScriptStats::GetStat | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptStats.GetStat
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptStats::GetStat"
ms.assetid: 31fd15b3-0713-4b55-b4f7-bfd7ea198493
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptStats::GetStat
표준 스크립트 통계 중 하나를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetStat(  
   DWORD   stid,  
   ULONG*  pluHi,  
   ULONG*  pluLo  
);  
```  
  
#### 매개 변수  
 `stid`  
 \[in\] 반환 하는 통계를 지정 합니다.  값 이어야 합니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|SCRIPTSTAT\_STATEMENT\_COUNT|1|시작 스크립트 또는 통계가 다시 설정 된 이후에 실행 된 문 수를 반환 합니다.|  
  
 `pluHi`  
 \[out\] 상위 32 비트 통계를 나타내는 64 비트 부호 없는 정수입니다.  
  
 `pluLo`  
 \[out\] 하위 32 비트 통계를 나타내는 64 비트 부호 없는 정수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값에는 포함 되지만 다음 표에 있는 값으로 제한 되지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 표준 스크립트 통계 중 하나를 반환합니다.  
  
## 참고 항목  
 [IActiveScriptStats::GetStatEx](../../winscript/reference/iactivescriptstats-getstatex.md)   
 [IActiveScriptStats 인터페이스](../../winscript/reference/iactivescriptstats-interface.md)