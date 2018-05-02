---
title: Visual Studio에서 코딩된 UI 테스트를 사용하여 SharePoint 응용 프로그램 테스트
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 5a23ed3a56c0d4b8daf8086e07ae04206c52ac4a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="test-sharepoint-applications-with-coded-ui-tests"></a>코딩된 UI 테스트를 사용하여 SharePoint 응용 프로그램 테스트

SharePoint 응용 프로그램에 코딩된 UI 테스트를 포함하면 해당 UI 컨트롤을 포함해서 전체 응용 프로그램이 올바르게 작동하는지 확인할 수 있습니다. 코딩된 UI 테스트는 또한 사용자 인터페이스에서 값 및 논리의 유효성을 검사할 수 있습니다.

코딩된 UI 테스트를 사용하는 혜택에 대한 자세한 내용은 [UI 자동화를 사용하여 코드 테스트](../test/use-ui-automation-to-test-your-code.md)를 참조하세요.

**요구 사항**

- Visual Studio Enterprise

## <a name="create-a-coded-ui-test-for-a-sharepoint-app"></a>SharePoint 응용 프로그램에 대해 코딩된 UI 테스트 만들기

SharePoint 응용 프로그램에 대한[코딩된 UI 테스트 만들기](../test/use-ui-automation-to-test-your-code.md) 는 다른 유형의 응용 프로그램에 대해 테스트 만들기와 동일합니다. 기록 및 재생은 웹 편집 인터페이스의 모든 컨트롤에 대해 지원됩니다. 범주 및 웹 파트 선택 인터페이스는 모두 표준 웹 컨트롤입니다.

![SharePoint 웹 파트](../test/media/cuit_sharepoint.png)

> [!NOTE]
> 작업을 기록하는 경우 코드를 생성하기 전에 작업의 유효성을 검사합니다. 마우스로 가리키기와 관련해서는 몇 가지 동작이 있으므로 기본적으로 설정됩니다. 코딩된 UI 테스트에서 중복된 위로 가져가기는 제거할 때 주의가 필요합니다. 이렇게 하려면 테스트에 대한 코드를 편집하거나 [코딩된 UI 테스트 편집기](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)를 사용합니다.

## <a name="test-office-controls-within-a-sharepoint-app"></a>SharePoint 앱 내에서 Office 컨트롤 테스트

SharePoint 응용 프로그램에서 일부 Office 웹 파트에 대해 자동화를 설정하려면 코드를 약간 수정해야 합니다.

> [!NOTE]
> SharePoint 응용 프로그램에서 Visio 및 PowerPoint 컨트롤 테스트는 지원되지 않습니다.

### <a name="excel-cell-controls"></a>Excel 셀 컨트롤

Excel 셀 컨트롤을 포함하려면 코딩된 UI 테스트의 코드에서 일부 항목을 변경해야 합니다.

> [!WARNING]
> 화살표 작업 후 Excel 셀에 텍스트를 입력하는 작업은 올바르게 기록되지 않습니다. 마우스를 사용해서 셀을 선택하세요.

빈 셀에 대한 작업을 기록할 때는 셀을 두 번 클릭하고 텍스트 설정 작업을 수행하여 코드를 수정해야 합니다. 셀을 클릭하고 키보드 작업을 수행하면 셀 내에서 `textarea` 가 활성화되기 때문에 이 작업이 필요합니다. 빈 셀에서 단순히 `setvalue` 를 기록하면 셀을 클릭할 때까지 제공되지 않은 `editbox` 가 검색됩니다. 예:

```csharp
Mouse.DoubliClick(uiItemCell,new Point(31,14));
uiGridKeyboardInputEdit.Text=value;
```

비어 있지 않은 셀에서 작업을 기록할 때는 셀에 텍스트를 입력하는 순간 셀의 자식으로 새로운 \<div> 컨트롤이 추가되기 때문에 기록이 조금 더 복잡해집니다. 새로운 \<div> 컨트롤에는 사용자가 방금 입력한 텍스트가 포함됩니다. 레코더는 새로운 \<div> 컨트롤에서 작업을 기록해야 하지만 테스트를 입력할 때까지는 새로운 \<div> 컨트롤이 존재하지 않기 때문에 그렇게 할 수 없습니다. 이 문제를 해결하기 위해서는 다음과 같이 코드를 직접 변경해야 합니다.

1. 셀 초기화로 이동하고 `RowIndex` 및 `ColumnIndex` 를 주 속성으로 지정합니다.

    ```csharp
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";
    ```

2. 셀의 `HtmlDiv` 자식을 찾습니다.

    ```csharp
    private UITestControl getControlToDoubleClick(HtmlCell cell)
    {
         if (String.IsNullOrEmpty(cell.InnerText)) return cell;
         HtmlDiv pane = new HtmlDiv(cell);
         pane.FilterProperties[HtmlDiv.PropertyNames.InnerText] = cell.InnerText;
         // Class is an important property in finding pane
         pane.FilterProperties[HtmlDiv.PropertyNames.Class] = "cv-nwr";
         UITestControlCollection panes = pane.FindMatchingControls();
         return panes[0];
    }
    ```

3. `HtmlDiv`에서 마우스 두 번 클릭 작업에 대한 코드를 추가합니다.

    ```csharp
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )
    ```

4. `TextArea`에서 텍스트를 설정하는 코드를 추가합니다.

    ```csharp
    uIGridKeyboardInputEdit.Text = value; }
    ``

## See also

- [Use UI Automation To Test Your Code](../test/use-ui-automation-to-test-your-code.md)
- [Create SharePoint Solutions](/office-dev/office-dev/create-sharepoint-solutions)
- [Verifying and Debugging SharePoint Code](/office-dev/office-dev/verifying-and-debugging-sharepoint-code)
- [Building and Debugging SharePoint Solutions](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)
- [Profiling the Performance of SharePoint Applications](/office-dev/office-dev/profiling-the-performance-of-sharepoint-applications)
