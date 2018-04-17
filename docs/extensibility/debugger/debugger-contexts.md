---
title: 디버거 컨텍스트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8a9310512417ac0e24046a1b7bcc1fd92099fe98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debugger-contexts"></a>디버거 컨텍스트
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅, 디버그 엔진 (DE)는 동시에 여러 가지 컨텍스트 내에서 다음과 같이 표시 합니다.  
  
-   프로그램의 실행 스트림 내의 현재 위치를 설명 하는 코드 컨텍스트  
  
-   설명서 컨텍스트 또는 소스 문서 내의 현재 위치에 설명 하는 위치입니다.  
  
-   식 계산 컨텍스트는 식에는 실행할 컨텍스트를 설명 합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)  
 코드를 명령은 처리 하지만 다른 방법으로 표현 되지 않을 수 있습니다 여기서 않던 언어와 오늘날의 런타임 아키텍처에서 프로그램의 명령 스트림에 주소로 코드 컨텍스트를 설명 합니다.  
  
 [문서 위치](../../extensibility/debugger/document-position.md)  
 Visual Studio IDE에 알려진 소스 파일의 위치에 대 한 추상화를 사용 하 여 디버깅에서 문서 위치를 정의 합니다.  
  
 [문서 컨텍스트](../../extensibility/debugger/document-context.md)  
 에서는 원본 파일과 관련 하 여 Visual Studio 디버깅의 문서 컨텍스트를 나타냅니다. 또한 기호 처리기 코드 컨텍스트 설명서 컨텍스트에 매핑되 하는 방법을 설명 합니다.  
  
 [식 계산 컨텍스트](../../extensibility/debugger/expression-evaluation-context.md)  
 Visual Studio에서 식 평가 컨텍스트에 대 한 정보를 제공합니다. 예를 들어 식 평가 컨텍스트에 연결 된 스택 프레임을 지역 변수, 메서드 매개 변수 및 클래스 멤버를 평가 하기 위한 컨텍스트를 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버깅 개념](../../extensibility/debugger/debugger-concepts.md)  
 기본 디버깅 아키텍처 개념을 설명합니다.  
  
 [디버깅 구성 요소](../../extensibility/debugger/debugger-components.md)  
 디버그 엔진 (DE), 식 계산기 (EE) 및 기호 처리기 (SH)를 포함 하는 Visual Studio 디버깅 구성의 개요를 제공 합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 여 식을 계산 등의 다양 한 디버깅 작업에 대 한 링크를 포함 합니다.