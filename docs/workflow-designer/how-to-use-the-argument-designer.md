---
title: '방법: 인수 디자이너를 사용 하 여 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5f4af6e06bbebe3f543deed68ff85f4cd0a39be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-the-argument-designer"></a>방법: 인수 디자이너 사용
이전 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 버전과 비교할 때 인수 디자이너에서 데이터를 활동에서/으로 전달하기가 쉬워졌습니다. 클릭 하 여 액세스 하는 디자이너는 **인수** 디자인 캔버스의 왼쪽 아래 모퉁이의 단추입니다. 제외 하 고 각각의 열 머리글을 하 여 정렬할 수 있고 테이블 형식으로 표시 되는 인수 목록이 있는 **기본값** 열입니다. 각 인수에는 이름, in/out/in-out/속성 방향, 형식 및 기본 식 값(있는 경우)이 포함됩니다. 이름 및 기본 식 값은 편집할 수 있는 텍스트 필드이며, 형식과 방향은 드롭다운입니다. 자세한 내용은 참조 [변수 및 인수 (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)합니다.

### <a name="to-create-a-new-argument"></a>새 인수를 만들려면

1.  [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]에서 워크플로 또는 활동 솔루션을 엽니다.

2.  클릭 하 여 인수 디자이너를 열고는 **인수** 디자인 캔버스의 왼쪽 아래 모퉁이의 단추입니다. 인수 디자이너가 나타납니다.

3.  라는 빈 행을 클릭 **인수 만들기**합니다. 이 다음과 같은 기본값을 사용 하는 새 인수를 가진 새 행이 추가 됩니다:에 대 한 argumentx는 **이름** 여기서 x는 정수 초기 값이 고유한 인수 이름을 만들기 위해 자동으로 증가 하는 1 이며 **에**  에 대 한는 **방향**, 및 **문자열** 에 대 한는 **인수 형식이**합니다. 값 없음에 대 한 추가 됩니다 **기본값**합니다. 워크플로 디자인 프로세스 중 언제라도 이러한 값을 변경할 수 있습니다.

    > [!NOTE]
    > 인수를 삭제 하려면 클릭 하 여 인수를 선택 하 고 다음 키를 누릅니다는 **삭제** 키입니다.

## <a name="see-also"></a>참고자료

- [워크플로 디자이너 사용](../workflow-designer/using-the-workflow-designer.md)
- [변수 및 인수](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)