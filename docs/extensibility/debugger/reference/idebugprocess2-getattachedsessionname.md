---
title: IDebugProcess2::GetAttachedSessionName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess2::GetAttachedSessionName
helpviewer_keywords: IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8ca045a1fee17891fbe053d1d072a4affa41c787
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
이 프로세스를 디버그 하는 세션의 이름을 가져옵니다. IDE를 사용자에 게 특정 컴퓨터에서 특정 프로세스를 디버깅 하는이 정보를 표시할 수 있습니다.  
  
> [!NOTE]
>  이 메서드는 더 이상 해당 구현은 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrSessionName`  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)