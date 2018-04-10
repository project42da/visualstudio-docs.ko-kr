---
title: IDebugField::GetExtendedInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugField::GetExtendedInfo
helpviewer_keywords:
- IDebugField::GetExtendedInfo method
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
caps.latest.revision: 13
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c6b2aaa953e47366e7a99fb5a821f530d37ed66e
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="idebugfieldgetextendedinfo"></a>IDebugField::GetExtendedInfo
이 메서드는 필드에 대 한 정보를 확장을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetExtendedInfo(   
   REFGUID guidExtendedInfo,  
   BYTE**  prgBuffer,  
   DWORD*  pdwLen  
);  
```  
  
```csharp  
int GetExtendedInfo(  
   ref Guid guidExtendedInfo,   
   IntPtr[] prgBuffer,   
   ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidExtendedInfo`  
 [in] 반환 될 정보를 선택 합니다. 올바른 값은 다음과 같습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`guidConstantValue`|바이트의 시퀀스 값입니다.|  
|`guidConstantType`|형식 서명에 형식입니다.|  
  
 `prgBuffer`  
 [out] 확장 된 정보를 반환합니다.  
  
 `pdwLen`  
 [out에서] 확장 정보의 크기 바이트 단위로 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 현재,이 메서드는 형식 또는 상수 값을 반환합니다. 호출자에 반환 되는 버퍼를 해제 해야 `prgBuffer` COM의 호출 `CoTaskMemFree` 함수 (c + +) 또는 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> (C#).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)