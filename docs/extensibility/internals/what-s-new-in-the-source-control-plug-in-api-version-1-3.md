---
title: "소스 제어 플러그 인 API 버전 1.3의에서 새로운 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인 API v1.3의 새로운 기능"
  - "새 [Visual Studio SDK], 소스 제어 플러그 인은 무엇입니까"
ms.assetid: 7dfb2227-6e1d-4028-bce9-f8967456a993
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 플러그 인 API 버전 1.3의에서 새로운 기능
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인 API 버전 1.3 고급 제어를 제공 하는 다음과 같은 새 기능을 소개 합니다.  
  
## 변경 내용  
 다음 함수는 소스 제어 플러그 인 API 버전 1.3 새로 추가 되었습니다.  
  
|Function|개요|  
|--------------|--------|  
|[SccGetExtendedCapabilities](../../extensibility/sccgetextendedcapabilities-function.md)|추가 기능 비트를 보고 해야 할 수 있습니다.|  
|[SccEnumChangedFiles](../../extensibility/sccenumchangedfiles-function.md)|최신 버전 보다 버전 제어 데이터베이스 로컬 디스크에 있는 파일의 수 있습니다.|  
|[SccQueryChanges](../../extensibility/sccquerychanges-function.md)|지정 된 파일에 대 한 이름 변경 \(예: 이름 바꾸기, 추가 및 삭제\)의 상태를 검사할 수 있습니다.|  
|[SccPopulateDirList](../../extensibility/sccpopulatedirlist-function.md)|버전 제어 데이터베이스의 디렉터리와 파일 검사를 허용합니다.|  
|[SccAddFilesFromSCC](../../extensibility/sccaddfilesfromscc-function.md)|파일의 지정 된 목록에서 버전 제어 데이터베이스를 현재 프로젝트에 추가|  
|[SccBackgroundGet](../../extensibility/sccbackgroundget-function.md)|자동 "Get" 지정 된 파일의 사용자 인터페이스는 없습니다 \(그림 참조\)를 수행 합니다.|  
|[SccGetUserOption](../../extensibility/sccgetuseroption-function.md)|사용자 고유의 옵션에 액세스할 수 있습니다.|  
  
## 참고 항목  
 [시작](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)   
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)