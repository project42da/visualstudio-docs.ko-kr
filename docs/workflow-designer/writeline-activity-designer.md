---
title: "WriteLine 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 615cfb46222dfbf6e6b3cb1ba6741cde7c7bf708
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="writeline-activity-designer"></a>WriteLine 활동 디자이너
**WriteLine** 활동 디자이너를 생성 및 구성 하는 데 사용 됩니다 한 <xref:System.Activities.Statements.WriteLine> 활동.  
  
## <a name="the-writeline-activity"></a>WriteLine 활동  
 <xref:System.Activities.Statements.WriteLine> 활동은 지정된 <xref:System.IO.TextWriter> 개체에 텍스트를 씁니다. 지정된 <xref:System.IO.TextWriter>가 없는 경우 <xref:System.Activities.Statements.WriteLine>은 콘솔에 텍스트를 씁니다.  
  
### <a name="using-the-writeline-activity-designer"></a>WriteLine 활동 디자이너 사용  
 **WriteLine** 활동 디자이너에서 찾을 수 있습니다는 **기본형** 의 범주는 **도구 상자**를 클릭 하 여 액세스할는 **도구 상자**탭은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **WriteLine** 활동 디자이너에서 끌어 올 수는 **도구** 장식 하 고는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 표면 어디 활동은 일반적으로 배치 같은 안쪽으로 <xref:System.Activities.Statements.Sequence>. 그러면 기본 <xref:System.Activities.Statements.WriteLine>인 WriteLine이라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더에서 편집할 수는 **WriteLine** 작업 디자이너 또는 **DisplayName** 속성 표의 상자.  
  
### <a name="the-writeline-properties"></a>WriteLine 속성  
 다음 표에서는 <xref:System.Activities.Statements.WriteLine> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.WriteLine> 활동의 이름입니다. 기본값은 WriteLine입니다. <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|쓸 텍스트입니다. 속성을 설정 하는 Visual Basic 식에 입력 하면 **텍스트** 상자는 **WriteLine** 활동 디자이너 속성 표에.|  
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter>이 <xref:System.Activities.Statements.WriteLine>를 쓸 대상 <xref:System.Activities.Statements.WriteLine.Text%2A>입니다. 기본값은 콘솔입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [기본 형식](../workflow-designer/primitives-activity-designers.md)   
 [할당](../workflow-designer/assign-activity-designer.md)   
 [지연](../workflow-designer/delay-activity-designer.md)   
 [메서드 호출](../workflow-designer/invokemethod-activity-designer.md)