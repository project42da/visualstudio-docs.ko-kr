---
title: IDebugProgramHost2::GetHostName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramHost2::GetHostName
helpviewer_keywords: IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7f1a77c7882dd85c1c64acb492b2522d77649b54
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
제목, 이름, 또는이 프로그램의 호스팅 프로세스의 파일 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```csharp  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwType`  
 [in] 값은 [GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) 열거 합니다.  
  
 `pbstrHostName`  
 [out] 호스팅 프로세스의 요청 된 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 방법의 일반적인 구현에는 `dwType` 매개 변수는 무시 되 고 호스트 컴퓨터의 이름을 반환 됩니다. 전달 하는 또 다른 가능한 구현을 `dwType` 한 호출에 매개 변수는 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) 메서드 이름을 가져올 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)