---
title: IDebugGenericParamField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugGenericParamField interface
ms.assetid: ba24f499-5ba7-4c67-83e6-923229b52327
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c1f187c96798f0da713d5100e9a444e3144530d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericparamfield"></a>IDebugGenericParamField
관리 코드 제네릭 형식에 대 한 매개 변수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugGenericParamField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 제네릭의 지원에 사용 됩니다.  
  
## <a name="methods"></a>메서드  
 메서드 외에도 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[ConstraintCount](../../../extensibility/debugger/reference/idebuggenericparamfield-constraintcount.md)|이 제네릭 매개 변수 연관 된 제약 조건의 수를 반환 합니다.|  
|[GetConstraints](../../../extensibility/debugger/reference/idebuggenericparamfield-getconstraints.md)|이 제네릭 매개 변수 연관 된 제약 조건을 검색 합니다.|  
|[GetFlags](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|이 제네릭 매개 변수 플래그를 검색 합니다.|  
|[GetIndex](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|이 제네릭 매개 변수의 인덱스를 검색합니다.|  
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|이 제네릭 매개 변수 이름을 검색합니다.|  
|[GetOwner](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|이 제네릭 매개 변수 형식 또는 메서드의 소유자를 검색합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll