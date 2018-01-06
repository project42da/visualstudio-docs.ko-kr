---
title: POPLISTFUNC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: POPDIRLISTFUNC
helpviewer_keywords: POPLISTFUNC callback function
ms.assetid: b2199fd5-d707-4628-92dd-e2a01e2f507a
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dc15af65c6541df5ef77a3bdc85ee0e59fa20991
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="poplistfunc"></a>POPLISTFUNC
이 콜백은에 제공 되는 [SccPopulateList](../extensibility/sccpopulatelist-function.md) IDE에서 소스 제어 플러그 인 파일 또는 디렉터리의 목록을 업데이트 하는 데 사용 되 고 (또한에 제공 되는 `SccPopulateList` 함수).  
  
 사용자가 선택 하는 경우는 **가져오기** 사용자 얻을 수 있는 모든 파일의 목록 상자를 표시 하는 IDE IDE에 명령 합니다. 안타깝게도, IDE 알지 못하므로 사용자 표시 될 수 있습니다; 모든 파일의 정확한 목록 만 플러그 인이 목록을 있습니다. 다른 사용자가 소스 코드 제어 프로젝트에 파일을 추가, 이러한 파일의 목록에 표시 되어야 하지만 IDE에 대해 알 수 없습니다. IDE는 사용자를 가져올 수 것으로 확인 하는 파일 목록을 작성 합니다. 호출 사용자에 게이 목록을 표시 하기 전에 [SccPopulateList](../extensibility/sccpopulatelist-function.md) `,` 소스 제어 플러그 인을 제공 하 추가 하 고 목록에서 파일을 삭제 합니다.  
  
## <a name="signature"></a>서명  
 소스 제어 플러그 인 다음과 같은 프로토타입으로 IDE 구현 함수를 호출 하 여 목록을 수정 합니다.  
  
```cpp  
typedef BOOL (*POPLISTFUNC) (  
   LPVOID pvCallerData,  
   BOOL fAddRemove,  
   LONG nStatus,  
   LPSTR lpFileName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 pvCallerData  
 `pvCallerData` (IDE) 호출자가 매개 변수가 전달 된 [SccPopulateList](../extensibility/sccpopulatelist-function.md)합니다. 소스 제어 플러그 인이 매개 변수 내용에 대해 아무 것도 가정해 야 합니다.  
  
 fAddRemove  
 경우 `TRUE`, `lpFileName` 는 파일 목록에 추가 해야 하는 파일입니다. 경우 `FALSE`, `lpFileName` 는 파일 목록에서 삭제 해야 하는 파일입니다.  
  
 nStatus  
 상태 `lpFileName` (의 조합을 `SCC_STATUS` 비트; 참조 [파일 상태 코드](../extensibility/file-status-code-enumerator.md) 대 한 자세한 내용은).  
  
 lpFileName  
 디렉터리의 전체 경로 파일 이름 추가 하거나 목록에서 삭제 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|값|설명|  
|-----------|-----------------|  
|`TRUE`|플러그 인 계속할 수이 함수를 호출 합니다.|  
|`FALSE`|IDE 면 (예: 메모리 상태를 벗어난)에 문제가 발생이 했습니다. 플러그 인 작업을 중지 해야 합니다.|  
  
## <a name="remarks"></a>설명  
 소스 제어 플러그 인에 추가 하거나 파일 목록에서 삭제 하는 각 파일에 대해 전달이 함수 호출의 `lpFileName`합니다. `fAddRemove` 플래그 목록에 추가할 새 파일 또는 삭제 하는 오래 된 파일을 나타냅니다. `nStatus` 매개 변수는 파일의 상태를 제공 합니다. 반환 하는 플러그 인 SCC 추가 및 파일 삭제 완료 되 면는 [SccPopulateList](../extensibility/sccpopulatelist-function.md) 호출 합니다.  
  
> [!NOTE]
>  `SCC_CAP_POPULATELIST` 기능 비트는 Visual Studio에 필요 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)   
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)