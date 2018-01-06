---
title: IDebugCustomAttribute::GetName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCustomAttribute::GetName
helpviewer_keywords: IDebugCustomAttribute::GetName
ms.assetid: ba509cc5-5816-4925-a094-4c72d88c360c
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8237fe3ad25baa912ee3a1eb84da533d788346cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcustomattributegetname"></a>IDebugCustomAttribute::GetName
사용자 지정 특성의 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetName(   
   BSTR* bstrName  
);  
```  
  
```csharp  
int GetName(  
   out string bstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bstrName`  
 [out] 사용자 지정 특성의 이름을 포함 하는 문자열을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드에서 반환 된 명명 된 특성을 선언 하는 데 클래스의 이름에 해당 합니다. C# 내에 허용 "특성" 접미사는 선언에서 사용 하는 경우 사용자 지정 특성 이름에서 삭제할 수를 정확 하 게 사용자 지정 특성 클래스 자체의 이름에 해당 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)