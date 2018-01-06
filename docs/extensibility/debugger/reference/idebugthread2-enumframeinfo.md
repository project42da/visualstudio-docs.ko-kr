---
title: IDebugThread2::EnumFrameInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThread2::EnumFrameInfo
helpviewer_keywords: IDebugThread2::EnumFrameInfo
ms.assetid: 17914a71-10ea-4b6f-8982-e364f87dca53
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a906cb23432c9b51d80ee6e0ff97cc5d30f2a665
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthread2enumframeinfo"></a>IDebugThread2::EnumFrameInfo
이 스레드에 대 한 스택 프레임의 목록을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumFrameInfo (   
   FRAMEINFO_FLAGS        dwFieldSpec,  
   UINT                   nRadix,  
   IEnumDebugFrameInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumFrameInfo (   
   enum_FRAMEINFO_FLAGS     dwFieldSpec,  
   uint                     nRadix,  
   out IEnumDebugFrameInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwFieldSpec`  
 [in] 플래그의 조합을 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) 의 필드를 지정 하는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조는 데이터를 입력할 수 있습니다. 지정 된 `FIF_FUNCNAME_FORMAT` 함수 이름은 단일 문자열로 서식을 지정 하는 플래그입니다.  
  
 `nRadix`  
 [in] 열거자의 숫자 정보를 서식 지정에 사용 되는 기 수입니다.  
  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) 의 목록을 포함 하는 개체 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 스택 프레임을 설명 하는 구조입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 스레드 프레임 가장 먼저 열거 현재 프레임 및 가장 오래 된 프레임 마지막 열거 순서에 열거 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)