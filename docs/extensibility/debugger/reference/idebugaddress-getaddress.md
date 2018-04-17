---
title: IDebugAddress::GetAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugAddress::GetAddress
helpviewer_keywords:
- IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e7f93b57d3cdbea71d3cf9cbe3d51645251c9628
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
개체 및 해당 범위 또는 컨테이너 내에서 위치를 설명 하는 구조를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```csharp  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pAddress`  
 [out에서] A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 이 메서드에 의해 채워지는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 구조는 다음 적절 한 정보를 사용 하 여 폴더는이 메서드에 전달 됩니다. 이 정보를 해석 하는 방법을 반환 되는 정보 및 기호 처리기 자체의 종류에 따라 달라 집니다. 참조 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 내용을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)