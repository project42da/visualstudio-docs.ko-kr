---
title: "IDebugFormatter::GetVariantForString | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugFormatter.GetVariantForString
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugFormatter::GetVariantForString"
ms.assetid: 2993431d-0ee2-4d8d-b62c-0a810a8bc391
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugFormatter::GetVariantForString
지정 된 문자열을 포함 하는 VARIANT를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetVariantForString(  
   LPCOLESTR  pwstrValue,  
   VARIANT*   pvar  
);  
```  
  
#### 매개 변수  
 `pwstrValue`  
 \[in\] VARIANT에 저장 하는 문자열입니다.  
  
 `pvar`  
 \[out\] 변형 포함 된 `pwstrValue`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 이렇게 지정 된 문자열을 포함 하는 VARIANT를 반환 합니다.  
  
## 참고 항목  
 [IDebugFormatter 인터페이스](../../winscript/reference/idebugformatter-interface.md)