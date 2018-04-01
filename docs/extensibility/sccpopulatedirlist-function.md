---
title: SccPopulateDirList 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 4be6e63df26d3c4a9b6539276aa97f69e349b83c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList 함수
이 함수는 디렉터리와 선택적으로 파일을 검사 하는 디렉터리 목록을 제공 하는 소스 제어에 저장 됩니다 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccPopulateDirList(  
   LPVOID        pContext,  
   LONG          nDirs,  
   LPCSTR*       lpDirPaths,  
   POPDIRLISTFUNCpfnPopulate,  
   LPVOID        pvCallerData,  
   LONG          fOptions  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nDirs  
 [in] 디렉터리 경로 수는 `lpDirPaths` 배열입니다.  
  
 lpDirPaths  
 [in] 검사할 디렉터리 경로 배열입니다.  
  
 pfnPopulate  
 [in] 콜백 함수 및 (선택 사항) 각 디렉터리 경로에 파일 이름에 대 한 호출을 `lpDirPaths` (참조 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md) 세부 정보에 대 한).  
  
 pvCallerData  
 [in] 콜백 함수에 전달 될 값을 변경 되지 않습니다.  
  
 fOptions  
 [in] 디렉터리를 처리 하는 방법을 제어 하는 값의 조합 (의 "PopulateDirList 플래그" 섹션을 참조 [에서 특정 명령을 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md) 가능한 값에 대 한).  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|작업을 완료 했습니다.|  
|SCC_E_UNKNOWNERROR|오류가 발생했습니다.|  
  
## <a name="remarks"></a>설명  
 만 해당 (선택 사항) 파일 이름 및 디렉터리 소스 제어 리포지토리에 실제로 있는 콜백 함수에 전달 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [오류 코드](../extensibility/error-codes.md)