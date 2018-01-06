---
title: "디버그 엔진 구현 전략 선택 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fae5211ac270832f07038faafbd6f5bc463d3944
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>디버그 엔진 구현 전략 선택
런타임 아키텍처를 사용 하 여 디버그 엔진 (DE) 구현 전략을 결정 합니다. 디버그 엔진에는 in-process에 프로그램을 디버깅, Visual Studio 세션 디버그 관리자 (SDM) 또는 둘 모두를 프로세스 아웃 프로세스를 만들 수 있습니다. 다음 지침은 이러한 세 가지 전략 중에서 선택할 수 있습니다는 데 도움이 되어야 합니다.  
  
## <a name="guidelines"></a>지침  
 Out of process를 DE에 대 한 가능 하지만 모두은 SDM 및 프로그램 디버깅, 일반적으로 없는 이유는 이렇게 하려면. 프로세스 경계를 넘어 호출은 상대적으로 속도가 느립니다.  
  
 디버그 하 고 공용 언어 런타임 환경에 대 한 Win32 네이티브 런타임 환경에 대 한 엔진 이미 제공 합니다. 이러한 환경 중 하나에 대 한는 DE 바꿔야 DE in-process은 SDM를 만들어야 합니다.  
  
 그렇지 않으면 응용 프로그램은 SDM에 프로세스 또는 디버깅할 프로그램에 프로세스는 DE 만들기를 선택할 수 있습니다. 식 계산기는 DE의 프로그램 기호 저장소에 자주 액세스를 해야 하는 여부 및 빠른 액세스를 위해 메모리에 기호 저장소를 로드할 수 있는지 여부를 고려 하는 것이 유용 합니다. 다음 사항도 고려 하십시오.  
  
-   식 계산기와 기호 저장소 간의 많은 호출 하지 않습니다. 또는 SDM 메모리 공간에 기호 저장소를 읽을 수 있으면은 SDM에 프로세스에서 DE 만듭니다. 프로그램에 연결할 때는 SDM에 디버그 엔진의 CLSID를 반환 해야 합니다. SDM이이 CLSID를 사용 하 여는 DE의 프로세스에서 인스턴스를 만듭니다.  
  
-   DE 기호 저장소에 액세스 하는 프로그램을 호출 해야 하는 경우 DE in-process 프로그램으로 만듭니다. 이 경우 프로그램은 DE의 인스턴스를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)