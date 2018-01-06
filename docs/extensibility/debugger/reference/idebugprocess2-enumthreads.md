---
title: IDebugProcess2::EnumThreads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::EnumThreads
helpviewer_keywords: IDebugProcess2::EnumThreads
ms.assetid: 05677385-7a7f-4545-8438-af00dde85db0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4e13147e12a630c596d19bcad99e81f2476d9a58
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess2enumthreads"></a>IDebugProcess2::EnumThreads
프로세스에서 실행 중인 모든 스레드의 목록을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumThreads(  
   IEnumDebugThreads2** ppEnum  
);  
```  
  
```csharp  
int EnumThreads(  
   out IEnumDebugThreads2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md) 프로세스의 모든 응용 프로그램에서 모든 스레드의 목록을 포함 하는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 각 프로그램에서 실행 중인 스레드를 열거 하 고 결합 하 여 스레드는 프로세스 보기. 여러 프로그램; 단일 스레드가 실행 될 수 있습니다. 이 메서드는 한 번만 해당 스레드를 열거합니다.  
  
 이 메서드는 중복 없이 프로세스의 스레드가 목록을 제공 합니다. 그렇지 않은 경우 사용할 특정 프로그램에서 실행 중인 스레드를 열거 하는 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)