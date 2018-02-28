---
title: "디버깅할 프로그램을 사용 하도록 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], enabling for programs
ms.assetid: 61d24820-0cd9-48b6-8674-6813f7493237
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a581c5a9ae56f52727c011db1de2ad35a5ba3592
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-a-program-to-be-debugged"></a>디버깅할 프로그램을 사용 하도록 설정
디버그 엔진 (DE)을 통해 프로그램을 디버그할 수는 DE 시작 하거나 해야 기존 프로그램에 연결 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [포트 가져오기](../../extensibility/debugger/getting-a-port.md)  
 디버깅할 프로그램을 사용 하도록 설정 하는 첫 번째 단계로 포트를 가져오는 방법을 설명 합니다.  
  
 [프로그램 등록](../../extensibility/debugger/registering-the-program.md)  
 디버깅할 프로그램을 사용 하기 위한 다음 단계에 설명: 포트를 등록 합니다. 프로그램을 디버그할 수 있습니다, 등록 후에 연결 하거나 타임 (JIT) 디버깅의 프로세스 중 하나입니다.  
  
 [프로그램에 연결](../../extensibility/debugger/attaching-to-the-program.md)  
 다음 단계에 설명: 프로그램에 디버거를 연결 합니다.  
  
 [시작 기반 연결](../../extensibility/debugger/launch-based-attachment.md)  
 시작 기반 첨부 파일은 SDM에서 시작 시 자동 프로그램에 설명 합니다.  
  
 [필요한 이벤트 보내기](../../extensibility/debugger/sending-the-required-events.md)  
 디버그 엔진 (DE)를 만들 때 필요한 이벤트를 단계별로 설명 하 고 프로그램에 연결 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [사용자 지정 디버그 엔진 만들기](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 디버그 엔진 (DE)을 정의 하 고 DE 인터페이스와 어떻게 다른 작업 모드 간에 전환 하도록 디버거를 초래할 수 있습니다를 통해 구현 되는 서비스에 설명 합니다.