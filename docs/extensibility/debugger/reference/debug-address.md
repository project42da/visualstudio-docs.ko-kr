---
title: "DEBUG_ADDRESS | Microsoft Docs"
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
  - "DEBUG_ADDRESS"
helpviewer_keywords: 
  - "DEBUG_ADDRESS 구조"
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUG_ADDRESS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조체의 주소를 나타냅니다.  
  
## 구문  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS {  
   ULONG32             ulAppDomainID;  
   GUID                guidModule;  
   _mdToken            tokClass;  
   DEBUG_ADDRESS_UNION addr;  
} DEBUG_ADDRESS;  
```  
  
```c#  
public struct DEBUG_ADDRESS {  
   public uint                ulAppDomainID;  
   public Guid                guidModule;  
   public int                 tokClass;  
   public DEBUG_ADDRESS_UNION addr;  
}  
```  
  
## 용어  
 ulAppDomainID  
 프로세스 id입니다.  
  
 guidModule  
 이 주소를 포함 하는 모듈의 GUID입니다.  
  
 tokClass  
 클래스 또는이 주소 유형을 식별 하는 토큰입니다.  
  
> [!NOTE]
>  이 값은 기호 공급자에 따라 다릅니다 및 따라서 일반 이외의 클래스 형식에 대 한 식별자로 의미가.  
  
 대상 주소  
 A [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 주소 유형에 대해 설명 하는 구조체의 공용 구조체를 포함 하는 구조입니다.  값 `addr`.`dwKind` 에서 제공 되는 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 통합 해석 하는 방법에 설명 하는 열거형입니다.  
  
## 설명  
 이 구조체에 전달 되는 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) 메서드를 채워야 합니다.  
  
 **경고 \[c \+ \+에만\]**  
  
 경우 `addr.dwKind` 입니다 `ADDRESS_KIND_METADATA_LOCAL` 경우 `addr.addr.addrLocal.pLocal` 호출 해야 하 고 값이 null입니다 `Release` 토큰 포인터:  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md)