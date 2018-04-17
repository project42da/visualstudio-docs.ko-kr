---
title: SccUninitialize 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 41cb6b5cec0e0d9bb4c90cc284009ab7fc693912
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sccuninitialize-function"></a>SccUninitialize 함수
이 함수를 한 할당 이나 열려 있는 연결에 대 한 이전 호출에서 만든 정리는 [SccInitialize](../extensibility/sccinitialize-function.md) 소스 제어 플러그 인을 종료 하는 준비 과정에서 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 만든 소스 제어 플러그 인 컨텍스트 구조에 대 한 포인터는 [SccInitialize](../extensibility/sccinitialize-function.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|정리 완료 되었습니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 플러그 인는 종료 준비에 대 한 상황에 맞는 구조에 대 한 플러그 인에서 할당 메모리를 해제 합니다. 함수는 지정 된 각 인스턴스에 플러그 인에 대해 한 번씩 호출 됩니다. 에 대 한 호출에서 [SccInitialize](../extensibility/sccinitialize-function.md) 이 호출 앞에 옵니다. 프로젝트가 여전히 열 수에 대 한 호출 시 `SccUninitialize`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)