---
title: IDebugCoreServer3::EnableAutoAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords: IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d0b7fbfc1d7c3d9d4ab5214e8c0c5518c6dad5cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
지정 된 디버그 엔진에 대 한 자동 연결을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```csharp  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rgguidSpecificEngines`  
 [in] 으로 자동 연결을 표시 하려면 각 디버그 엔진에 대 한 Guid의 배열입니다.  
  
 `celtSpecificEngines`  
 [in] 엔진에 지정 된 수가 `rgguidSpecificEngines`합니다.  
  
 `pszStartPageUrl`  
 [in] 자동 연결 시 사용할 시작 URL입니다.  
  
 `pbstrSessionID`  
 [out] 자동 연결 된 세션 ID입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다. 한 오류 코드는 `E_AUTO_ATTACH_NOT_REGISTERED`, auto-attach 클래스 팩터리가 등록 되지 않은 나타냅니다.  
  
## <a name="remarks"></a>설명  
 지정 된 URL과 연결 된 프로그램을 시작 하는 경우 지정 된 디버그 엔진을 자동으로 시작 되어 연결 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)