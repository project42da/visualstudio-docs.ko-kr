---
title: IDebugPortPicker::DisplayPortPicker | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DisplayPortPicker
- IDebugPortPicker::DisplayPortPicker
ms.assetid: 08511ef5-be64-4069-b169-a569cc94bc64
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bf6dee7f9c79e82d9e952e481c638c870308e890
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugportpickerdisplayportpicker"></a>IDebugPortPicker::DisplayPortPicker
사용자가 포트를 선택할 수 있는 지정 된 대화 상자를 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DisplayPortPicker(  
   HWND hwndParentDialog,  
   BSTR* pbstrPortId  
);  
```  
  
```csharp  
public int DisplayPortPicker(  
   int hwndParentDialog,  
   out string pbstrPortId  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hwndParentDialog`  
 [in] 부모 대화 상자에 대 한 핸들입니다.  
  
 `pbstrPortId`  
 [out] 포트 식별자 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. 반환 값이 `S_FALSE` (또는 반환 값이 `S_OK` 와 `BSTR` 로 설정 `NULL`) 사용자가 클릭 했음을 나타냅니다. **취소**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)