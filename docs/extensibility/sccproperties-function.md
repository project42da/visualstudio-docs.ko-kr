---
title: SccProperties 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccProperties
helpviewer_keywords:
- SccProperties function
ms.assetid: 1bed38c9-73d2-4474-9717-f9dc26a89cbe
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: efaa2877743fcf69a61a79633108d203442489e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sccproperties-function"></a>SccProperties 함수
이 함수는 파일이 나 프로젝트에 대 한 소스 제어 속성을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SCCRTN SccProperties (  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pvContext  
 [in] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 [in] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에를 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 lpFileName  
 [in] 파일 또는 프로젝트의 정규화 된 경로 이름입니다.  
  
## <a name="return-value"></a>반환 값  
 소스 제어 플러그 인이 함수의 구현은 다음 값 중 하나를 반환:  
  
|값|설명|  
|-----------|-----------------|  
|SCC_OK|속성이는 성공적으로 표시 되었습니다.|  
|SCC_I_RELOADFILE|버전 제어 시스템이 IDE이이 파일을 다시 로드 해야 하므로 파일 속성을 수정 했습니다.|  
|SCC_E_PROJNOTOPEN|지정된 된 프로젝트에 소스 제어에서 열리지 않았습니다.|  
|SCC_E_NOTAUTHORIZED|이 파일 또는 프로젝트의 속성을 보는 사용자 권한이 없습니다.|  
|SCC_E_FILENOTCONTROLLED|지정 된 파일 또는 프로젝트 제어 하지 않는 소스입니다.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|알 수 없거나 일반 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 플러그 인 대화 상자에서 속성을 표시합니다.  
  
 속성 소스 제어 플러그 인 정의 되 고 플러그 인에서 플러그 인에 다를 수 있습니다. 반환 해야 하는 경우 플러그 인을 사용 하면 파일의 소스 제어 속성을 변경 하려면, `SCC_I_RELOAD` 신호를 보내이 파일 또는 프로젝트 다시 로드 해야 하는 IDE.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)