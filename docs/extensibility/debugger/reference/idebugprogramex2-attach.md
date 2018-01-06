---
title: IDebugProgramEx2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEx2::Attach
helpviewer_keywords: IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 440a4ce6b008efe541187d1d99d886f4c7c5f9ab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
프로그램에 세션을 연결 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 연결 된 디버그 엔진 이벤트를 전송 하는 콜백 함수를 나타내는 개체입니다.  
  
 `dwReason`  
 [in] 값은 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) 연결 작업에 대 한 이유를 설명 하는 열거형입니다.  
  
 `pSession`  
 [in] 이 프로그램에 연결 하는 세션을 고유 하 게 식별 하는 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드가 반환 됩니다. 이 메서드를 반환 하도록 `E_ATTACH_DEBUGGER_ALREADY_ATTACHED` 프로그램 이미 연결 된 경우.  
  
## <a name="remarks"></a>설명  
 프로그램을 포함 하는 포트에 값을 사용할 수 `pSession` 는 세션에서 프로그램에 연결 하려고 합니다. 확인 하려면. 예를 들어 프로세스에 연결 하는 한 번에 하나만 디버그 세션을 허용 하는 포트를 포트 같은 세션 프로세스에서 다른 프로그램에 이미 연결 되어 있는지 확인할 수입니다.  
  
> [!NOTE]
>  인터페이스에 전달 `pSession` 쿠키, 세션 디버그 관리자;이 프로그램에 연결을 고유 하 게 식별 하는 값 으로만 간주 하는 것에 제공 된 인터페이스 메서드는 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)