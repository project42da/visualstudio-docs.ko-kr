---
title: IDebugCustomViewer::DisplayValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCustomViewer::DisplayValue
helpviewer_keywords: IDebugCustomViewer::DisplayValue
ms.assetid: 7a538248-5ced-450e-97cd-13fabe35fb1c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 701c5e33273dc6d00156e554e1abaa9a003568eb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcustomviewerdisplayvalue"></a>IDebugCustomViewer::DisplayValue
이 메서드는 지정 된 값을 표시 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DisplayValue(  
   HWND             hwnd,  
   DWORD            dwID,  
   IUnknown *       pHostServices,  
   IDebugProperty3* pDebugProperty);  
);  
```  
  
```csharp  
int DisplayValue(  
   IntPtr          hwnd,   
   uint            dwID,   
   object          pHostServices,   
   IDebugProperty3 pDebugProperty  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hwnd`  
 [in] 부모 창  
  
 `dwID`  
 [in] 둘 이상의 유형을 지 원하는 사용자 지정 뷰어에 대 한 ID입니다.  
  
 `pHostServices`  
 [in] 예약 되어 있습니다. 항상 설정 null로 합니다.  
  
 `pDebugProperty`  
 [in] 표시할 값을 검색 하는 데 사용할 수 있는 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 표시는 "모달" 점에서이 메서드는 필요한 창을 만들, 값을 표시, 입력을 대기 하 고 호출자에 게 반환 하기 전에 모든 창을 닫습니다. 즉, 메서드 창 소멸에 사용자 입력을 대기 하는 상태로 출력에 대 한 창을 만들지 못하도록 속성의 값을 표시 하는의 모든 측면을 처리 해야 합니다.  
  
 에 값을 변경 지원 하기 위해는 주어진 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) 개체를 사용할 수 있습니다는 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md) 메서드-값을 문자열로 표현할 수 있는 경우. 사용자 지정 인터페이스를 만들 수는 그렇지 않은 경우-이 구현 하는 식 계산기에만 적용 `DisplayValue` 메서드-구현 하는 동일한 개체에는 `IDebugProperty3` 인터페이스입니다. 이 사용자 지정 인터페이스 복잡성 또는 임의 크기의 데이터를 변경 하기 위한 메서드를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [SetValueAsStringWithError](../../../extensibility/debugger/reference/idebugproperty3-setvalueasstringwitherror.md)