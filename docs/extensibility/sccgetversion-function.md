---
title: "SccGetVersion 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetVersion
helpviewer_keywords: SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2aef7ed21124c2e3555442819461f1989388ab22
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetversion-function"></a>SccGetVersion 함수
이 함수는 소스 제어 플러그 인에서 지 원하는 소스 제어 플러그 인 API의 버전 번호를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 A `LONG` 지원 되는 소스 제어 플러그 인 API의 버전 번호를 포함 하는 데이터 형식:  
  
|WORD|설명|  
|----------|-----------------|  
|HIWORD|주 버전|  
|LOWORD|부 버전|  
  
## <a name="remarks"></a>설명  
 예를 들어 소스 제어 플러그 인 소스 제어 플러그 인 API의 버전 1.3을 지 원하는 경우이 함수 0x0103를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)