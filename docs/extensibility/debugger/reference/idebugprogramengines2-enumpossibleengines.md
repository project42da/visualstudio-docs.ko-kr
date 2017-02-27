---
title: "IDebugProgramEngines2::EnumPossibleEngines | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramEngines2::EnumPossibleEngines"
helpviewer_keywords: 
  - "IDebugProgramEngines2::EnumPossibleEngines"
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgramEngines2::EnumPossibleEngines
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램을 디버깅할 수 있는 모든 가능한 디버그 엔진 \(DE\)에 대 한 Guid를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumPossibleEngines(   
   DWORD  celtBuffer,  
   GUID*  rgguidEngines,  
   DWORD* pceltEngines  
);  
```  
  
```c#  
int EnumPossibleEngines(   
   uint      celtBuffer,  
   GUID[]    rgguidEngines,  
   ref DWORD pceltEngines  
);  
```  
  
#### 매개 변수  
 `celtBuffer`  
 \[in\] 수 반환 합니다 DE Guid입니다.  이의 최대 크기를 지정 합니다는 `rgguidEngines` 배열입니다.  
  
 `rgguidEngines`  
 \[in, out\] DE에서 Guid의 배열입니다.  
  
 `pceltEngines`  
 \[out\] 실제 수를 반환 하는 DE Guid를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  \[C \+ \+\] 반환 `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` 또는 \[C\#\] 0x8007007A 버퍼가 충분히 큰 경우입니다.  
  
## 설명  
 엔진 있을 수를 확인 하려면이 메서드를 한 번 호출을 `celtBuffer` 매개 변수를 0으로 설정 하는 `rgguidEngines` 매개 변수 값이 null로 설정 합니다.  이 반환 `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` \(0x8007007A\) C\#에 대 한 및 해당 `pceltEngines` 매개 변수를 필요한 버퍼 크기를 반환 합니다.  
  
## 참고 항목  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)