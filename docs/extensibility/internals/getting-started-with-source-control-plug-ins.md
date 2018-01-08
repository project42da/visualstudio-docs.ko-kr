---
title: "소스 제어 플러그 인 시작 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, getting started
- getting started, source control plug-ins
ms.assetid: 46ac1f9f-4ecc-4a72-88d3-4c7e1647e1cb
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 197cc0f0997e80d6cae277c4b19c5bbc82dce805
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-source-control-plug-ins"></a>소스 제어 플러그 인 시작
소스 제어 플러그 인을 만들려면 소스 제어 플러그 인 API에 정의 된 함수를 구현 하는 DLL 만들어야 DLL을 등록 한 다음 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 코드 버전 제어에서 사용 하기 위해 사용할 수 있도록 합니다.  
  
 세 가지 버전 (버전 1.1, 1.2 및 1.3) 소스 제어 플러그 인 API의 소스 제어 플러그 인 수 있습니다. 여기에 설명 되어 소스 제어 플러그 인은 버전 1.3입니다. 소스 제어 플러그 인을 완벽 하 게 호환 되도록 설계 되었습니다 버전 1.1 및 1.2를 지원 합니다. [소스 제어 플러그 인 API 버전 1.3의 새로운](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md) 섹션 소스 제어 플러그 인 API의 최신 버전에서 지원 되는 새 기능에 자세히 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 소스 제어 플러그 인 설치](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)  
 소스 제어 DLL에에서 연결 하는 데 필요한 레지스트리 항목을 확인 하는 방법에 설명 합니다.  
  
 [소스 제어 플러그 인 API 버전 1.3의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-3.md)  
 버전 1.3에서에서 소스 제어 플러그 인 API에 대 한 변경의 간략 한 개요를 제공 합니다.  
  
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)  
 소스 제어 플러그 인 API 버전 1.2에 대 한 변경의 간략 한 개요를 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)  
 소스 제어 플러그 인 API에 있는 모든 요소의 전체 목록을 제공합니다.  
  
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)  
 소스 제어 플러그 인 SDK을 정의 하 고 포함 된 리소스에 설명 합니다.