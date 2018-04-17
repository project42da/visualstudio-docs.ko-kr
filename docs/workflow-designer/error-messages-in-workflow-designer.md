---
title: 워크플로 디자이너에서 오류 메시지 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- WFDErrorMessages.UI
- System.Activities.Presentation.ErrorActivity.UI
- System.Activities.Presentation.View.ErrorView.UI
ms.assetid: 4d8bbc2e-34fc-477f-9140-4adfd70c34a0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f4deecb6617e85263abc5eaad11dd829abecb05d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="error-messages-in-workflow-designer"></a>워크플로 디자이너의 오류 메시지
이 항목에는 Windows 워크플로 디자이너에서 작업할 때 발생할 수 있는 오류 메시지의 형식을 설명 합니다.

## <a name="situations-in-which-errors-in-the-workflow-designer-occur"></a>워크플로 디자이너에서 오류가 발생하는 경우
 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 오류는 다음 경우에 발생합니다.

1.  식에 오류가 있습니다.

2.  활동의 유효성 검사 제약 조건이 충족되지 않았습니다.

3.  XAML 파일에 오류가 있어서 활동을 로드할 수 없습니다.

4.  XAML 파일에 오류가 있어서 워크플로를 로드할 수 없습니다.

 잘못된 식과 충족되지 않은 유효성 검사 제약 조건으로도 워크플로가 작성됩니다. 워크플로는 작성되지만 런타임 시 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다. XAML 파일에 오류가 있으면 빌드가 수행되지 않습니다.

 내부 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 워크플로가 로드 될 때, 해당 오류에 표시 됩니다는 **오류 목록**합니다. 오류의 소스인 활동을 이동 하려면에서 오류를 두 번 클릭은 **오류 목록**합니다.

### <a name="expression-errors"></a>식 오류
 잘못된 식에는 식 앞에 빨간색 원과 흰색 느낌표가 표시됩니다. 하지만 이 아이콘 위로 마우스를 가져가면 오류의 원인을 설명하는 도구 설명이 표시됩니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 내부에서 식을 클릭하면 오류 원인을 나타내는 줄(밑줄로 표시됨)을 볼 수 있습니다. 밑줄이 그어진 텍스트 위로 마우스를 가져가면 오류의 원인을 설명하는 도구 설명이 표시됩니다.

### <a name="activity-validation-errors"></a>활동 유효성 검사 오류
 활동의 유효성 검사 제약 조건이 충족되지 않은 경우 빨간색 원과 흰색 느낌표가 활동의 오른쪽 위 모서리에 나타납니다. 하지만 이 아이콘 위로 마우스를 가져가면 오류의 원인을 설명하는 도구 설명이 표시됩니다.

### <a name="xaml-load-errors"></a>XAML 로드 오류
 활동 로드 하지 못하는 경우 텍스트와 함께 "활동 로드할 수 없습니다는 XAML에 오류가 있어" 빨간색 상자가 나타납니다. 이 문제는 일반적으로 활동 형식을 확인할 수 없는 경우 발생 합니다. 빨간색 상자를 선택한 후 삭제하여 디자이너에서 잘못된 활동을 삭제할 수 있습니다.

### <a name="workflow-load-errors"></a>워크플로 로드 오류
 워크플로 로드 하지 못하면 "문서에 문제가 발생 하는 워크플로 디자이너" 텍스트가 워크플로 로드 실패 원인이 된 예외 정보와 함께 디자이너 화면에 나타납니다. 일반적으로 이 오류는 XAML 파일의 구문을 분석할 수 없는 경우에 발생합니다.