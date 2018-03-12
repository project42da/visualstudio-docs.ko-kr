---
title: "방법: 검색을 사용 하 여 워크플로 디자이너에서 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: f42d3115-2ed2-4941-8f1e-92dac41c30fa
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0ab8fe2ca639dd4660dfbabc8c5497f4ab0b3487
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-use-search-in-the-workflow-designer"></a>방법: 워크플로 디자이너에서 검색 사용
더 크고 복잡한 워크플로를 쉽게 만들려면 워크플로 디자이너에서 검색 기능을 사용하여 키워드로 항목을 찾을 수 있습니다. 디자이너는 바꾸기를 지원하지 않습니다. 검색은 디자이너에서 다음을 찾습니다.  
  
## <a name="quick-find"></a>빠른 찾기  
 빠른 찾기는 디자이너에서 다음을 찾습니다.  
  
-   <xref:System.Activities.Activity> 개체, <xref:System.Activities.Statements.FlowNode> 개체, <xref:System.Activities.Statements.State> 개체, 전환 및 기타 사용자 지정 흐름 제어 항목의 속성  
  
-   변수  
  
-   인수  
  
-   식  
  
#### <a name="using-quick-find"></a>빠른 찾기 기능 사용  
  
1.  워크플로 디자이너를 연, 키를 눌러 **Ctrl + F**, 선택 또는 **편집**, **찾기 및 바꾸기**, **빠른 찾기**합니다.  
  
2.  에 검색 조건을 입력는 **찾을 내용** 텍스트 상자를 클릭 하 고 **다음 찾기**합니다.  
  
3.  검색 조건은 현재 워크플로에 있습니다. 다음 스크린 샷은 디자이너에 있는 활동 표시 이름을 보여 줍니다.  
  
     ![워크플로 디자이너에서 검색 결과](../workflow-designer/media/designersearch.png "DesignerSearch")  
  
## <a name="find-in-files"></a>파일에서 찾기  
 파일에서 찾기를 사용하여 워크플로 파일에서 XAML 파일을 포함한 문자열을 찾습니다.  
  
#### <a name="using-find-in-files"></a>파일에서 찾기 사용  
  
1.  키를 눌러 Visual Studio에서 **Ctrl + Shift + F**, 선택 또는 **편집**, **찾기 및 바꾸기**, **파일에서 찾기**  
  
2.  에 검색 조건을 입력는 **찾을 내용** 텍스트 상자를 클릭 하 고 **모두 찾기**  
  
3.  찾기 결과에 표시 됩니다는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] **찾기 결과** 보기. 결과 항목을 두 번 클릭하면 워크플로 디자이너의 일치 항목이 포함된 활동으로 이동됩니다.