---
title: "원본 제어 플러그 인 아키텍처 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control plug-ins, architecture
ms.assetid: 35351d4c-9414-409b-98fc-f2023e2426b7
caps.latest.revision: "24"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 22929c34d656fb4f163076ca0b5dfb498d44c884
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-plug-in-architecture"></a>소스 제어 플러그 인 아키텍처
원본 제어 지원을 추가할 수 있습니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구현 하는 소스 제어 플러그 인을 연결 하 여 통합된 개발 환경 (IDE). IDE는 잘 정의 된 소스 제어 플러그 인 API를 통해 플러그 인 소스 제어에 연결합니다. IDE의 도구 모음 및 메뉴 명령으로 구성 된 사용자 인터페이스 (UI)를 제공 하 여 원본 제어 시스템의 버전 제어 기능을 노출 합니다. 소스 제어 플러그 인 소스 제어 기능을 구현합니다.  
  
## <a name="source-control-plug-in-resources"></a>소스 제어 플러그 인 리소스  
 리소스 버전 관리 응용 프로그램을 연결 하 고를 제공 하는 소스 제어 플러그 인은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. 소스 제어 플러그 인에 통합 될 수 있도록 소스 제어 플러그 인에서 구현 해야 하는 API 사양을 포함는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. 또한 기본 원본 제어 플러그 인 보여 주는 구현 하는 소스 제어 플러그 인 API와 호환 되는 필수 기능을 구현 하는 코드 샘플 (c + +로 작성)를 포함 합니다.  
  
 소스 제어 플러그 인 API 사양에 필요한 소스 제어 플러그 인 API에 따라 구현 된 함수 집합을 소스 제어 DLL을 만들면 사용자가 선택한 모든 소스 제어 시스템을 활용할 수 있습니다.  
  
## <a name="components"></a>구성 요소  
 다이어그램에서 소스 제어 어댑터 패키지는 소스 제어 플러그 인에서 지 원하는 함수 호출에 소스 제어 작업에 대 한 사용자의 요청을 변환 하는 IDE의 구성 요소입니다. 이러한 상황이 발생 하기에 대 한 IDE와 소스 제어 플러그 인 및 플러그 인 IDE 간에 간에 정보를 전달 하는 효과적인 대화가 있어야 합니다. 수행 하려면이 대화 상자에 대 한 동일한 언어 서로 통신할 해야 모두. 이 설명서에 설명 된 소스 제어 플러그 인은이 교환에 대 한 일반적인 어휘입니다.  
  
 ![소스 코드 제어 아키텍처 다이어그램](../../extensibility/internals/media/vs_sccsdk_plug_in_arch.gif "vs_sccsdk_plug_in_arch")  
간의 상호 작용 VS 및 소스 제어 플러그 인을 보여 주는 아키텍처 다이어그램  
  
 아키텍처 다이어그램에 나와 있는 것 처럼는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자의 작업 중인 프로젝트와 관련 된 구성 요소 편집기 및 솔루션 탐색기와 같은 VS shell는 다이어그램에 지정 된 레이블 셸을 호스트 합니다. 소스 제어 어댑터 패키지는 소스 제어 플러그 인 및 IDE 간의 상호 작용을 처리합니다. 소스 제어 어댑터 패키지는 자체 소스 제어 UI를 제공합니다. 되기 시작 하 고 소스 제어 작업의 범위를 정의 하기 위해 상호 작용 하는 최상위 UI.  
  
 소스 제어 플러그 인에 그림에 나와 있는 것 처럼 두 부분으로 구성 될 수 있는 자체 UI를 가질 수 있습니다. "공급 업체 UI" 이라는 상자, 소스 제어 플러그 인 작성자를 제공 하는 사용자 지정 사용자 인터페이스 요소를 나타냅니다. 이러한 사용자는 고급 소스 제어 작업을 호출 하는 경우 소스 제어 플러그 인에서 직접 표시 됩니다. "도우미 UI" 이라는 상자는 소스 제어 플러그 인 UI 기능 IDE를 통해 직접 호출 되는 집합. 소스 제어 플러그 인 IDE에서 제공 하는 특별 한 콜백 함수를 통해 IDE에 UI 관련 메시지를 전달 합니다. 도우미 UI와 IDE 보다 원활한 통합을 용이 하 게 (종종을 사용 하 여 프로그램 **고급** 단추) 하 고 따라서 더 통합 된 최종 사용자 환경을 제공 합니다.  
  
 소스 제어 플러그 인을 변경할 수 없습니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸 하 고 따라서을 소스 제어 어댑터 패키지 또는 소스 IDE에서 제공 하는 UI를 제어 합니다. 최종 사용자에 대 한 통합된 된 환경을에 영향을 주는 다양 한 소스 제어 플러그 인 API 함수 구현을 통해 제공 하는 유연성을 최대한으로 사용을 해야 합니다. 소스 제어 플러그 인 API 설명서의 참조 섹션에는 몇 가지 고급 소스 제어 플러그 인 기능에 대 한 정보가 포함 됩니다. 이러한 기능을 활용 하려면 소스 제어 플러그 인 선언 해야 IDE 하기 위한 고급 기능 초기화 하는 동안 하며 각 기능에 대 한 특정 고급 함수를 구현 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)   
 [용어 설명](../../extensibility/source-control-plug-in-glossary.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)