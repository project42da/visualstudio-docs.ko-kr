---
title: IDebugClassField::DoesInterfaceExist | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugClassField::DoesInterfaceExist
helpviewer_keywords: IDebugClassField::DoesInterfaceExist method
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 07a4760064003a45af55aa747192e044edca8e0c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugclassfielddoesinterfaceexist"></a>IDebugClassField::DoesInterfaceExist
클래스에는 특정 인터페이스는 정의 하는 경우를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```csharp  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pszInterfaceName`  
 [in] 찾으려는 인터페이스 이름을 포함 하는 문자열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 S_OK를 반환, S_FALSE를 반환 합니다. 인터페이스; 존재 하지 않는 경우 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 유효한 모든 인터페이스의 열거형을 가져옵니다 하 고 일치 하는 인터페이스에 대 한 목록을 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)