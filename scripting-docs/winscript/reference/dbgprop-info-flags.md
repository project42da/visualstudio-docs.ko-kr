---
title: "DBGPROP_INFO_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: DBGPROP_INFO_FLAGS
apilocation: scrobj.dll
f1_keywords: 
  - "DBGPROP_INFO_FLAGS"
helpviewer_keywords: 
  - "DBGPROP_INFO_FLAGS"
ms.assetid: e9450a21-a802-4c3e-8b3d-8e202f555de1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# DBGPROP_INFO_FLAGS
지정 하는 데 사용 `DebugPropertyInfo` 필드  
  
## 구문  
  
```  
enum {  
   DBGPROP_INFO_NAME  =0x001,  
   DBGPROP_INFO_TYPE  =0x002,  
   DBGPROP_INFO_VALUE  =0x004,  
   DBGPROP_INFO_FULLNAME  =0x020,  
   DBGPROP_INFO_ATTRIBUTES  =0x008,  
   DBGPROP_INFO_DEBUGPROP  =0x010,  
   DBGPROP_INFO_AUTOEXPAND  =0x8000000  
};  
```  
  
## Members  
 DBGPROP\_INFO\_NAME  
 초기화는 `bstrName` 필드입니다.  
  
 DBGPROP\_INFO\_TYPE  
 초기화는 `bstrType` 필드입니다.  
  
 DBGPROP\_INFO\_VALUE  
 초기화는 `bstrValue` 필드입니다.  
  
 DBGPROP\_INFO\_FULLNAME  
 초기화는 `bstrFullName` 필드입니다.  
  
 DBGPROP\_INFO\_ATTRIBUTES  
 초기화는 `dwAttrib` 필드입니다.  
  
 DBGPROP\_INFO\_DEBUGPROP  
 초기화는 `pDebugProp` 필드는 `IDebugProperty` 인터페이스.  
  
 DBGPROP\_INFO\_AUTOEXPAND  
 사용 가능한 경우이 형식의 개체에 대 한 값 필드 자동 확장 값을 포함 하도록 지정 합니다.  
  
## 참고 항목  
 [DebugPropertyInfo 구조체](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)