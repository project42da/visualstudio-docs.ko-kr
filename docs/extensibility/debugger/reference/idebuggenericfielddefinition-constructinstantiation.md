---
title: IDebugGenericFieldDefinition::ConstructInstantiation | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ConstructInstantiation
- IDebugGenericFieldDefinition::ConstructInstantiation
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d2a7c9b85c3025e3e23bbd316c84fce9f0d741fc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggenericfielddefinitionconstructinstantiation"></a>IDebugGenericFieldDefinition::ConstructInstantiation
지정 된 형식 인수 배열을 필드 인스턴스를 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ConstructInstantiation(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   IDebugField** ppConstructedField  
);  
```  
  
```csharp  
int ConstructInstantiation(  
   uint            cArgs,  
   IDebugField[]   ppArgs,  
   out IDebugField ppConstructedField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cArgs`  
 [in] 인수 개수는 `ppArgs` 배열입니다.  
  
 `ppArgs`  
 [in] 형식 인수를 포함 하는 배열입니다. 형식 인수 (제네릭이 아닌 또는 전체적으로 인스턴스화된 제네릭) 닫힌된 형식 이어야 합니다.  
  
 `ppConstructedField`  
 [out] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 새 필드를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 제약 조건이 확인 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)