---
title: POPDIRLISTFUNC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8503afb26ec8dc244db39dff5bddcc6d3b733896
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
이것은에 지정 된 콜백 함수는 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) (선택 사항) 파일 이름 및 디렉터리를 확인 하는 소스 제어의 컬렉션을 업데이트 하는 함수입니다.  
  
 `POPDIRLISTFUNC` 콜백 디렉터리와 파일 이름에 대해서만 호출 해야 (에 지정 된 목록에는 `SccPopulateDirList` 함수)는 실제로 소스 제어입니다.  
  
## <a name="signature"></a>서명  
  
```cpp  
typedef BOOL (*POPDIRLISTFUNC)(  
   LPVOID pvCallerData,  
   BOOL bFolder,  
   LPCSTR lpDirectoryOrFileName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 pvCallerData  
 [in] 사용자가 값을 가리키는 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)합니다.  
  
 bFolder  
 [in] `TRUE` 경우에서 이름을 `lpDirectoryOrFileName` 디렉터리; 그렇지 않으면 이름은 파일 이름입니다.  
  
 lpDirectoryOrFileName  
 [in] 소스 코드 제어 아래에 있는 디렉터리 또는 파일 이름에 전체 로컬 경로입니다.  
  
## <a name="return-value"></a>반환 값  
 IDE에서 적절 한 오류 코드를 반환합니다.  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|계속 처리 합니다.|  
|SCC_I_OPERATIONCANCELED|처리를 중지 합니다.|  
|SCC_E_xxx|모든 적절 한 소스 제어 오류 처리를 중지 해야 합니다.|  
  
## <a name="remarks"></a>설명  
 경우는 `fOptions` 의 매개 변수는 `SccPopulateDirList` 함수에 포함 되어는 `SCC_PDL_INCLUDEFILES` 플래그를 디렉터리 이름 뿐만 아니라 파일 이름에 가능한 목록 포함 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)   
 [오류 코드](../extensibility/error-codes.md)