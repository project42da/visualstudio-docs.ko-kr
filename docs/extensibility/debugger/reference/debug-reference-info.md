---
title: "DEBUG_REFERENCE_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEBUG_REFERENCE_INFO"
helpviewer_keywords: 
  - "DEBUG_REFERENCE_INFO 구조"
ms.assetid: 24b83d00-d756-42a1-8083-730f998761dc
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUG_REFERENCE_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

에 대 한 참조를 설명합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagDEBUG_REFERENCE_INFO {   
   DEBUGREF_INFO_FLAGS dwFields;  
   BSTR                bstrName;  
   BSTR                bstrType;  
   BSTR                bstrValue;  
   DBG_ATTRIB_FLAGS    dwAttrib;  
   REFERENCE_TYPE.     dwRefType;  
   IDebugReference2*   m_pReference;  
} DEBUG_REFERENCE_INFO;  
```  
  
```c#  
public struct DEBUG_REFERENCE_INFO {   
   public uint             dwFields;  
   public string           bstrName;  
   public string           bstrType;  
   public string           bstrValue;  
   public ulong            dwAttrib;  
   public uint.            dwRefType;  
   public IDebugReference2 m_pReference;  
};  
```  
  
## Members  
 dwFields  
 플래그의 조합에서 [DEBUGREF\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) 채워진 필드를 지정 하는 열거형입니다.  
  
 bstrName  
 사용자 지정 이름에는 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체입니다.  
  
 bstrType  
 참조 형식으로 서식이 지정 된 문자열입니다.  
  
 bstrValue  
 참조 값으로 서식이 지정 된 문자열  
  
 dwAttrib  
 플래그의 조합에서 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 디버그 속성 특성에 대 한 플래그를 지정 하는 열거형입니다.  
  
 dwRefType  
 값은 [REFERENCE\_TYPE](../../../extensibility/debugger/reference/reference-type.md) 참조 유형을 잘 되거나 잘 되는지 여부를 지정 하는 열거형입니다.  
  
 m\_pReference  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 참조 정보를 지정 하는 개체입니다.  
  
## 설명  
 이 구조에 대 한 호출에 전달 되는 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md) 메서드를 채워야 합니다.  이 구조에서 목록의 일부로 반환 되는 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md) ,에 대 한 호출에서 반환 되는 인터페이스는 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUGREF\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)   
 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [REFERENCE\_TYPE](../../../extensibility/debugger/reference/reference-type.md)   
 [GetReferenceInfo](../../../extensibility/debugger/reference/idebugreference2-getreferenceinfo.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)   
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)