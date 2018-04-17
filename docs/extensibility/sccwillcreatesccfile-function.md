---
title: SccWillCreateSccFile 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccWillCreateSccFile
helpviewer_keywords:
- SccWillCreateSccFile function
ms.assetid: 0d7542f0-4351-41b3-b24c-960ab99c05a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: af6da09badf0ffea4846d35fe00b4ca146243d64
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="sccwillcreatesccfile-function"></a>SccWillCreateSccFile 함수
이 함수는 소스 제어 플러그 인은 MSSCCPRJ 만들기를 지원 하는지 여부를 결정 합니다. 지정 된 파일의 파일을 SCC입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccWillCreateSccFile(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPBOOL  pbSccFiles  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nFiles  
 [in] 파일 이름에 포함 된 수의 `lpFileNames` 배열 길이 뿐만 아니라는 `pbSccFiles` 배열입니다.  
  
 lpFileNames  
 [in] 확인 하려면 정규화 된 파일 이름 배열을 (배열 호출자가 할당 해야 합니다).  
  
 pbSccFiles  
 [out에서] 결과 저장할 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|명령 실행 성공|  
|SCC_E_INVALIDFILEPATH|배열에 있는 경로 중 하나가 올바르지 않습니다.|  
|SCC_E_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는 소스 제어 플러그 인은 MSSCCPRJ에서 지원 되는 확인 하는 파일의 목록을 사용 하 여 호출 됩니다. 각 (에 대 한 자세한 내용은 MSSCCPRJ 지정 된 파일에 대 한 SCC 파일. SCC 파일 참조 [MSSCCPRJ 합니다. SCC 파일](../extensibility/mssccprj-scc-file.md)). 소스 제어 플러그 인 MSSCCPRJ 만드는 기능이 있는지를 선언할 수 있습니다. SCC 파일 선언 하 여 `SCC_CAP_SCCFILE` 초기화 하는 동안 합니다. 플러그 인 반환 `TRUE` 또는 `FALSE` 파일당는 `pbSccFiles` MSSCCPRJ 가질 지정 된 파일 중를 나타내는 배열입니다. 소스 코드 제어를 지원 합니다. 플러그 인 함수에서 성공 코드를 반환 하면 반환 배열에 있는 값을 적용할 수 있습니다. 실패 한 경우, 배열의 무시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [MSSCCPRJ.SCC 파일](../extensibility/mssccprj-scc-file.md)