---
title: "디버그 엔진 구현 전략 선택 | Microsoft Docs"
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
  - "디버그 엔진을 구현 전략"
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# 디버그 엔진 구현 전략 선택
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

런타임 아키텍처를 사용 하 여 디버그 엔진 \(DE\) 구현 전략을 결정 합니다.  In\-process 디버깅 하는 프로그램 Visual Studio 세션 디버그 매니저 \(SDM\) 또는 아웃 프로세스에 두 프로세스에 디버그 엔진을 만들 수 있습니다.  다음 지침에 따라 이러한 세 가지 전략 중에서 선택 하는 데 도움이 됩니다.  
  
## 지침  
 독립 프로세스에 DE를 수 있는 동안은 SDM와 프로그램을 디버깅 하려면,는 일반적으로 작업을 수행 하는 이유가 없습니다.  호출 프로세스 간에 상대적으로 느린 됩니다.  
  
 디버그 엔진 Win32 네이티브 런타임 환경에 대 한 공용 언어 런타임 환경에 대해 제공 되는 이미 있습니다.  DE은 이러한 환경 중 하나를 교체 해야 하는 경우에 SDM DE in\-process 만들어야 합니다.  
  
 그렇지 않은 경우에 SDM 프로세스에서 또는 프로그램을 디버깅 하려면 프로세스에는 DE를 만드는 사이 선택할 수 있습니다.  식 계산기는 DE의 프로그램 기호 저장소에 자주 액세스 해야 하는지 여부 및 여부 기호 저장소에 대 한 신속한 액세스 메모리에 로드할 수 있습니다 고려해 야 하는 것이 중요 합니다.  또한 다음 사항을 고려 하십시오.  
  
-   식 계산기와 기호 저장소를 호출 하면 또는 SDM 메모리 공간에 기호 저장소를 읽을 수 있는 경우는 DE\-프로세스는 SDM 만듭니다.  프로그램에 첨부 하는 경우 디버그 엔진의 CLSID는 SDM을 반환 해야 합니다.  SDM이이 CLSID를 사용 하 여는 DE의 프로세스의 인스턴스를 만듭니다.  
  
-   기호 저장소에 액세스 하는 프로그램에서 DE 호출 해야 하는 경우 DE in\-process 프로그램을 만듭니다.  이 경우 프로그램에서 DE의 인스턴스를 만듭니다.  
  
## 참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)