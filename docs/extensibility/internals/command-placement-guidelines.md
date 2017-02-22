---
title: "명령 배치 지침 | Microsoft Docs"
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
  - "명령, 작은 명령 집합"
  - "작은 명령 집합"
  - "명령 집합"
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
caps.latest.revision: 28
caps.handback.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
---
# 명령 배치 지침
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio 통합된 개발 환경 \(IDE\)에서 명령을 위치에 대 한 유용한 명령 집합의 크기에 따라 달라 집니다. 명령은 정의 하 고.vsct 파일의 정보에 따라 배치 됩니다.  
  
## 모든 명령 집합에 대 한 모범 사례  
 모든 명령 집합에 대 한 다음이 지침을 따르십시오.  
  
-   명령 구조에 대 한 차트를 미리 준비 합니다. 명령, 콤보 상자, 명령 그룹 및 둘 이상의 위치에 사용할 바로 가기 메뉴를 식별 합니다.  
  
-   동일한 그룹에 표시 된 명령 관련 되어야 합니다.  
  
-   하나의 명령을 포함 하는 그룹을 사용할 수 있습니다.  
  
-   패키지를 기존 Visual Studio 메뉴 명령 많은 추가 해야 합니다. 대신, 메뉴 또는 하위 메뉴를 호스팅할 새 명령을이 만들어야 합니다.  
  
-   놓으면 명령을 기존 메뉴, 명령 이름에의 용도 명확 하 고 기존 명령을와 혼동 해서는 안 됩니다.  
  
## 작은 명령 집합에 대 한 모범 사례  
 몇 개의 명령이 포함 된 VSPackage를 개발 하는 경우 또한 다음이 지침을 따르십시오.  
  
-   사용 가능한 경우는 [부모 요소](../../extensibility/parent-element.md) 명령, 콤보 상자, 그룹 또는 자식 메뉴를 적절 한 그룹에 넣습니다.  
  
-   VSPackage에서 표시 하는 메뉴에 이러한 그룹을 할당 합니다.  
  
-   부모 또는 자식 메뉴 명령을 해야는 [그룹 요소](../../extensibility/group-element.md)합니다. 그룹에 명령 및 자식 메뉴를 할당 하 고 부모 메뉴에 그룹을 할당 합니다.  
  
-   추가 하 여 추가 그룹에 명령을 넣을 수 있습니다는 [CommandPlacements 요소](../../extensibility/commandplacements-element.md) 명령의 정의 뒤 섹션 한 후에 추가 `CommandPlacements Element` 는 [CommandPlacement 요소](../../extensibility/commandplacement-element.md) 각 추가 그룹에 대 한 합니다.  
  
## 긴 명령 집합에 대 한 모범 사례  
 VSPackage에는 여러 컨텍스트에서 표시 되는 많은 명령을 포함 하는 경우 또한 다음이 지침을 따르십시오.  
  
-   메뉴, 그룹 및 자체의 부모로 지정 하는 명령을 확인 합니다. 즉, 할당 하지 않으면는 `Parent Element` 항목의 정의에 있습니다.  
  
-   사용 하 여 `CommandPlacement Element` 항목에는 `CommandPlacements Element` 메뉴, 그룹 및 명령은 해당 부모 메뉴 및 그룹에 배치 하는 섹션입니다.  
  
-   에 `CommandPlacements` 섹션, 특정된 메뉴를 채우는 하는 항목 또는 그룹은 서로 인접 한 해야 합니다. 이 쉬워지며는 `Priority` 순위를 보다 쉽게 확인할 수 있습니다.  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)