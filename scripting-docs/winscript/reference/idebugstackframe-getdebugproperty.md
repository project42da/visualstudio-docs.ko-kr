---
title: "IDebugStackFrame::GetDebugProperty | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugStackFrame.GetDebugProperty
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugStackFrame::GetDebugProperty"
ms.assetid: e03c7504-bce4-4a44-81e4-db8c0216538d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrame::GetDebugProperty
속성 브라우저에 현재 프레임을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetDebugProperty(  
   IDebugProperty**  ppDebugProp  
);  
```  
  
#### 매개 변수  
 `ppDebugProp`  
 \[out\] 현재 프레임에 대 한 속성 브라우저입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 속성 브라우저에 현재 프레임에 대 한 반환합니다.  
  
## 참고 항목  
 [IDebugStackFrame 인터페이스](../../winscript/reference/idebugstackframe-interface.md)