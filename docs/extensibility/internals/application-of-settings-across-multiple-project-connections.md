---
title: "여러 프로젝트 연결을 통해 설정의 적용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, application of settings
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a5d66bf7670d5ba9b6423461bdb5e5482819592f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="application-of-settings-across-multiple-project-connections"></a>여러 프로젝트 연결을 통해 설정의 적용
소스 제어 플러그 인 여러 프로젝트 또는 여러 연결 컨텍스트 같은 소스 제어 작업을 실행 하려면 일괄 처리 작업을 사용할 수 소스 제어 플러그 인 API 1.2를 사용 하 여 작성. 일괄 처리에서 중복 제거, 프로젝트 대화 상자에서 사용자 환경 데 사용할 수 있습니다.  
  
 소스 제어 플러그 인 API 1.1 (예를 들어 두 개의 웹 프로젝트에 다른 파일 공유 컴퓨터)를 사용 하 여 만든 소스 제어 플러그 인에서 둘 이상의 연결에 속하는 여러 항목을 선택 하 고 체크 아웃 하는 사용자, 사용자에 게 동일한 대화 상자 표시 반복 합니다. 사용자가 클릭 하는 경우에 이런는 **모든 항목에 적용** IDE 각 연결 컨텍스트에 대 한 해당 상태를 다시 설정 하기 때문에 대화 상자에서 상자를 선택 합니다.  
  
## <a name="new-capability-flag"></a>새 기능 플래그  
 `SccBeginBatch`집합 함수는 `SCC_CAP_BATCH` 를 일괄 처리 작업이 진행 중임을 나타내는 플래그  
  
## <a name="new-functions"></a>새로운 함수  
 다음과 같은 새 함수에는 일괄 처리 작업을 지원합니다.  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` 함수 그룹의 소스 제어 작업을 시작 합니다. `SccEndBatch`그룹을 닫습니다. 그룹을 중첩할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)