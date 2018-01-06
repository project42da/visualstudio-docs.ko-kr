---
title: "워크플로 디자이너 셸 기능 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: WFDShellFeatures.UI
ms.assetid: 14bfe312-9592-408e-92ce-e98585ad16e7
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: f2df04273936f84c8bf371ecb053a7bb22f82147
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-designer-shell-features"></a>워크플로 디자이너 셸 기능
[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]는 디자이너 화면, 화면 위쪽의 이동 경로 탐색 막대, 화면 아래쪽의 셸 등 세 가지 주요 UI 영역으로 구성됩니다. 화면 위쪽에 있는 이동 경로 탐색 막대는 현재 루트 활동의 상위 목록을 표시하는 데 사용됩니다. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][방법: 이동 경로 탐색을 사용 하 여](../workflow-designer/how-to-use-breadcrumb-navigation.md)합니다. 화면 중앙의 디자이너 화면은 워크플로를 작성하는 데 사용됩니다. 화면 아래쪽의 셸에는 현재 뷰를 관리하는 데 사용되는 단추가 포함되어 있습니다.  
  
## <a name="shell-features"></a>셸 기능  
 셸 막대 오른쪽에는 워크플로를 확대/축소하고 워크플로의 내용을 화면 크기에 맞추며 개요 맵을 표시하거나 숨기는 데 사용할 수 있는 단추가 있습니다.  바로 가기 키 Ctrl++ 및 Ctrl+-를 사용하여 워크플로를 확대하거나 축소할 수도 있습니다.  
  
## <a name="overview-map"></a>개요 맵  
 개요 맵은 모든 자식과 확장된 자식을 포함하여 현재의 이동 경로 탐색 막대에 해당하는 전체 활동을 작은 버전으로 표시합니다. 편집기 안에는 현재 표시된 활동 부분을 강조하는 주황색 테두리의 사각형 뷰포트가 있습니다. 이 사각형을 개요 맵 주위로 끌면 Workflow Designer가 스크롤되면서 편집기 뷰가 바뀝니다.  
  
> [!NOTE]
>  [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 사용자 인터페이스는 가상화되어 있습니다. 활동 디자이너는 필요한 경우에만 렌더링됩니다. 디자이너 화면에 표시된 적이 없는 워크플로 부분이 있다면 그 부분은 개요 맵에서 흰색으로 나타납니다. 개요 맵 주위를 스크롤하면 워크플로가 완전히 그려집니다.  
  
## <a name="copying-or-saving-workflows-as-images"></a>워크플로를 이미지로 복사 또는 저장  
 워크플로를 비트맵 형식으로 복사하거나 비트맵 또는 벡터 형식으로 저장할 수 있습니다. 이미지를 복사하거나 저장하면 모든 자식과 확장된 자식을 포함하여 현재의 경로 탐색 루트의 전체 활동에 대한 뷰를 다른 프로그램으로 내보낼 수 있습니다.  
  
 이미지로 복사 하려면 마우스 오른쪽 단추로 클릭 하 고 선택 디자이너 **이미지로 복사**합니다. 이미지로 저장 하려면 마우스 오른쪽 단추로 클릭 하 고 선택 디자이너 **이미지로 저장**합니다. 워크플로는 JPG, PNG, GIF 또는 XPS 형식으로 저장할 수 있습니다. 형식에서 선택 된는 **다른 이름으로 저장** 대화 상자에는 **파일 형식:** 드롭다운 목록 상자는 창의 맨 아래에 있습니다.  
  
## <a name="fonts-and-colors"></a>글꼴 및 색  
 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 내부의 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]에서 사용하는 글꼴은 운영 체제 글꼴로 제어합니다. 운영 체제 테마에 고대비 색 구성표를 사용하는 경우 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 표시되는 색상이 달라집니다. 글꼴 또는 색상 설정을 변경한 후 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]에 변경 내용을 적용하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]을 다시 시작해야 합니다.