---
title: "찾아보기 및.NET 유형 선택 대화 상자 (레거시) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.ComponentModel.Design.TypeBrowserDialog.UI
helpviewer_keywords:
- Browse and Select a .NET Type dialog box
ms.assetid: 1e66c9bc-94b2-46e2-bedf-871752e5f917
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 3cdc5d3928cd436d86d529e667f99251e1e7cc95
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="browse-and-select-a-net-type-dialog-box-legacy"></a>.NET 유형 선택 대화 상자(레거시)
이 항목에서는 설명 방법을 사용 하 여는 **.NET 유형 선택** 레거시 Windows 워크플로 디자이너의 대화 상자. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

 에 **속성** 창에서 참조 된 어셈블리는 줄임표에.NET Framework 형식을 사용 하는 속성을 선택 하면 **[...]**  속성의 텍스트 상자 끝에 나타납니다. 클릭 하 고 **[...]**  열립니다는 **.NET 유형 선택** 대화 상자. 이 대화 상자에서 참조된 어셈블리의 트리 뷰에서 형식을 선택할 수 있습니다. 예를 들어 때 사용할 활동 디자이너에는 **속성** 창 클릭는 **기본 클래스** 줄임표 **[...]**  참조 된 어셈블리 트리에서 활동에 대 한 다른 기본 클래스를 선택할 수 있습니다.

 다음 표에 사용자 인터페이스 (UI) 요소는 **.NET 유형 선택** 대화 상자.

|UI 요소|설명|
|----------------|-----------------|
|**유형 이름:**|현재 선택한 형식의 이름입니다.|
|**Type**|왼쪽 창에는 참조된 어셈블리의 트리 뷰가 나타나고, 오른쪽 창에는 왼쪽 창에서 선택한 참조된 어셈블리 선택 항목에 대해 사용 가능한 형식이 표시됩니다.|

## <a name="see-also"></a>참고 항목

- [레거시 활동 디자이너 사용](../workflow-designer/using-the-legacy-activity-designer.md)