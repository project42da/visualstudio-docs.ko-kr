---
title: IDebugPortRequest2::GetPortName | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: 10
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5906560574836390656254055130af3275fa4f76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportrequest2getportname"></a>IDebugPortRequest2::GetPortName
포트의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetPortName(   
   BSTR* pbstrPortName  
);  
```  
  
```csharp  
int GetPortName(   
   out string pbstrPortName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pbstrPortName`  
 [out] 포트의 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 인터페이스는 일반적으로 패키지에서 전달는 디버그 (클라이언트)에 연결 하는 연결 포트 공급자 (서버) 포트에 있습니다. 디버그 패키지가 포트 공급자가 인식 하는 포트에 대 한 선택 가능한 항목의 합니다. 간단한 문자열에 해당 포트를 설명할 수 있는 경우 하면 `IDebugPortRequest2::GetPortName` 메서드는 연결을 만드는 데 충분 한 정보입니다. 그렇지 않은 경우 사용 하 여 서버에서 가져올 수 있는 클라이언트에서 추가 인터페이스를 제공할 수 있습니다 `IDebugPortRequest2::QueryInterface`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)