---
title: IDebugProgramPublisher2::UnpublishProgram | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramPublisher2::UnpublishProgram
helpviewer_keywords: IDebugProgramPublisher2::UnpublishProgram
ms.assetid: 627e7d38-b2ac-4873-9a40-37ff7f47cd1d
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 17a2bde6cf83df906a50c4683e0455978060ae22
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogrampublisher2unpublishprogram"></a>IDebugProgramPublisher2::UnpublishProgram
디버깅을 사용할 수 없는 프로그램을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT UnpublishProgram(  
   IUnknown* pDebuggeeInterface  
);  
```  
  
```csharp  
int UnpublishProgram(  
   object pDebuggeeInterface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pDebuggeeInterface`  
 [in] `IUnknown` 프로그램에 대 한 인터페이스입니다. 이 값은 동일한 값에 제공 되는 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) 메서드 제거 하 고 프로그램을 고유 하 게 식별 하 고 (즉, 쿠키로 사용 됩니다).  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 프로그램을 사용 하려면 디버그 엔진 및 세션 디버그 관리자를 사용 하 여는 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)