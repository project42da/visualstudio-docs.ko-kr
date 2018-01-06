---
title: OPTNAMECHANGEPFN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OPTNAMECHANGEPFN
helpviewer_keywords: OPTNAMECHANGEPFN callback function
ms.assetid: 147303f3-c7f1-438a-81b7-db891ea3d076
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2d067d5dd150dd026a2bd29a8933e8d9f72222b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="optnamechangepfn"></a>OPTNAMECHANGEPFN
이것이에 대 한 호출에 지정 된 콜백 함수는 [SccSetOption](../extensibility/sccsetoption-function.md) (옵션을 사용 하 여 `SCC_OPT_NAMECHANGEPFN`) 이름에서 변경한 소스 제어 플러그 인 IDE에 다시 통신 하는 데 사용 됩니다.  
  
## <a name="signature"></a>서명  
  
```cpp  
typedef void (*OPTNAMECHANGEPFN)(  
   LPVOID pvCallerData,  
   LPCSTR pszOldName,  
   LPCSTR pszNewName  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 pvCallerData  
 [in] 사용자가 값에 대 한 이전 호출에 지정 된 된 [SccSetOption](../extensibility/sccsetoption-function.md) (옵션을 사용 하 여 `SCC_OPT_USERDATA`).  
  
 pszOldName  
 [in] 파일의 원래 이름입니다.  
  
 pszNewName  
 [in] 파일 이름은로 바뀌었습니다.  
  
## <a name="return-value"></a>반환 값  
 없음  
  
## <a name="remarks"></a>설명  
 이름을 바꾸면 파일을 소스 제어 작업을 하는 동안 소스 제어 플러그 인에이 콜백을 통해 이름 변경에 대 한 IDE에 알릴 수 있습니다.  
  
 IDE는이 콜백을 지원 하지 않는 경우를 호출 하지는 [SccSetOption](../extensibility/sccsetoption-function.md) 를 지정 합니다. 경우 플러그 인을 지원 하지 않으면이 콜백에서 반환 `SCC_E_OPNOTSUPPORTED` 에서 `SccSetOption` IDE 콜백을 설정 하려고 할 때 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDE에 의해 구현 되는 콜백 함수](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)