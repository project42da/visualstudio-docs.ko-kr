---
title: "디버거 개념 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK]"
ms.assetid: 2d371d38-f1a0-4a9a-8ea3-100e8c0149b7
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 디버거 개념
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio 디버그 패키지를 작성 하려면 패키지를 디자인 하는 데 사용 되는 아키텍처 개념을 잘 알고 있어야 합니다.  
  
## 단원 내용  
 [디버그 세션](../../extensibility/debugger/debug-session.md)  
 디버깅 아키텍처에서 세션의 역할에 설명 합니다.  
  
 [서버](../../extensibility/debugger/servers-visual-studio-sdk.md)  
 정의 어떤 서버 아키텍처, abstract 및 물리적 용어로 디버깅의 관점에서입니다.  
  
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)  
 무엇 인지를 정의 아키텍처 디버깅의 포트 공급자입니다.  
  
 [포트](../../extensibility/debugger/ports.md)  
 정의 아키텍처 디버깅의 어떤 포트입니다.  
  
 [프로세스](../../extensibility/debugger/processes.md)  
 정의 아키텍처 디버깅의 어떤 프로세스입니다.  
  
 [프로그램 노드](../../extensibility/debugger/program-nodes.md)  
 프로그램의 관점에서 아키텍처에서 실행 되는 프로세스와을 식별할 수 있습니다 포함 한 디버깅 노드를 정의 합니다.  
  
 [Programs](../../extensibility/debugger/programs.md)  
 프로그램 디버깅 아키텍처 측면에서 정의 합니다.  
  
 [스레드](../../extensibility/debugger/threads.md)  
 스레드 디버깅 아키텍처의 특성을 정의 합니다.  
  
 [스택 프레임](../../extensibility/debugger/stack-frames.md)  
 스택 프레임은 디버깅 아키텍처를 정의 합니다.  스택 프레임을 스레드 실행 컨텍스트를 제공 하는 스택 추상화입니다.  
  
 [모듈](../../extensibility/debugger/modules.md)  
 관점에서 아키텍처의 물리적 컨테이너 코드 실행 파일 또는 DLL의 디버깅 모듈을 정의 합니다.  
  
 [중단점](../../extensibility/debugger/breakpoints-visual-studio-sdk.md)  
 세 가지 종류의 중단점을 정의\-보류, 바인딩, 오류\-의 관점에서 아키텍처를 디버깅 합니다.  
  
## 관련 단원  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 디버그 엔진 \(DE\) 동시에 코드, 설명서, 및 식 평가 컨텍스트 내에서 작동 하는 방식을 설명 합니다.  각각의 세 가지 컨텍스트, 위치, 위치, 또는 평가에 관련에 대해 설명합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 디버그 엔진 \(DE\), 식 계산기 \(EE\) 기호 처리기 \(SH\) 등 Visual Studio 디버깅 구성 요소의 개요를 제공 합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 고 식을 계산 하는 것과 같은 다양 한 디버깅 작업에 대 한 링크가 포함 되어 있습니다.