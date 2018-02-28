---
title: IDebugBinder3::GetEEService | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugBinder3::GetEEService
helpviewer_keywords:
- IDebugBinder3::GetEEService method
ms.assetid: eb07aa40-8cd9-4a52-a4c7-4affd2307a01
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fbebf4a70c8e22fda39e9b20e56ca6192f81a00e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbinder3geteeservice"></a>IDebugBinder3::GetEEService
이 메서드는 요청 된 서비스를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetEEService(  
   [in] GUID        vendor,  
   [in] GUID        language,  
   [in] GUID        iid,  
   [out] IUnknown** ppService  
);  
```  
  
```csharp  
Int GetEEService(  
   Guid       vendor,  
   Guid       language,  
   Guid       iid,  
   out object ppService  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `vendor`  
 [in] `GUID` (null 값이 허용 가능한) 공급 업체의 합니다.  
  
 `language`  
 [in] `GUID` (null 값이 허용) 하는 언어의 합니다.  
  
 `iid`  
 [in] `IID` 가져오기 위해 서비스입니다.  
  
 `ppService`  
 [out] 요청된 된 서비스를 사용 하는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 전달 된 `IID` 에 대 한는 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md) 인터페이스 (`IID_IEEVisualizerServiceProvider`) 형식 시각화 도우미 서비스를 사용할 수 있는지를 합니다. 식 계산기를 얻을 수 있는 경우는 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) 인터페이스 형식 시각화 도우미를 지원 하도록 합니다. 참조 [Visualizing 및 데이터 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md) 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [데이터 시각화 및 보기](../../../extensibility/debugger/visualizing-and-viewing-data.md)