---
title: "EX_DBGPROP_INFO_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: EX_DBGPROP_INFO_FLAGS
apilocation: scrobj.dll
helpviewer_keywords: 
  - "EX_DBGPROP_INFO_FLAGS"
ms.assetid: ee309dfe-9432-4dff-8756-7a8d677f9dcc
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# EX_DBGPROP_INFO_FLAGS
지정 하는 데 사용 `ExtendedDebugPropertyInfo` 필드입니다.  
  
## 구문  
  
```  
enum {  
   EX_DBGPROP_INFO_ID  =0x0100,  
   EX_DBGPROP_INFO_NTYPE  =0x0200,  
   EX_DBGPROP_INFO_NVALUE  =0x0400,  
   EX_DBGPROP_INFO_LOCKBYTES  =0x0800,  
   EX_DBGPROP_INFO_DEBUGEXTPROP  =0x1000  
};  
```  
  
## Members  
 EX\_DBGPROP\_INFO\_ID  
 식별자 속성을 초기화합니다.  
  
 EX\_DBGPROP\_INFO\_NTYPE  
 초기화 속성을 입력합니다.  
  
 EX\_DBGPROP\_INFO\_NVALUE  
 속성의 값을 초기화합니다.  
  
 EX\_DBGPROP\_INFO\_LOCKBYTES  
 초기화는 `plb` 필드입니다.  
  
 EX\_DBGPROP\_INFO\_DEBUGEXTPROP  
 초기화는 `pDebugExtProp` 필드는 `IDebugExtendedProperty` 인터페이스.  
  
## 참고 항목  
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)   
 [IDebugExtendedProperty 인터페이스](../../winscript/reference/idebugextendedproperty-interface.md)