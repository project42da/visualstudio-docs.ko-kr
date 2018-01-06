---
title: IDebugStackFrame2::GetPhysicalStackRange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame2::GetPhysicalStackRange
helpviewer_keywords: IDebugStackFrame2::GetPhysicalStackRange
ms.assetid: 2f6992e2-ac1c-433f-83b7-a7f83a4ce63d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e90137ada43a127dc3c7eac3c98620f3a846d024
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstackframe2getphysicalstackrange"></a>IDebugStackFrame2::GetPhysicalStackRange
스택 프레임과 연결 된 물리적 주소 범위에 대 한 컴퓨터 종속 표현을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPhysicalStackRange (   
   UINT64* paddrMin,  
   UINT64* paddrMax  
);  
```  
  
```csharp  
int GetPhysicalStackRange (   
   out ulong paddrMin,  
   out ulong paddrMax  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `paddrMin`  
 [out] 이 스택 프레임과 연결 된 가장 낮은 물리적 주소를 반환 합니다.  
  
 `paddrMax`  
 [out] 이 스택 프레임과 연결 된 가장 높은 물리적 주소를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 된 정보는 스택 프레임을 정렬 하려면 세션 디버그 관리자 (SDM) 사용 됩니다.  
  
 호출 스택을 다운 즉 증가, 새 스택 프레임 점점 더 낮은 메모리 주소에 추가 된 간주 됩니다. 런타임 아키텍처는이 가정을 일치 하는 물리적 스택과 범위를 제공 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)