---
title: "소스 제어 저장소를 프로젝트 폴더를 비교 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d5bc147592bfc36247c35f23ac2885055d096af3
ms.openlocfilehash: b2ed6955e5ba6fa334cc89a0c2ea8a3d4248f362
ms.lasthandoff: 02/22/2017

---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>소스 제어 저장소를 로컬 프로젝트 폴더의 선택적 비교
소스 제어 플러그 인 API 1.2 로컬 프로젝트 폴더 및 소스 제어 간의 비교 함수를 사용 하 여 수행 됩니다 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) 및 [SccDirDiff](../../extensibility/sccdirdiff-function.md)합니다.  
  
 내에서 **솔루션 탐색기**개별 파일 대신 폴더를 선택 하는 경우는 **버전 비교** 새 바로 가기 메뉴를 호출 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) 및 [SccDirDiff](../../extensibility/sccdirdiff-function.md) 소스 제어 플러그 인에 있습니다.  
  
## <a name="new-capability-flags"></a>새 기능 플래그  
 `SCC_CAP_DIRECTORYDIFF`  
  
 `SCC_CAP_DIRECTORYCHECKOUT`  
  
## <a name="new-functions"></a>새로운 함수  
 [SccDirDiff](../../extensibility/sccdirdiff-function.md)  
  
 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)  
  
 `SccDirQueryInfo` 함수 보다 먼저 호출 됩니다 `SccDirDiff` 소스 제어의 작업 디렉터리 인지 확인할 수 있습니다. `SccDirDiff` 함수는 현재 로컬 디렉터리와 해당 소스 제어 폴더 사이의 차이 표시 합니다. 이 명령은 디렉터리에 변경 내용 목록을 표시 하는 플러그 인 소스 제어를 요청 합니다. 소스 제어 플러그 인 차이 표시 하는 고유한 UI를 제공 합니다.  
  
> [!NOTE]
>  이 함수에 동일한 명령 플래그를 사용 하 여 [SccDiff](../../extensibility/sccdiff-function.md)합니다. 소스 제어 플러그 인 공급자는 디렉터리에 대 한 "빠른 비교" 작업을 지원 하지 않도록 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
