---
title: "IDebugProperty::SetValueAsString | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugProperty.SetValueAsString
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugProperty::SetValueAsString"
ms.assetid: cad8d7b2-19a5-4a29-9000-cafdecdc238b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProperty::SetValueAsString
지정 된 문자열에서 속성의 값을 설정합니다.  
  
## 구문  
  
```  
HRESULT SetValueAsString (  
   LPCOLESTR pszValue,  
   UINT nRadix,  
);  
```  
  
#### 매개 변수  
 `pszValue`  
 \[in\] 설정 값입니다.  
  
 `nRadix`  
 \[in\] 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)