---
title: "IDebugProperty::EnumMembers | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugProperty.EnumMembers
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugProperty::EnumMembers"
ms.assetid: 8ce398a5-6452-4804-ae8f-5c54cd11c661
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProperty::EnumMembers
속성의 구성원을 열거합니다.  
  
## 구문  
  
```  
HRESULT EnumMembers (  
   DBGPROP_INFO_FLAGS dwFieldSpec,  
   UINT nRadix,  
   REFIID refiid,  
   IEnumDebugPropertyInfo** ppEnum  
);  
```  
  
#### 매개 변수  
 `dwFieldSpec`  
 \[in\] 지정 된 `DBGPROP_INFO_FLAGS` 필드에 열거 된 디버그 속성 구조에서 결정 하는 상수.  
  
 `nRadix`  
 \[in\] 숫자 정보를 해석 하는 데 사용할 기 수입니다.  
  
 `refiid`  
 \[in\] 이 IID 열거자 필터링에 전달 됩니다.  IID 중 하나인는 `IDebugPropertyEnumType` 에서 상속 하는 인터페이스 `IDebugPropertyEnumType_All`.  
  
 `ppEnum`  
 \[out\] 반환 된 `IEnumDebugPropertyInfo` 구성원 속성을 열거 하는 인터페이스.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP\_INFO\_FLAGS](../../winscript/reference/dbgprop-info-flags.md)   
 [IDebugPropertyEnumType\_All 인터페이스](../../winscript/reference/idebugpropertyenumtype-all-interface.md)   
 [IEnumDebugPropertyInfo 인터페이스](../../winscript/reference/ienumdebugpropertyinfo-interface.md)