---
title: IDebugProcessSecurity::GetUserName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: aa8da8828dbbc314ce976572d1f6bd9d5abf5721
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
포트 공급자에서 사용자 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrUserName`  
 [out] 사용자 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 반환 `S_OK`합니다. 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 `GetUserName`에 표시 되는 사용자 이름을 반환 하는 **사용자 이름** 의 열은 **프로세스에 연결** 대화 상자. 보려는 **프로세스에 연결** 대화 상자에서 클릭 **프로세스에 연결** 에 **도구** 메뉴에는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)