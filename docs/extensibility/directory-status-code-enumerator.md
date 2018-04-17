---
title: 디렉터리 상태 코드 열거자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 539dc4c2ea7b33ce88465f1d8f6651dc890c8e45
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="directory-status-code-enumerator"></a>디렉터리 상태 코드 열거자
`SccDirStatus` 소스 제어 시스템의 디렉터리의 상태를 지정 하는 명명 된 상수 값을 포함 하는 열거자입니다. 이 열거형은에서 사용 된 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)합니다. 이 옵션은 소스 제어 플러그 인 API의 버전 1.2에서에서 도입 되었습니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>멤버  
 SCC_DIRSTATUS_INVALID  
 상태를 가져올 수 없습니다. 것에 의존 하지 마십시오.  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 디렉터리를 소스 제어에 없습니다.  
  
 SCC_DIRSTATUS_CONTROLLED  
 디렉터리는 소스 제어입니다.  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 이 디렉터리에 여러 프로젝트 비어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)