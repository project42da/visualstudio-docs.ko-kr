---
title: "소스 제어 플러그 인 아키텍처 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인, 아키텍처"
ms.assetid: 35351d4c-9414-409b-98fc-f2023e2426b7
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# 소스 제어 플러그 인 아키텍처
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 지원을 추가할 수 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\)을 구현 하 고 플러그 인을 연결.  IDE 플러그인 잘 정의 된 소스 제어 플러그 인 API를 통해 소스 제어에 연결 됩니다.  IDE 도구 모음 및 메뉴 명령을 구성 사용자 인터페이스 \(UI\)를 제공 하 여 소스 제어 시스템의 버전 제어 기능을 제공 합니다.  소스 제어 플러그 인은 소스 제어 기능을 구현합니다.  
  
## 소스 제어 플러그 인 리소스  
 소스 제어 플러그 인을 만들고 버전 관리 응용 프로그램에 연결 하는 데 도움이 되는 리소스를 제공의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  소스 제어 플러그 인에 통합 될 수 있도록 해당 소스 제어 플러그 인에서 구현 해야 하는 API 사양을 포함 되어 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  기본 소스 제어 플러그 인 demonstrating 구현 필수 기능에 소스 제어 플러그 인 API 규격의 구현 하는 코드 샘플을 \(c \+ \+로 작성\) 포함 되어 있습니다.  
  
 소스 제어 플러그 인 API 사양은 필요 집합의 기능에 따라 소스 제어 플러그 인 API를 구현 소스 컨트롤 DLL을 만드는 경우 모든 소스 제어 시스템을 활용할 수 있습니다.  
  
## 구성 요소  
 원본 컨트롤 어댑터 패키지 다이어그램에서은 소스 제어 작업에는 소스 제어 플러그 인을 지원 되는 함수 호출에 대 한 사용자의 요청으로 변환 하는 IDE의 구성 요소입니다.  이렇게 하려면 소스 제어 플러그 인 및 IDE IDE와 플러그인 사이의 정보를 앞뒤로 전달 하는 효과적인 대화가 있어야 합니다.  이 대화 상자에 모두 동일한 언어를 사용 해야 합니다.  소스 제어 플러그 인이이 문서에 설명 된 API이이 교환에 대 한 일반적인 용어입니다.  
  
 ![소스 코드 컨트롤 아키텍처 다이어그램](../../extensibility/internals/media/vs_sccsdk_plug_in_arch.png "vs\_sccsdk\_plug\_in\_arch")  
VS와 소스 제어 플러그 인을 보여 주는 아키텍처 다이어그램  
  
 아키텍처 다이어그램에 표시 된 대로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자의 프로젝트 작업 및 관련된 부품, 편집기와 솔루션 탐색기 같은 셸을 VS 셸 다이어그램에서 지정 된 레이블 호스팅합니다.  원본 컨트롤 어댑터 패키지 IDE에서 소스 제어 플러그 인 사이의 상호 작용을 처리합니다.  컨트롤 어댑터 소스 패키지 자체 소스 컨트롤 UI를 제공합니다.  이 시작 하 고 소스 제어 작업의 범위를 정의 하는 사용자와 상호 작용 하는 최상위 UI입니다.  
  
 소스 제어 플러그 인은 그림에 표시 된 두 부분으로 구성 될 수 있습니다 자신의 UI를 가질 수 있습니다.  "공급 업체 UI" 상자를 경우에 소스 제어 플러그 인 작성자는 제공 하는 사용자 지정 사용자 인터페이스 요소를 나타냅니다.  사용자는 고급 소스 제어 작업을 호출 하면 이러한 직접 해당 소스 제어 플러그 인에 표시 됩니다.  "UI 도우미" 상자를 IDE를 통해 직접 호출 되는 소스 제어 플러그 인 UI 기능 집합입니다.  소스 제어 플러그 인 IDE에서 제공 하는 특수 한 콜백 함수를 통해 IDE UI 관련 메시지를 전달 합니다.  IDE는 더 완벽 하 게 통합 UI 도우미를 용이 하 게 \(자주 사용 하는  **고급** 단추\) 따라서 보다 일관 된 최종 사용자 경험을 제공 하 고 있습니다.  
  
 소스 제어 플러그 인을 변경할 수 없습니다.는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸 및 따라서 소스 컨트롤 어댑터 패키지 또는 소스를 IDE에서 제공 하는 UI를 제어 합니다.  이 구현에 통합된 된 경험을 최종 사용자에 대 한 기여는 다양 한 소스 제어 플러그 인 API 함수를 통해 제공 하는 유연성의 최대 사용을 해야 합니다.  소스 제어 플러그 인 API 설명서의 참조 단원 일부 고급 소스 제어 플러그 인 기능에 대 한 정보가 포함 되어 있습니다.  이러한 기능을 이용 하려면 소스 제어 플러그 인 IDE로 고급 기능 초기화 하는 동안 선언 해야 하 고 각 기능에 대 한 특정 고급 함수를 구현 해야 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)   
 [용어](../../extensibility/source-control-plug-in-glossary.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)