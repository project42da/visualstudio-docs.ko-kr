---
title: "DoWhile 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 041c63d45e70305495fd18ed595a31eee6772389
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="dowhile-activity-designer"></a>DoWhile 활동 디자이너
<xref:System.Activities.Statements.DoWhile> 활동 실행에 포함 된 활동의 <xref:System.Activities.Statements.DoWhile.Body%2A> 적어도 한 번에 지정된 된 조건이 평가 될 때까지 **false**합니다. 루프 본문에 포함된 활동을 0번 이상 실행해야 할 경우 <xref:System.Activities.Statements.While> 활동을 대신 사용하세요.  
  
## <a name="dowhile-properties-in-the-workflow-designer"></a>Workflow Designer의 DoWhile 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.DoWhile> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|조건에 해당 하는 동안 실행할 활동을 **true**합니다. 추가 하는 <xref:System.Activities.Statements.DoWhile.Body%2A> 활동을 도구 상자의 활동은 **본문** 상자에 **DoWhile** 활동 디자이너를 "여기에 작업 놓기" 힌트 텍스트가 있습니다.|  
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|True|루프를 반복할 때마다 평가할 조건입니다. 설정 하는 <xref:System.Activities.Statements.DoWhile.Condition%2A>, 입력 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식에는 **조건** 상자에 **DoWhile** 활동 디자이너나 속성 표의 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [While](../workflow-designer/while-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)