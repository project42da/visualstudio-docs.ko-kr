---
title: Bookmark 컨트롤 | Microsoft Docs
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Bookmark
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- bookmarks, controlling
- Bookmark control, data binding
- Bookmark control, events
- Bookmark control
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 68934d202fbffc162b6888ab3a45cdf0b7fd439d
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="bookmark-control"></a>Bookmark 컨트롤
  <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 고유한 이름이 있고 이벤트를 노출하며 데이터에 바인딩될 수 있는 책갈피입니다. 책갈피는 Microsoft Office Word 문서에서 항목 또는 위치를 표시하는 자리 표시자로 사용할 수 있습니다. <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 <xref:Microsoft.Office.Interop.Word.Bookmark> 개체 및 <xref:Microsoft.Office.Interop.Word.Range> 개체의 조합입니다.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 문서 수준 프로젝트에서는 디자인 타임 또는 런타임에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 문서에 추가할 수 있습니다. VSTO 추가 기능 프로젝트에서는 런타임에 열려 있는 임의 문서에 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 추가할 수 있습니다. 자세한 내용은 [방법: Word 문서에 책갈피 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)을 참조하세요.

## <a name="binding-data-to-the-control"></a>컨트롤에 데이터 바인딩
 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤은 단순 데이터 바인딩을 지원합니다. 책갈피는 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> 속성을 사용하여 데이터 원본에 바인딩해야 합니다. 책갈피의 기본 데이터 바인딩 속성은 <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> 속성입니다.

 바인딩된 데이터 집합의 데이터가 업데이트 되는 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤 변경 내용을 표시 합니다.

 문서 수준 프로젝트에서 **데이터 원본** 창을 사용하여 데이터를 책갈피에 바인딩할 수 있습니다. 자세한 내용은 [How to: Populate Documents with Data from Objects](../vsto/how-to-populate-documents-with-data-from-objects.md)을 참조하십시오.

## <a name="formatting"></a>서식
 <xref:Microsoft.Office.Interop.Word.Bookmark> 에 적용할 수 있는 서식은 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 적용할 수 있습니다. 이 서식 글꼴, 들여쓰기, 간격, 번호 매기기 및 스타일이 포함 됩니다.

## <a name="assigning-text-to-the-bookmark"></a>책갈피에 텍스트 할당
 간의 추가 차이점은 <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> 개체 및 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> 컨트롤은 텍스트가 책갈피에 할당 될 때 동작 하는 방법입니다. 텍스트를 길이가 0 인 할당 <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType>, 책갈피의 오른쪽에 추가 되 고 길이가 0으로 유지 됩니다. 그러나 텍스트를 길이가 0 인 할당 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType>, 텍스트를 책갈피에 삽입 됩니다 및 고 책갈피 길이 삽입 된 문자의 총 수로 확장 됩니다.

 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> 컨트롤에는 <xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType> 속성입니다. 이 속성은 다른는 <xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType> 속성에서 사용할 수 있는 <xref:Microsoft.Office.Tools.Word.Bookmark.Range?displayProperty=nameWithType> 속성의는 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> 컨트롤 또는 <xref:Microsoft.Office.Interop.Word.Bookmark.Range?displayProperty=nameWithType> 의 속성은 <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> 개체입니다.

|Text 속성|설명|
|-------------------|-----------------|
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType>|이 속성을 사용하여 텍스트를 책갈피 안에 표시하고 문서에 책갈피를 남겨 둡니다. 텍스트를 책갈피에 할당하면 책갈피 범위를 확장하고 책갈피를 삭제하지 않습니다.<br /><br /> 예를 들어 `Bookmark1.Text = "Hello world"` 는 텍스트를 책갈피에 삽입하고 책갈피를 그대로 둡니다.|
|<xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType>|이 속성을 사용하여 책갈피 위치에 텍스트를 표시하고 책갈피를 자동으로 삭제합니다. 예를 들어 `Bookmark1.Range.Text = "Hello world"` 는 책갈피에 텍스트를 삽입하고 책갈피를 삭제합니다.|

## <a name="renaming-the-control-at-design-time"></a>디자인 타임에 컨트롤 이름 바꾸기
 문서 수준 프로젝트에서 <xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤을 **도구 상자** 에서 문서로 끌어 놓으면 Visual Studio가 자동으로 컨트롤의 이름을 생성합니다. **속성** 창에서 컨트롤의 이름을 변경할 수 있습니다.

## <a name="overlapping-controls"></a>컨트롤 겹침
 책갈피 컨트롤은 서로 겹칠 수 있습니다. 동일한 텍스트를 둘 이상의 책갈피에서 공유할 수 있습니다. 겹치는 책갈피 중 하나에 새 텍스트를 할당 하면 새 텍스트만 포함 및 책갈피가 더 이상 겹치지 않게 합니다. 이제 다른 책갈피는 원래 겹치는 책갈피 간에 공유 되지 않은 텍스트만을 포함 합니다.

 다음 표는 "This is sample text." 문장이 두 개의 겹치는 책갈피에서 공유 됩니다.

|책갈피|텍스트|
|--------------|----------|
|겹치는 책갈피|[this is {sample] text.}|
|책갈피1|This is sample|
|책갈피2|sample text.|

 새 텍스트 "This is replacement."를 Bookmark1, 하는 책갈피 겹치지 않는지 Bookmark2 Bookmark1의 원래 없었던 텍스트만 유지 합니다.

|책갈피|텍스트|
|--------------|----------|
|별도의 두 책갈피|[this is replacement]{ text.}|
|책갈피1|This is replacement|
|책갈피2|text.|

다른 책갈피를 포함 하는 책갈피의 텍스트를 변경 하는 경우 내부 책갈피는 삭제 되지 않습니다. 그러나 내부 책갈피는 빈 책갈피가 및 외부 책갈피 끝으로 이동 합니다.

다음 표는 "This is sample text." 문장이 다른 책갈피 내에 포함 된 책갈피에서 공유 됩니다.

|책갈피|텍스트|
|--------------|----------|
|겹치는 책갈피|[this is {sample} text.]|
|책갈피1|This is sample text.|
|책갈피2|sample|

 새 텍스트 "This is replacement."를 책갈피1에 할당하는 경우 책갈피가 더 이상 겹치지 않고 책갈피2는 책갈피1의 끝에 있는 빈 책갈피가 됩니다.

|책갈피|텍스트|
|--------------|----------|
|별도의 두 책갈피|[대체 되었습니다.]{}|
|책갈피1|This is replacement.|
|책갈피2|*\<빈 >*|

## <a name="events"></a>이벤트

<xref:Microsoft.Office.Tools.Word.Bookmark> 컨트롤에 대해 다음 이벤트를 사용할 수 있습니다.

-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeDoubleClick>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.BindingContextChanged>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.Deselected>

-   <xref:System.ComponentModel.IComponent.Disposed>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.Selected>

-   <xref:Microsoft.Office.Tools.Word.Bookmark.SelectionChange>

## <a name="see-also"></a>참고자료

- [Automating Word by Using Extended Objects](../vsto/automating-word-by-using-extended-objects.md)
- [방법: Word 문서에 Bookmark 컨트롤 추가](../vsto/how-to-add-bookmark-controls-to-word-documents.md)
- [연습: 책갈피에 대한 바로 가기 메뉴 만들기](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)
- [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)
- [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)