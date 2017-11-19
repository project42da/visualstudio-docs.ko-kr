---
title: "SccBeginBatch 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccBeginBatch
helpviewer_keywords: SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0e18eedcab133329f10064ef3dd6486beb2e1596
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch 함수
이 함수는 소스 제어 작업의 일괄 처리 순서를 시작합니다. [SccEndBatch](../extensibility/sccendbatch-function.md) 일괄 처리를 종료 하려면 호출 됩니다. 이러한 일괄 처리를 중첩할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>매개 변수  
 없음  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|성공적으로 시작 된 작업의 일괄 처리입니다.|  
|SCC_E_UNKNOWNERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 일괄 처리는 여러 프로젝트 또는 여러 컨텍스트 간에 동일한 작업을 실행 하는 데 사용 됩니다. 일괄 처리 된 작업 중 사용자 환경에서 중복 프로젝트 대화 상자를 제거 하기 위해 일괄 처리를 사용할 수 있습니다. `SccBeginBatch` 함수 및 [SccEndBatch](../extensibility/sccendbatch-function.md) 작업의 시작과 끝을 나타내는 데 함수 쌍으로 사용 됩니다. 중첩할 수 없습니다. `SccBeginBatch`일괄 처리 작업이 진행 중임을 나타내는 플래그를 설정 합니다.  
  
 일괄 처리 작업을 적용 하는 동안 소스 제어 플러그 인 사용자에 게 최대 한다면 어떤 호환성에 대 한 하나의 대화 상자를 표시 하 고 모든 후속 작업에서 해당 대화 상자에서 응답을 적용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)