---
title: 어떤&#39;의 새로운 소스 제어 플러그 인 API 버전 1.3 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: abeb2a0a936a5d706e2e3744e9dd0f4e3123bdbf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>어떤&#39;의 새로운 소스 제어 플러그 인 API 버전 1.3
소스 제어 플러그 인 API 버전 1.3에서는 보다 고급 수준의 제어를 제공 다음과 같은 새로운 함수입니다.  
  
## <a name="changes"></a>변경 내용  
 다음 함수는 처음 사용 하는 소스 제어 플러그 인 API 버전 1.3:  
  
|함수|개요|  
|--------------|--------------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|추가 기능 비트를을 보고할 수 있습니다.|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|최신 버전은 버전 제어에 로컬 디스크에 보다 데이터베이스에 포함 된 파일을 검사할 수 있습니다.|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|지정 된 파일에 대 한 이름 변경 (이름 바꾸기, 추가 및 삭제)의 상태을 검사할 수 있습니다.|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|버전 제어 데이터베이스에서 디렉터리 및 파일을 검사할 수 있습니다.|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|지정된 된 목록 파일에 버전 제어 데이터베이스에서 현재 프로젝트에 추가 하는|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|자동 "Get" (사용자 인터페이스 없이 표시) 지정 된 파일의 수행|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|사용자 고유의 옵션에 대 한 액세스를 허용합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)