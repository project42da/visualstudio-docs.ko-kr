---
title: 디버깅 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], tasks
ms.assetid: 5d60e9e8-305e-4a48-829f-b9440fc8af7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 77cc933c49e15786221fd1cd3eb7e242118527a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-tasks"></a>디버깅 작업
프로그램을 디버깅 하려면이 시작 해야 및 디버그 엔진 (DE),에 연결 되어야 합니다. 그렇지 않으면는 DE 이전에 시작된 된 프로그램에 연결 되어야 합니다. 연결 하면는 DE 특정 시작 이벤트를 생성 해야 합니다. 에 대 한 응답 디버그 패키지가 IDE에서 설정 된 중단점을 바인딩할 시도 합니다. 바인딩된 중단점을 적중 하는 프로그램을 중지 하 고 사용자 입력을 대기 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [보안 문제](../../extensibility/debugger/security-issues.md)  
 프로그램을 디버깅 하는 데 필요한 보안 단계를 설명 합니다.  
  
 [프로그램 시작](../../extensibility/debugger/launching-a-program.md)  
 프로그램을 시작 하려면 운영 체제를 호출 하는 DE, 지정 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
 [프로그램에 직접 연결](../../extensibility/debugger/attaching-directly-to-a-program.md)  
 이미 실행 중인 프로세스에서 프로그램을 디버깅 하는 데 사용 하는 프로세스를 설명 합니다.  
  
 [시작 후 시작 이벤트 보내기](../../extensibility/debugger/sending-startup-events-after-a-launch.md)  
 프로그램의 주 진입점에 이며 디버깅에 대 한 준비 될 때까지 DE 프로그램에 연결 되 면 발생 하는 이벤트를 나열 합니다.  
  
 [실행 제어](../../extensibility/debugger/control-of-execution.md)  
 DE 일반적으로 보내는 방법을 진입점 이벤트, 로드 완료 이벤트 또는 상황에 따라 stopping 이벤트를 설명 합니다.  
  
 [중단점 바인딩](../../extensibility/debugger/binding-breakpoints.md)  
 방법, 사용자 중단점을 설정 하는 경우 IDE는 요청을 생성 및 설명 중단점을 만들려고 하면 디버그 세션 라는 메시지를 표시 합니다.  
  
 [식 계산](../../extensibility/debugger/evaluating-expressions.md)  
 식이 계산 되는 경우 및 식이 생성 하는 방법을 설명 합니다.  
  
 [데이터 시각화 및 보기](../../extensibility/debugger/visualizing-and-viewing-data.md)  
 시각화 도우미 형식 및 사용자 지정 뷰어는 식 계산기 (EE)가 지원 되는 방식에 대해 설명 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 기본 디버깅 아키텍처 개념을 설명합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 Visual Studio 디버깅 구성 요소, DE, EE, 기호 처리기 (SH) 등의 개요를 제공 합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 DE는 동시에 코드, 설명서 및 식 평가 컨텍스트 내에서 작동 방법에 대해 설명 합니다. 세 가지 컨텍스트, 위치, 위치, 또는 그와 관련 된 계산의 각각에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)