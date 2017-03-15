---
title: "IDebugMessageEvent2::GetMessage | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: a54fe55d214e23394783f92c6ce6311257d5ef5d
ms.lasthandoff: 02/22/2017

---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
표시할 메시지를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT GetMessage(   
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrMessage,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```c#  
int GetMessage(   
   out enum_MESSAGETYPE pMessageType,  
   out string           pbstrMessage,  
   out uint             pdwType,  
   out string           pbstrHelpFileName,  
   out uint             dwHelpId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pMessageType`  
 [out] 값을 반환 된 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) 메시지의 형식을 설명 하는 열거형입니다.  
  
 `pbstrMessage`  
 [out] 메시지를 반환합니다.  
  
 `pdwType`  
 [out] Win32의 규칙을 사용 하는 메시지의 형식을 반환 `MessageBox` 함수입니다. 참조는 [AfxMessageBox](http://msdn.microsoft.com/Library/d66d0328-cdcc-48f6-96a4-badf089099c8) 세부 정보에 대 한 함수입니다.  
  
 `pbstrHelpFileName`  
 [에서, out] 도움말 파일의 이름을 반환합니다. 도움말 파일이 없는 경우 null (c + +) 또는 빈 값 (C#)를 수 있습니다.  
  
 `pdwHelpId`  
 [에서, out] 도움말 식별자를 반환합니다. 수 될이 메시지와 관련 된 도움말이 없습니다 경우 0입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)   
 [AfxMessageBox](http://msdn.microsoft.com/Library/d66d0328-cdcc-48f6-96a4-badf089099c8)
