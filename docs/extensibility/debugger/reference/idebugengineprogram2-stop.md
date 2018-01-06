---
title: IDebugEngineProgram2::Stop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngineProgram2::Stop
helpviewer_keywords: IDebugEngineProgram2::Stop
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4004ca92b32e63565a71a3a6971ebb4ae073b9f9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengineprogram2stop"></a>IDebugEngineProgram2::Stop
이 프로그램에서 실행 중인 모든 스레드를 중지 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Stop(   
   void   
);  
```  
  
```csharp  
int Stop();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 다중 프로그램 환경에서이 프로그램을 디버깅 되는 호출 됩니다. 다른 프로그램에서 중지 이벤트를 받으면이 프로그램에이 메서드가 호출 됩니다. 이 메서드 구현은 비동기; 해야 합니다. 즉, 모든 스레드는이 메서드가 반환 되기 전에 중지 하는 데 필요한 이어야 합니다. 이 메서드의 구현을 호출 처럼 간단 해질 수 있습니다는 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) 이 프로그램에 메서드.  
  
 디버그 이벤트가이 메서드에 대 한 응답으로 전송 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)