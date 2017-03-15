---
title: "여러 프로젝트 연결 설정의 응용 프로그램 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인, 응용 프로그램 설정"
ms.assetid: 2116d3d0-c46c-4d0a-b482-08a178584f46
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# 여러 프로젝트 연결 설정의 응용 프로그램
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

플러그 인 소스 제어 플러그 인 API 1.2를 사용 하 여 일괄 작업이 여러 프로젝트 또는 여러 개의 연결 컨텍스트 간에 동일한 소스 제어 작업을 실행할 수 있습니다.  일괄 처리 사용 하 여 중복 제거, 각 프로젝트 대화 상자에서 사용자 경험.  
  
 사용자는 소스 제어 플러그 인 API 1.1을 \(예를 들어, 두 개의 웹 프로젝트에서 서로 다른 파일 공유 시스템\)를 사용 하 여 둘 이상의 연결 플러그 인에 속하는 여러 항목을 선택 하 여 아웃 확인 하는 경우 사용자 같은 대화 상자를 반복 해 서 표시 됩니다.  사용자가 클릭 하는 경우에 이러한 상황이 발생의  **모두 적용** IDE의 상태에 대 한 각 연결 컨텍스트를 다시 설정 하기 때문에 대화 상자에서 확인란을 선택 합니다.  
  
## 새 기능 플래그  
 `SccBeginBatch`집합 함수는 `SCC_CAP_BATCH` 일괄 작업이 진행 중임을 나타내는 플래그  
  
## 새 함수  
 일괄 처리 작업을 다음과 같은 새 기능을 지원합니다.  
  
-   [SccBeginBatch](../../extensibility/sccbeginbatch-function.md)  
  
-   [SccEndBatch](../../extensibility/sccendbatch-function.md)  
  
 `SCCBeginBatch` 함수 그룹 소스 제어 작업을 시작 합니다.  `SccEndBatch`그룹을 닫습니다.  그룹은 중첩 될 수 없습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의에서 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)