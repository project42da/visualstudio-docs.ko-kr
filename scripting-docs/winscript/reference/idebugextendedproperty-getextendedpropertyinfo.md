---
title: "IDebugExtendedProperty::GetExtendedPropertyInfo | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugExtendedProperty.GetExtendedPropertyInfo
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugExtendedProperty::GetExtendedPropertyInfo"
ms.assetid: 56edf538-5082-4653-82b6-e6640d6f61ba
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExtendedProperty::GetExtendedPropertyInfo
자세한 정보 보다는 간단한 확장된 속성에 대 한 확장된 정보를 페치 \(fetch\) `IDebugProperty`.  
  
## 구문  
  
```  
HRESULT GetExtendedPropertyInfo(  
   EX_DBGPROP_INFO_FLAGS  dwFieldSpec,  
   UINT  nRadix,  
   ExtendedDebugPropertyInfo*  pExtendedPropertyInfo  
);  
```  
  
#### 매개 변수  
 `dwFieldSpec`  
 \[in\] 지정에 채워야 하는 필드를 확인 하는 EX\_DBGPROP\_INFO\_FLAGS 상수는 `ExtendedDebugPropertyInfo` 구조.  
  
 `nRadix`  
 \[in\] 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
 `pExtendedPropertyInfo`  
 \[out\] 반환 된 `ExtendedDebugPropertyInfo` 속성에 설명 하는 구조입니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IDebugExtendedProperty 인터페이스](../../winscript/reference/idebugextendedproperty-interface.md)   
 [EX\_DBGPROP\_INFO\_FLAGS](../../winscript/reference/ex-dbgprop-info-flags.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)