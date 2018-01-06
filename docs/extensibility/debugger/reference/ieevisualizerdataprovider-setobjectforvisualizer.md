---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords: IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: feb48452b466301f7987db613997158aed160bac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
이 메서드는 시각화 도우미를 나타내는 개체를 변경 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetObjectForVisualizer(  
   IDebugObject*  pNewObject,  
   BSTR*          error,  
   IDebugObject** pException  
);  
```  
  
```csharp  
int SetObjectForVisualizer(  
   IDebugObject     pNewObject,  
   out string       error,  
   out IDebugObject pException  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pNewObject`  
 [in] 설정할 개체입니다.  
  
 `error`  
 [out] 개체를 설정 하는 동안 오류가 발생 했으면이 문자열 오류 메시지를 보유 합니다.  
  
 `pException`  
 [out] 오류가 있는 경우,이 개체는 예외 정보를 보유 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 구현 자가 오류 정보를 반환 하는 방법을 결정 하는 합니다. 그러나 것만 확인 하는 경우는 예외 개체 반환 된 있음을 확인할 하십시오 오류가 발생 하는 경우이 메서드는 예외 개체를 항상 반환 해야 하므로 오류가 발생 했습니다. 일부 호출자 바꿀 수 있으며는 가능 합니다. 오류 문자열 호출자에 게 확인 하려고 하는 경우에 지정 해야 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)