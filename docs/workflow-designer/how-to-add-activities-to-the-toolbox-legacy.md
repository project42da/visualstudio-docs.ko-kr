---
title: '방법: 도구 상자 (레거시)에 활동 추가 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Toolbox, adding activities
- activities, adding to Toolbox
ms.assetid: b66ea29c-120b-40ba-8a61-c1c8240850fa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 779735cb1d163db9e7b05e2892d01a991a4a4c2c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-activities-to-the-toolbox-legacy"></a>방법: 도구 상자에 활동 추가(레거시)
대상으로 하는 레거시 Windows 워크플로 디자이너로 워크플로 솔루션을 빌드하는 경우는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)], 사용자 지정 활동을 워크플로 프로젝트에 추가할 수 있습니다 및 해당 디자이너에 배치 된 **도구 상자** 에 대 한 쉽게 액세스할 수 있습니다. 작업을 직접 추가할 수도 수는 **도구 상자** 동적 연결 라이브러리 (DLL)입니다.

### <a name="to-add-an-activity-to-the-toolbox-from-a-dll"></a>DLL에서 도구 상자에 활동을 추가하려면

1.  아래에서 도구 상자 창 화면을 마우스 오른쪽 단추로 클릭 **Windows Workflow**, 클릭 하 고 **항목 선택**합니다.

2.  에 **도구 상자 항목 선택** 대화 상자를 클릭는 **System.Activities 구성 요소** 탭을 클릭 한 다음 **찾아보기** 창의 오른쪽 아래에서 합니다.

3.  에 추가할 사용자 지정 활동의 구현이 포함 된 파일 디렉터리에서 DLL을 선택 된 **도구 상자**, 클릭 하 고 **열려**합니다.

4.  클릭 **확인** 도구 상자에 활동 추가 작업을 마칩니다.

## <a name="see-also"></a>참고자료

- [레거시 활동 디자이너 사용](../workflow-designer/using-the-legacy-activity-designer.md)
- [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)