---
title: "Workflow Designer의 바로 가기 키 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "WFDKeyboardShortcuts.UI"
ms.assetid: 9be75438-a4a3-4781-94e5-45b7ec082358
caps.latest.revision: 4
caps.handback.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# Workflow Designer의 바로 가기 키
키보드를 사용하여 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]의 모든 핵심 기능에 액세스할 수 있습니다.  
  
## 키보드를 사용하여 Workflow Designer 탐색  
 [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에서는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 전역 바로 가기와 디버깅 바로 가기가 적용됩니다.또한 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 고유의 바로 가기 키도 여러 가지가 있습니다.[!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에서 모든 바로 가기 키를 다시 매핑할 수 있습니다.하지만 다시 호스팅된 응용 프로그램에는 이러한 바로 가기 키가 하드 코딩되어 있습니다.  
  
### Workflow Designer 바로 가기 키  
 다음 표에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 명령에 할당된 기본 바로 가기 키가 요약되어 있습니다.  
  
|바로 가기|목적|  
|-----------|--------|  
|Ctrl\+E, A|인수 디자이너를 표시하거나 숨깁니다.|  
|Ctrl\+E, C|현재 위치에서 선택한 활동을 축소합니다.|  
|Ctrl\+E, E|현재 위치에서 선택한 활동을 확장합니다.|  
|Ctrl\+E, F|순서도에서 선택한 활동을 연결합니다.|  
|Ctrl\+E, I|가져오기 디자이너를 표시하거나 숨깁니다.|  
|Ctrl\+E, M|키보드 포커스를 탭 순서의 다음 항목으로 이동합니다.|  
|Ctrl\+E, N|선택한 활동\(또는 가장 가까운 활동\) 범위 내에 새 변수를 만듭니다.|  
|Ctrl\+E, O|개요 맵을 표시하거나 숨깁니다.|  
|Ctrl\+E, P|선택한 활동의 부모로 이동합니다.그러면 이동 경로 탐색에서 한 수준 위로 올라가면서 디자이너 화면의 루트 활동이 바뀝니다.|  
|Ctrl\+E, S|키보드 포커스가 있는 항목을 현재 선택에 추가합니다.|  
|Ctrl\+E, V|변수 디자이너를 표시하거나 숨깁니다.|  
|Ctrl\+E, X|워크플로의 모든 활동을 확장합니다.|  
|Ctrl\+Alt\+F6|키보드 포커스를 현재 UI 영역에서 시퀀스의 다음 영역으로 이동합니다.순서는 다음과 같습니다.<br /><br /> 1.  이동 경로 탐색 막대<br />2.  디자이너 화면<br />3.  인수\/변수\/가져오기 디자이너\(열려 있는 경우\)<br />4.  셸|  
  
### 순서도  
 다음 목록은 키보드로 순서도를 구성하는 데 사용되는 제스처를 보여 줍니다.[!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 나머지 부분에서와 마찬가지로 [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에 제공된 전역 도구 상자 바로 가기를 사용하여 디자이너 화면에 활동을 추가합니다.  
  
-   활동을 이동하려면 활동을 선택하고 화살표 키를 사용하여 활동 위치를 조정합니다.  
  
-   순서도의 크기를 조정하려면 화살표 키를 사용하여 순서도의 현재 경계 너머로 활동을 이동합니다.순서도의 크기가 자동으로 조정됩니다.  
  
-   활동을 시작 노드로 설정하려면 상황에 맞는 메뉴에서 **시작 노드로 설정** 명령을 사용합니다.  
  
-   활동을 연결하려면  
  
    1.  소스 활동으로 이동하여 해당 활동을 선택합니다.  
  
    2.  Ctrl\+E, M을 여러 번 눌러 키보드 포커스를 대상 활동으로 옮깁니다.  
  
    3.  Ctrl\+E, S를 눌러 대상 활동을 선택 항목에 추가합니다.  
  
    4.  Ctrl\+E, F를 눌러 소스의 커넥터를 대상에 추가합니다.  
  
 키보드로 활동을 연결하는 방법에 대한 참고 사항은 다음과 같습니다.  
  
-   CTRL\+E, F를 누르기 전에 선택 영역에 활동을 추가하여 동시에 여러 연결을 만들 수 있습니다.선택 영역에 활동이 추가된 순서로 연결이 이루어집니다.  
  
-   활동 쌍을 연결할 수 없는 경우\(예: 소스 활동에 나가는 연결이 이미 있는 경우\)에도 가능하면 선택 항목의 활동 사이에 다른 연결이 설정됩니다.  
  
-   **FlowDecision**이 선택 항목에 포함되어 있고 **FlowDecision**에 나가는 커넥터가 없는 경우 커넥터는 **True** 분기에 배치됩니다.  
  
### 식 편집  
 기본적으로 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 식 편집기에는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 텍스트 편집을 위한 기본 바로 가기 키가 적용되며 다음과 같은 제한 사항이 있습니다.  
  
-   다음 명령에 대한 바로 가기 키를 다시 매핑할 수 없습니다.식을 편집할 때 이러한 명령에 액세스하기 위해서는 기본 바로 가기 키만 사용할 수 있습니다.  
  
    1.  잘라내기  
  
    2.  복사  
  
    3.  붙여넣기  
  
    4.  모두 선택  
  
    5.  실행 취소  
  
    6.  다시 실행  
  
-   [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]의 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에서 식 편집 명령에 대한 바로 가기 키를 다시 매핑하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 범위에서 바로 가기를 편집합니다.텍스트 편집기 범위에서 변경한 내용이 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에 자동으로 적용되지는 않습니다.따라서 양쪽 모두에서 바로 가기를 다시 매핑하려면 범위마다 한 번씩 변경을 두 번 적용해야 합니다.