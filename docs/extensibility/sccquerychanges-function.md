---
title: SccQueryChanges 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d887c0cea989fa6a955edc2f39b9667e7421093d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sccquerychanges-function"></a>SccQueryChanges 함수
이 함수는 콜백 함수를 통해 각 파일에 대 한 이름 변경에 대 한 정보를 제공 하는 파일의 지정 된 목록을 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nFiles  
 [in] 파일 수가 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 [in] 에 대 한 정보를 얻을 수 파일 이름 배열입니다.  
  
 pfnCallback  
 [in] 콜백 함수를 목록에서 각 파일 이름에 대 한 호출 (참조 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) 세부 정보에 대 한).  
  
 pvCallerData  
 [in] 콜백 함수에 전달 되는 값을 변경 되지 않습니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|쿼리 프로세스가 완료 되었습니다.|  
|SCC_E_PROJNOTOPEN|프로젝트에 소스 제어에서 열리지 않았습니다.|  
|SCC_E_ACCESSFAILURE|소스 제어 시스템에 네트워크 또는 경합 문제 때문에 액세스 하는 문제가 발생 했습니다.|  
|SCC_E_NONSPECIFICERROR|지정 되지 않은 또는 일반 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 네임 스페이스는 변경에 대 한 쿼리 중인: 구체적으로, 이름 바꾸기, 추가 및 파일 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [오류 코드](../extensibility/error-codes.md)