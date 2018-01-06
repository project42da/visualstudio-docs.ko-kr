---
title: IDebugProperty2::SetValueAsString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2::SetValueAsString
helpviewer_keywords: IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1fb87f1ad075c0bae10c4d154b2c0e0fa2ceb999
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
지정 된 문자열에서 속성의 값을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetValueAsString (   
   LPCOLESTR pszValue,  
   UINT      nRadix,  
   DWORD     dwTimeout  
);  
```  
  
```csharp  
int SetValueAsString (   
   string pszValue,  
   uint   nRadix,  
   uint   dwTimeout  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszValue`  
 [in] 설정할 값을 포함 하는 문자열입니다.  
  
 `nRadix`  
 [in] 모든 숫자 정보를 해석 하는 데 사용할 기 수입니다. 이 경우 0을 기 수를 자동으로 확인 하도록 수 있습니다.  
  
 `dwTimeout`  
 [in] 이 메서드로부터 반환 하기 전에 대기할 밀리초 단위로 최대 시간을 지정 합니다. 사용 하 여 `INFINITE` 무기한 대기를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다. 다음 표에서 가능한 다른 값을 보여 줍니다.  
  
|값|설명|  
|-----------|-----------------|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|문자열 속성 값으로 변환할 수 없습니다 또는 속성 값을 설정할 수 없습니다.|  
|`E_SETVALUE_VALUE_IS_READONLY`|속성이 읽기 전용입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)