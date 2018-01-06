---
title: IDebugProcess3::SetHostingProcessLanguage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::SetHostingProcessLanguage
helpviewer_keywords: IDebugProcess3::SetHostingProcessLanguage
ms.assetid: e42f33ed-f29c-4e45-92ce-ab504b72d77c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 59f613543a0f80c1dfc7f43d0973d19fb1a4dd6e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocess3sethostingprocesslanguage"></a>IDebugProcess3::SetHostingProcessLanguage
이 메서드는 프로세스에서 호스팅하는 언어를 설정 합니다. 이 언어 적절 한 식 계산기를 로드 하는 디버그 엔진 (DE)에 의해 사용 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetHostingProcessLanguage(  
   REFGUID guidLang  
);  
```  
  
```csharp  
int SetHostingProcessLanguage(  
   ref Guid guidLang  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidLang`  
 [in] `GUID` 는 DE 사용 해야 하는 언어입니다. 지정 `GUID_NULL` (c + +) 또는 `Guid.Empty` (C#)의 기본 언어를 사용 하 여 장치가 있어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 [GetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-gethostingprocesslanguage.md) 는 현재 언어 설정을 검색 하는 데 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [GetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-gethostingprocesslanguage.md)