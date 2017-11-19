---
title: "기능 &#39;의 새로운 소스 제어 플러그 인 API 버전 1.3 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, what's new in API v1.3
- what's new [Visual Studio SDK], source control plug-ins
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd0c23258034fb99f5e2e4e0c86ca9e61c3d68ab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="what39s-new-in-the-source-control-plug-in-api-version-13"></a>기능 &#39; 소스 제어 플러그 인 API 버전 1.3의 새로운 s
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