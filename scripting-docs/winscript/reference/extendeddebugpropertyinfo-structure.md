---
title: "ExtendedDebugPropertyInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ExtendedDebugPropertyInfo
apilocation: scrobj.dll
helpviewer_keywords: 
  - "ExtendedDebugPropertyInfo 구조체"
ms.assetid: f2cf6477-454b-4d13-95da-ae4c90daa175
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ExtendedDebugPropertyInfo 구조체
확장은 `DebugPropertyInfo` 구조와 확장된 속성 특성 추가 멤버.  
  
## 구문  
  
```  
typedef struct ExtendedDebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   LPOLESTR  bstrName;  
   LPOLESTR  bstrType;  
   LPOLESTR  bstrValue;  
   LPOLESTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
   DWORD  nDISPID;  
   DWORD  nType;  
   VARIANT  varValue;  
   ILockBytes*  plbValue;  
   IDebugExtendedProperty*  pDebugExtProp;  
};  
```  
  
## Members  
 `dwValidFields`  
 열거 데이터 형식을 지정할 필드를 초기화 하는 데 사용 합니다.  
  
 `bstrName`  
 컨텍스트 내에서 속성 이름입니다.  
  
 `bstrType`  
 속성으로 서식이 지정 된 문자열을 입력 합니다.  
  
 `bstrValue`  
 서식이 지정 된 문자열 속성 값입니다.  
  
 `bstrFullName`  
 속성의 전체 이름입니다.  
  
 `dwAttrib`  
 디버그 속성 특성에 대 한 플래그를 지정 하는 열거형입니다.  
  
 `pDebugProp`  
 `IDebugProperty`이에 해당 하는 개체 `ExtendedDebugPropertyInfo`.  
  
 `nDISPID`  
 디스패치 id입니다.  
  
 `nType`  
 확장된 속성 형식입니다.  
  
 `varValue`  
 확장된 속성 값의 VARIANT를 맞출 수 있을 경우  
  
 `plbValue`  
 속성 값의 실제 데이터 바이트 수입니다.  
  
 `pDebugExtProp`  
 `IDebugExtendedProperty`이에 해당 하는 개체 `ExtendedDebugPropertyInfo`.  
  
## 참고 항목  
 [DebugPropertyInfo 구조체](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)   
 [IDebugExtendedProperty 인터페이스](../../winscript/reference/idebugextendedproperty-interface.md)   
 [DBGPROP\_ATTRIB\_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP\_INFO\_FLAGS](../../winscript/reference/dbgprop-info-flags.md)