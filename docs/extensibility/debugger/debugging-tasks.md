---
title: "디버깅 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 작업"
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# 디버깅 작업
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로그램을 디버깅 하는 시작 되어야 하 고 디버그 엔진 \(DE\)을 부착 해야 하거나 \[DE은 이전에 실행된 프로그램에 연결 해야 합니다.  연결 된 후에 DE 특정 시작 이벤트를 생성 해야 합니다.  이에 따라 디버그 패키지 IDE에서 설정할 중단점을 바인딩하려고 시도 합니다.  프로그램이 바인딩된 중단점에 도달 하면 중지 하 고 사용자 입력을 기다립니다.  
  
## 단원 내용  
 [보안 문제](../../extensibility/debugger/security-issues.md)  
 프로그램을 디버깅 하는 데 필요한 보안 단계에 설명 합니다.  
  
 [프로그램 실행](../../extensibility/debugger/launching-a-program.md)  
 프로그램을 실행 하는 운영 체제를 호출 하는 DE를 지정 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [프로그램에 직접 연결](../../extensibility/debugger/attaching-directly-to-a-program.md)  
 이미 실행 중인 프로세스에서 프로그램을 디버깅 하는 프로세스를 설명 합니다.  
  
 [시작 된 후 시작 이벤트를 전송합니다.](../../extensibility/debugger/sending-startup-events-after-a-launch.md)  
 프로그램의 주 진입점에 디버깅 준비 때까지 프로그램에는 DE를 연결 하면 수행 하는 이벤트를 나열 합니다.  
  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)  
 DE은 일반적으로 진입점 이벤트, 로드 완료 이벤트, 또는 상황에 따라 중지 이벤트를 보내는 방법을 설명 합니다.  
  
 [바인딩 중단점](../../extensibility/debugger/binding-breakpoints.md)  
 방법, 사용자가 중단점을 설정 하는 경우 IDE는 요청을 공식화 및 디버그 세션에서 중단점을 만들려면 메시지를 표시에 대해 설명 합니다.  
  
 [식 계산](../../extensibility/debugger/evaluating-expressions.md)  
 식을 만드는 방법, 식을 계산할 때 일어나는 설명 합니다.  
  
 [시각화 및 데이터 보기](../../extensibility/debugger/visualizing-and-viewing-data.md)  
 형식 시각화 및 사용자 지정 뷰어는 식 계산기 \(EE\) 지원 됩니다 설명 합니다.  
  
## 관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 디버깅의 주요 아키텍처 개념에 설명 합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 DE, EE, 기호 처리기 \(SH\) 등 Visual Studio 디버깅 구성의 개요를 제공 합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 DE에서 동시에 코드, 설명서, 및 식 평가 컨텍스트 내에서 작동 하는 방식을 설명 합니다.  각각의 세 가지 컨텍스트, 위치, 위치, 또는 평가에 관련에 대해 설명합니다.  
  
## 참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)