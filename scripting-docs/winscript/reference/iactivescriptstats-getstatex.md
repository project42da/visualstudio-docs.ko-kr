---
title: "IActiveScriptStats::GetStatEx | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptStats.GetStatEx
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptStats::GetStatEx"
ms.assetid: f526f51d-8ab5-49ef-a8f7-ae0ac1cb46e4
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptStats::GetStatEx
사용자 지정 스크립트 통계를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetStatEx(  
   REFGUID  guid,  
   ULONG*   pluHi,  
   ULONG*   pluLo  
);  
```  
  
#### 매개 변수  
 `guid`  
 \[in\] 반환 하는 통계를 지정 합니다.  의미 체계의 특정 하는 통계에 해당 GUID 완전히 정의 엔진입니다.  
  
 `pluHi`  
 \[out\] 상위 32 비트 통계를 나타내는 64 비트 부호 없는 정수입니다.  
  
 `pluLo`  
 \[out\] 하위 32 비트 통계를 나타내는 64 비트 부호 없는 정수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|메서드가 구현되지 않았습니다.|  
  
## 설명  
 이 메서드는 사용자 지정 호스트에 의미 있는 통계를 반환 하는 사용자 지정 스크립트 엔진이 있습니다.  
  
> [!NOTE]
>  이 메서드가 현재 구현되지 않았습니다.  
  
## 참고 항목  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats 인터페이스](../../winscript/reference/iactivescriptstats-interface.md)