---
title: IApplicationDebugger::CreateInstanceAtDebugger | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IApplicationDebugger.CreateInstanceAtDebugger
apilocation: scrobj.dll
helpviewer_keywords: IApplicationDebugger::CreateInstanceAtDebugger
ms.assetid: 6763afac-c86a-4e88-9580-77108fb242fb
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6495c2d8782d1128700bdfb6d4081b80ffae878
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iapplicationdebuggercreateinstanceatdebugger"></a>IApplicationDebugger::CreateInstanceAtDebugger
디버거 프로세스에서 코드에 의해 개체 만들기를 허용 하 고 디버거 프로세스 아웃 즉 합니다.  
  
> [!IMPORTANT]
>  신뢰할 수 없는 코드가 신뢰할 수 있는 디버거 스레드에 임의의 개체를 만들 수 있기 때문에이 메서드를 구현 되어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateInstanceAtDebugger(  
   REFCLSID    rclsid,  
   IUnknown*   pUnkOuter,  
   DWORD       dwClsContext,  
   REFIID      riid,  
   IUnknown**  ppvObject  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 [in] 클래스 식별자 (CLSID)를 만들 개체입니다.  
  
 `pUnkOuter`  
 [in] 경우 `NULL`, 개체가 집계의 일환으로 만들지 않습니다. 그렇지 않으면 `pUnkOuter` 집계 개체에 대 한 포인터 `IUnknown` 인터페이스 (제어용 `IUnknown`).  
  
 `dwClsContext`  
 [in] 실행 코드를 실행 컨텍스트입니다. 열거형에서 값을 가져옵니다 `CLSCTX`합니다.  
  
 `riid`  
 [in] 개체와 통신 하는 데 사용 되는 인터페이스 식별자입니다.  
  
 `ppvObject`  
 [out] 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소 `riid`합니다. 성공적으로 반환 되 면 *`ppvObject` 요청 된 인터페이스 포인터를 포함 합니다. 실패 시 \* `ppvObject` 포함 `NULL`합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드 `CoCreateInstance`합니다.  
  
 메서드가 현재 구현 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IApplicationDebugger 인터페이스](../../winscript/reference/iapplicationdebugger-interface.md)