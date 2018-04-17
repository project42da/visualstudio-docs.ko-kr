---
title: 디버거 개념 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK]
ms.assetid: 2d371d38-f1a0-4a9a-8ea3-100e8c0149b7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c157e570179da1e1f16ed5c2c12af63b95b0b61d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debugger-concepts"></a>디버거 개념
Visual Studio 디버그 패키지를 빌드하려면 패키지 디자인에 사용 되는 아키텍처 개념을 숙지 해야 해야 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [디버그 세션](../../extensibility/debugger/debug-session.md)  
 디버깅 아키텍처에서 세션의 역할에 설명 합니다.  
  
 [서버](../../extensibility/debugger/servers-visual-studio-sdk.md)  
 정의 어떤 서버는 용어로 추상 및 물리적 아키텍처를 디버깅 하는 데 기준으로 합니다.  
  
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)  
 대상을 정의 포트 공급자는 디버깅 아키텍처를 기준으로 합니다.  
  
 [포트](../../extensibility/debugger/ports.md)  
 정의 어떤 포트는 디버깅 아키텍처를 기준으로 합니다.  
  
 [프로세스](../../extensibility/debugger/processes.md)  
 정의 프로세스는 디버깅 아키텍처를 기준으로 합니다.  
  
 [프로그램 노드](../../extensibility/debugger/program-nodes.md)  
 디버깅 자체 및에서 실행 중인 프로세스를 확인할 수 방법을 포함 하 여 아키텍처 측면에서 프로그램 노드를 정의 합니다.  
  
 [프로그램](../../extensibility/debugger/programs.md)  
 디버깅 아키텍처 측면에서 프로그램을 정의 합니다.  
  
 [스레드](../../extensibility/debugger/threads.md)  
 스레드 디버깅 아키텍처 측면에서 특성을 정의 합니다.  
  
 [스택 프레임](../../extensibility/debugger/stack-frames.md)  
 디버깅 아키텍처 측면에서 스택 프레임을 정의 합니다. 스택 프레임은 스레드의 실행 컨텍스트를 제공 하는 스택에 대 한 추상화입니다.  
  
 [모듈](../../extensibility/debugger/modules.md)  
 아키텍처와 같은 실행 파일 또는 DLL 코드의 물리적 컨테이너 디버깅 측면에서 모듈을 정의 합니다.  
  
 [중단점](../../extensibility/debugger/breakpoints-visual-studio-sdk.md)  
 세 가지 유형의 중단점 정의-보류 중인 바인딩되며, 및 오류-디버깅 아키텍처를 기준으로 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 디버그 엔진 (DE) 동시에 코드, 설명서 및 식 평가 컨텍스트 내에서 작동 방법에 대해 설명 합니다. 세 가지 컨텍스트, 위치, 위치, 또는 그와 관련 된 계산의 각각에 대해 설명합니다.  
  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)  
 디버그 엔진 (DE), 식 계산기 (EE) 및 기호 처리기 (SH)를 포함 하는 Visual Studio 디버깅 구성 요소에 대 한 개요를 제공 합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 여 식을 계산 등의 다양 한 디버깅 작업에 대 한 링크를 포함 합니다.