---
title: "명령 배치 지침 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e74bda24459bedeef007b451c7fabe3922e7ab37
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="command-placement-guidelines"></a>명령 배치 지침
Visual Studio 통합된 개발 환경 (IDE)에서 명령을 위치 지정에 대 한 유용한 명령 집합의 크기에 따라 달라 집니다. 명령 정의 되 고.vsct 파일의 정보에 따라 배치 됩니다.  
  
## <a name="best-practices-for-all-command-sets"></a>모든 명령 집합에 대 한 모범 사례  
 모든 명령 집합에 대 한 다음이 지침을 따르십시오.  
  
-   차트 명령 구조는 미리 준비 합니다. 명령, 콤보 상자, 명령 그룹 및 둘 이상의 위치에 사용할 수 있는 바로 가기 메뉴를 식별 합니다.  
  
-   같은 그룹에 나타나는 명령은 관련 되어야 합니다.  
  
-   하나의 명령을 포함 하는 그룹을 사용할 수 있습니다.  
  
-   패키지를 기존 Visual Studio 메뉴 명령의 많은 추가 해야 합니다. 대신, 메뉴 또는 하위 메뉴를 호스팅할 새로운 명령이 있습니다를 만들어야 합니다.  
  
-   포함 하면 명령을 기존 메뉴, 명령 이름에의 용도 선택을 취소 하 고 기존 명령와 혼동 해서는 안 됩니다.  
  
## <a name="best-practices-for-small-command-sets"></a>작은 명령 집합에 대 한 모범 사례  
 에 몇 개의 명령이 하는 VSPackage를 개발 하는 경우 또한 다음이 지침을 따르십시오.  
  
-   사용 가능한 경우는 [부모 요소](../../extensibility/parent-element.md) 명령, 콤보 상자, 그룹 또는 자식 메뉴의 적절 한 그룹에 배치 하 합니다.  
  
-   표시는 VSPackage에서 메뉴에 이러한 그룹을 할당 합니다.  
  
-   부모 또는 자식 메뉴 명령을 이어야 합니다는 [그룹 요소](../../extensibility/group-element.md)합니다. 그룹에 명령 및 자식 메뉴를 지정 하 고 부모 메뉴에 그룹을 할당 합니다.  
  
-   추가 하 여 명령을 추가 그룹에 넣을 수 있습니다는 [CommandPlacements 요소](../../extensibility/commandplacements-element.md) 명령의 정의 다음 섹션 및 다음 여기에 추가 된 `CommandPlacements Element` 는 [CommandPlacement 요소](../../extensibility/commandplacement-element.md) 각각에 대해 추가 그룹입니다.  
  
## <a name="best-practices-for-large-command-sets"></a>긴 명령 집합에 대 한 모범 사례  
 VSPackage에서 여러 컨텍스트에서 표시 되는 많은 명령을 사용할 경우 또한 다음이 지침을 따르십시오.  
  
-   메뉴, 그룹 및 자체 부모로 지정 하는 명령을 확인 합니다. 즉, 할당 하지 않습니다는 `Parent Element` 정의 항목의 합니다.  
  
-   사용 하 여 `CommandPlacement Element` 의 항목은 `CommandPlacements Element` 메뉴, 그룹 및 명령을 해당 부모 메뉴 및 그룹에 배치 하는 섹션입니다.  
  
-   에 `CommandPlacements` 섹션을 채우는 특정된 메뉴 항목 또는 그룹은 서로 인접 한 해야 합니다. 이 쉬워지며는 `Priority` 순위를 더 쉽게 확인할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)