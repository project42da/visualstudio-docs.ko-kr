---
title: "METADATA_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "METADATA_TYPE"
helpviewer_keywords: 
  - "METADATA_TYPE 구조"
ms.assetid: 2d8b78f6-0aef-4d79-809a-cff9b2c24659
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# METADATA_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조체는 메타 데이터에서 가져온 필드 형식에 대 한 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _tagTYPE_METADATA {  
   ULONG32  ulAppDomainID;  
   GUID     guidModule;  
   _mdToken tokClass;  
} METADATA_TYPE;  
```  
  
```c#  
public struct METADATA_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public int  tokClass;  
};  
```  
  
#### 매개 변수  
 ulAppDomainID  
 기호를 가져온 응용 프로그램의 ID입니다. 이 응용 프로그램의 인스턴스를 고유 하 게 식별 하기 위해 사용 됩니다.  
  
 guidModule  
 이 필드를 포함 하는 모듈의 GUID입니다.  
  
 tokClass  
 이러한 종류의 메타 데이터 토큰 ID입니다.  
  
 \[C\+\+\] `_mdToken` 한 `typedef` 32 비트 `int`합니다.  
  
## 설명  
 이 구조에는 공용 구조체의 일부분으로 표시는 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md) 때 구조는 `dwKind` 필드는 `TYPE_INFO` 구조로 설정 된 `TYPE_KIND_METADATA` \(의 값은 [dwTYPE\_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) 열거형\)입니다.  
  
 `tokClass` 값은 형식을 고유 하 게 식별 하는 메타 데이터 토큰입니다. 메타 데이터 토큰 ID의 상위 비트를 해석 하는 방법에 대 한 자세한 내용은 참조는 `CorTokenType` 열거형에서 corhdr.h 파일에는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE\_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)