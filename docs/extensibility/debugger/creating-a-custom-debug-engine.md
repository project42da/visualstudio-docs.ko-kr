---
title: "사용자 지정 디버그 엔진 만들기 | Microsoft Docs"
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
  - "구현 하는 디버그 엔진"
  - "사용자 지정 디버그 엔진"
  - "디버깅 [디버깅 SDK], 사용자 지정 디버그 엔진"
ms.assetid: 52794238-6fae-451c-bf1c-99f344c6f173
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 사용자 지정 디버그 엔진 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)의 특정 런타임 아키텍처를 디버깅할 수 있는 구성 요소입니다.  일반적으로 런타임 환경 당 하나의 DE 구현이입니다.  
  
> [!NOTE]
>  Transact\-SQL 및 JScript에 대 한 별도 DE 구현 되지만 VBScript 및 JScript 단일 DE 공유 합니다.  
  
 실행 제어, 중단점 및 식 평가 같은 디버깅 서비스를 제공 하는 인터프리터 또는 작업 시스템 DE를 사용할 수 있습니다.  이러한 서비스 DE 인터페이스를 통해 구현 되 고 다른 운영 모드 간의 전환에 발생할 수 있습니다.  자세한 내용은 [작업 모드](../../extensibility/debugger/operational-modes.md)를 참조하십시오.  
  
 DE를 만드는 다음 단계로 구성 됩니다.  
  
1.  DE Visual Studio 등록 하는 중  
  
2.  프로그램 디버깅 될 수 있도록  
  
3.  실행 제어 및 상태 평가  
  
4.  이벤트 보내기  
  
5.  종료 및 분리  
  
## 단원 내용  
 [사용자 지정 디버그 엔진을 등록합니다.](../../extensibility/debugger/registering-a-custom-debug-engine.md)  
 사용 될 수 있도록 디버그 엔진 Visual Studio 등록 하는 데 필요한 단계에 설명 합니다.  
  
 [디버깅할 프로그램을 사용 하도록 설정](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)  
 사용자 DE 프로그램을 디버깅 하려면 DE를 실행 하거나 해야 기존 프로그램에 첨부할 것에 대해 설명 합니다.  
  
 [실행 제어 및 상태 평가](../../extensibility/debugger/execution-control-and-state-evaluation.md)  
 이유는 응용 프로그램을 디버깅 실행 제어 기능 구현에 필요한 방법에 대해 설명 합니다.  
  
 [이벤트 전송](../../extensibility/debugger/sending-events.md)  
 디버거에서 하는 DE 간의 통신에 DCOM 기반 이벤트 모델로 설명 합니다.  
  
 [종료 및 분리](../../extensibility/debugger/termination-and-detaching.md)  
 중단점, 예외, 런타임 오류 및 디버깅 하려면 응용 프로그램에서 무한 루프 된다는 것을 의미 하는 정상적인 종료를 달성 하는 방법에 설명 합니다.  
  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)  
 디버깅 세션에서 발생 하는 이벤트의 호출 순서를 문서화 합니다.  
  
 [방법: 사용자 지정 디버그 엔진 디버깅](../../extensibility/debugger/how-to-debug-a-custom-debug-engine.md)  
 사용자 지정 DE 디버깅 하는 방법에 설명 합니다.  
  
## 참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)