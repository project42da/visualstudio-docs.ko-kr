---
title: "PDB_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PDB_TYPE"
helpviewer_keywords: 
  - "PDB_TYPE 구조"
ms.assetid: 1c1bb772-77d6-4870-90b2-fd9247d0004e
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# PDB_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조에서 PDB를 기호 라인 필드 형식에 대 한 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _tagTYPE_PDB {  
   ULONG32 ulAppDomainID;  
   GUID    guidModule;  
   DWORD   symid;  
} PDB_TYPE;  
```  
  
```c#  
public struct PDB_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public uint symid;  
};  
```  
  
#### 매개 변수  
 ulAppDomainID  
 심볼의 원본 응용 프로그램의 ID입니다.  이 응용 프로그램의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.  
  
 guidModule  
 이 필드를 포함 하는 모듈의 GUID입니다.  
  
 symid  
 ID이이 필드에 해당 하는 기호입니다.  
  
## 설명  
 이 구조에 공용 구조체의 일부로 표시 되는 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md) 때 구조는 `dwKind` 필드는 `TYPE_INFO` 구조 설정 되어 `TYPE_KIND_PDB` \(값의 [dwTYPE\_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) 열거형\).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE\_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)