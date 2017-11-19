---
title: "SccEnumChangedFiles 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccEnumChangedFiles
helpviewer_keywords: SccEnumChangedFiles function
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ad62f14ea658e4af6e22d4beef410e6d9cf02df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sccenumchangedfiles-function"></a>SccEnumChangedFiles 함수
로컬 파일의 목록에 지정 된 경우이 함수는 파일은 소스 코드 제어 데이터베이스에서 해당 버전의 다른 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccEnumChangedFiles(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LONG    cFiles,  
   LPCSTR* lpFileNames,  
   LONG*   plIsFileDifferent  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pContext  
 [in] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 cFiles  
 [in] 파일 이름에 지정 된 수의 `lpFileNames` 배열입니다. 또한의 크기를 지정 `plIsFileDifferent` 배열입니다.  
  
 lpFileNames  
 [in] 확인 하려면 로컬 파일 이름 배열입니다.  
  
 plIsFileDifferent  
 [out에서] 각 파일의 차이 상태를 나타내는 값의 배열입니다 (배열에 적어도 있어야 `cFiles` 항목). Nonzero는 파일이 다른 임을 의미 합니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|작업이 완료 되었습니다.|  
|SCC_UNSPECIFIEDERROR|일반 오류입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)