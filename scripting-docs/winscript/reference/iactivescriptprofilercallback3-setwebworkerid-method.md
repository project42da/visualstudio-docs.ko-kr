---
title: "Iactivescriptprofilercallback3:: Setwebworkerid 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 47744746-1276-441e-ab60-2a78f550e8e2
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 426767b8d4d23964d6bfaa7102ee53b550e7ab9b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercallback3setwebworkerid-method"></a>IActiveScriptProfilerCallback3::SetWebWorkerId 메서드
프로 파일링이 세션에 사용할 작업자 ID에 대 한 프로파일러를 알립니다. 함수는 페이지의 컨텍스트를 실행 하는 경우이 메서드는 호출 되지 않습니다. 값 `webWorkerId` 1부터 시작 하는 모든 작업자에 대해 1 씩 증가 합니다. 세션이 안정 되 고 작업 자가 생성 된 순서에만 해당 하는 ID 값이를 사용 하는 것이 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetWebWorkerId([in] DWORD webWorkerId);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `webWorkerId`  
 웹 작업자 id입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드의 반환 값은 스크립팅 엔진에서 무시 됩니다.