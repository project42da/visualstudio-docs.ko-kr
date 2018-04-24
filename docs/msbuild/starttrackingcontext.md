---
title: StartTrackingContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- StartTrackingContext
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContext
ms.assetid: 720cd295-38e7-4974-86db-b8106b1207ba
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 35fef17924d0ef4bc431742258d12b03667a25bc
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="starttrackingcontext"></a>StartTrackingContext
추적 컨텍스트를 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT WINAPI StartTrackingContext(LPCTSTR intermediateDirectory, LPCTSTR taskName);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `intermediateDirectory`  
 추적 로그를 저장할 디렉터리입니다.  
  
 [in] `taskName`  
 추적 컨텍스트를 식별합니다. 이 이름은 로그 파일 이름을 만드는 데 사용됩니다.  
  
## <a name="return-value"></a>반환 값  
 추적 컨텍스트가 만들어진 경우 **SUCCEEDED** 비트가 설정된 **HRESULT**를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** FileTracker.h