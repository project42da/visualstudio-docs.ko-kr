---
title: IDebugArrayObject::GetElement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayObject::GetElement
helpviewer_keywords: IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dbe40cd481d3044eb87b5c5935e023bc7b110a50
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
배열의 요소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```csharp  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwIndex`  
 [in] 요소의 인덱스입니다.  
  
 `ppElement`  
 [out] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 요소를 나타내는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 배열 개체는 다차원 배열 하는 경우에 배열 개체의 요소를 모두 1 차원 배열에으로 간주 합니다. 예를 들어 배열의 지정 된 `myarray[3][2][6]` 및 `dwIndex` 20 매개 변수를이 메서드는 반환 요소 `myarray[1][1][2]`, 및 `dwIndex` 21의 매개 변수에서 요소를 반환 합니다 `myarray[1][1][3]`합니다. 사용 하 여는 [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) 메서드는 배열에 있는 요소의 총 수를 결정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)