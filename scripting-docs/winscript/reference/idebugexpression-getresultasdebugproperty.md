---
title: "IDebugExpression::GetResultAsDebugProperty | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugExpression.GetResultAsDebugProperty
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugExpression::GetResultAsDebugProperty"
ms.assetid: 9075bf2f-d5bb-464e-b6c2-3fa3215e9ae0
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExpression::GetResultAsDebugProperty
디버그 속성 및 작업의 반환 값으로 식이 평가의 결과 반환합니다.  
  
## 구문  
  
```  
HRESULT GetResultAsDebugProperty(  
   HRESULT*          phrResult,  
   IDebugProperty**  ppdp  
);  
```  
  
#### 매개 변수  
 `phrResult`  
 \[out\] 작업의 반환 값입니다.  
  
 `ppdp`  
 \[out\] 디버그 속성 식입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_PENDING`|작업이 계속 됩니다 보류 합니다.|  
  
## 설명  
 식 평가 결과 반환 하는이 메서드는 `IDebugProperty` 및 작업의 `HRESULT`.  
  
 이 메서드를 반환 합니다. `S_OK` 및 `phrResult` 반환 `E_ABORT` 경우 `Abort` 작업을 중단 합니다.  
  
## 참고 항목  
 [IDebugExpression 인터페이스](../../winscript/reference/idebugexpression-interface.md)   
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)