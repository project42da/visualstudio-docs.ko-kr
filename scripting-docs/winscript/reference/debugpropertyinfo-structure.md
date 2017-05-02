---
title: "DebugPropertyInfo 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: DebugPropertyInfo
apilocation: scrobj.dll
helpviewer_keywords: 
  - "DebugPropertyInfo 구조체"
ms.assetid: 3246efbc-c212-4024-8f07-6414c2f85e75
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# DebugPropertyInfo 구조체
개체 이름, 형식 및 값을 가진 계층적 특성을 설명 합니다.  지역 변수, 매개 변수, 조사식 변수 및 식의 디버그 속성을 설명 하는 데 사용 하 고 등록 합니다.  
  
## 구문  
  
```  
typedef struct DebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   BSTR  bstrName;  
   BSTR  bstrType;  
   BSTR  bstrValue;  
   BSTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
};  
```  
  
## Members  
 dwValidFields  
 열거 데이터 형식을 지정할 필드를 초기화 하는 데 사용 합니다.  
  
 bstrName  
 컨텍스트 내에서 속성 이름입니다.  
  
 bstrType  
 문자열로 형식이 지정 된 속성 형식입니다.  
  
 bstrValue  
 서식이 지정 된 문자열 속성 값입니다.  
  
 bstrFullName  
 속성의 전체 이름입니다.  
  
 dwAttrib  
 디버그 속성 특성에 대 한 플래그를 지정 하는 열거형입니다.  
  
 pDebugProp  
 `IDebugProperty` 이 정보에서 설명한 `DebugPropertyInfo` 구조.  
  
## 참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP\_ATTRIB\_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP\_INFO\_FLAGS](../../winscript/reference/dbgprop-info-flags.md)