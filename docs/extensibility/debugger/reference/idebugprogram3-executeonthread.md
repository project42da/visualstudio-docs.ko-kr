---
title: IDebugProgram3::ExecuteOnThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProgram3::ExecuteOnThread
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 649b16c1b57b2f66772c2117b776e6b79ad862be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram3executeonthread"></a>IDebugProgram3::ExecuteOnThread
디버거가 프로그램을 실행합니다. 스레드를 사용자가 프로그램을 실행 하는 경우 보고 디버거 정보를 제공 하는 스레드 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```csharp  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pThread`  
 [in] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 디버거 중지 한 후 실행을 재개할 수는 세 가지 방법으로  
  
-   실행: 이전 단계를 취소 하 고 등 다음 중단점까지 실행 합니다.  
  
-   단계: 이전 단계를 취소 하 고 새 단계 완료 될 때까지 실행 합니다.  
  
-   계속: 다시 실행 하 고 이전 단계를 활성 상태로 유지 합니다.  
  
 에 전달 되는 스레드 `ExecuteOnThread` 취소 하려면 단계를 결정할 때 유용 합니다. 스레드를 실행 중인 실행 알 수 없는 모든 단계를 취소 합니다. 스레드 정보를 현재 스레드에서 단계 취소 하기만 하면 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)