---
title: "열거자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0b9f71c83d70dc6daca7a3906b784d6babf8dea7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="enumerators"></a>열거자
이 섹션에는 소스 제어 플러그 인에 대해 알고 있어야 하는 소스 제어 플러그 인 API의 열거자 데이터 형식을 나열 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [명령 코드](../extensibility/command-code-enumerator.md)  
 에 대 한 옵션을 열거는 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) 및 [SccPopulateList](../extensibility/sccpopulatelist-function.md) 함수입니다.  
  
 [메시지](../extensibility/message-enumerator.md)  
 인쇄 콜백 함수에 사용 되는 플래그 열거 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)합니다.  
  
 [파일 상태 코드](../extensibility/file-status-code-enumerator.md)  
 소스 제어에서 파일의 상태를 지정 하는 명명 된 상수 값을 포함 합니다.  
  
 [디렉터리 상태 코드](../extensibility/directory-status-code-enumerator.md)  
 소스 제어에서 디렉터리의 상태를 지정 하는 명명 된 상수 값을 포함 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [소스 제어 플러그 인 만들기](../extensibility/internals/creating-a-source-control-plug-in.md)  
 소스 제어 플러그 인 SDK을 정의 하 고 포함 된 리소스에 설명 합니다.  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 지정 된 명령에 대 한 고급 옵션에 대 한 사용자 메시지를 표시합니다.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 현재 상태에 대 한 파일 목록에 있는지 검사합니다. 또한 사용 하 여는 `pfnPopulate` 함수를 파일에 대 한 조건을 일치 하지 않는 경우 호출자에 게는 `nCommand`합니다.  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 사용 되는 콜백 함수에 설명 [SccOpenProject](../extensibility/sccopenproject-function.md) IDE를 통해 플러그 인 소스 제어에서 메시지를 표시 합니다.  
  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)  
 소스 제어 플러그 인 API에 있는 모든 요소의 전체 목록을 제공합니다.