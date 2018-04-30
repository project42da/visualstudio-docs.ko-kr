---
title: XAML 디자이너 에서 컨트롤을 삽입하고 해당 동작을 수정
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: e2ec53e78bc88e18d9ba8e77aa888ffa855b64ea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>XAML 디자이너 에서 컨트롤을 삽입하고 해당 동작을 수정

컨트롤을 사용하면 사용자가 앱과 상호 작용할 수 있습니다. 컨트롤을 사용하여 정보를 수집하고 개체에 애니메이션 효과를 적용하고 데이터 소스를 쿼리하는 등 여러 동작을 수행할 수 있습니다.

## <a name="add-controls-to-the-artboard"></a>아트보드에 컨트롤 추가

컨트롤을 **자산** 패널에서 **아트보드**로 끌어와 **속성** 창에서 수정할 수 있습니다.

![Blend 자산 탭 컨트롤](../designers/media/blend_assetsflipview_xaml.png)

### <a name="make-a-control-out-of-an-image-shape-or-path"></a>이미지, 도형 또는 패스를 컨트롤로 만들기

모든 개체를 컨트롤로 만들 수 있습니다.

![Blend - 컨트롤로 만들기 대화 상자](../designers/media/blend_makeintocontrol_xaml.png)

예를 들어, 페이지의 가운데에 텔레비전 그림이 있다고 가정해 보세요. 텔레비전 단추처럼 보이는 작은 이미지를 컨트롤로 만들 수 있습니다. 그런 다음 사용자가 이 단추를 클릭하여 채널을 변경할 수 있습니다.

이 작업은 단추가 이제 컨트롤이기 때문에 가능합니다. 컨트롤을 사용하면 사용자 상호 작용에 응답할 수 있습니다. 이 경우 사용자가 단추를 클릭했습니다.

컨트롤을 만들려면 개체를 선택합니다. 그런 다음 **도구** 메뉴에서 **컨트롤 만들기**를 클릭합니다.

## <a name="make-controls-do-things"></a>작업을 수행하는 컨트롤 만들기

컨트롤은 사용자가 상호 작용하는 경우 작업을 수행할 수 있습니다. 예를 들어 컨트롤은 애니메이션 효과를 적용하고 데이터 소스를 업데이트하거나 비디오를 재생할 수 있습니다.

*트리거*, *동작*및 *이벤트* 를 사용하여 컨트롤이 작업을 수행하도록 합니다.

### <a name="triggers"></a>트리거

*트리거* 는 속성을 변경하거나 이벤트에 응답하여 작업을 수행하거나 다른 속성의 변경을 수행합니다. 예를 들어, 사용자가 마우스로 가리킬 때 단추의 색을 변경할 수 있습니다.

!["트리거" 패널](../designers/media/custom_button_blend_propertytriggerinfo.png)

### <a name="behaviors"></a>동작

*동작* 은 다시 사용할 수 있는 코드 패키지로, 속성 변경 이외의 작업도 수행할 수 있습니다. 데이터 서비스 쿼리 등과 같은 작업을 수행할 수 있습니다. Blend에는 몇 가지 동작 모음이 기본 제공되며, 더 추가할 수 있습니다. 동작을 아트보드의 개체로 끌어와 속성을 설정하여 동작을 사용자 지정합니다.

![속성 패널의 FluidMoveBehavior](../designers/media/b4_fluidmovebehaviorproperties_sample.png)

**비디오 보기:** ![재생 아이콘](../designers/media/bldadminconsoleinitialconfigicon.PNG) [Blend 팁: 동작 사용 소개 1부](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904).

### <a name="events"></a>이벤트

유연성을 최대화하기 위해 *이벤트*를 처리합니다. 일부 코드를 작성해야 합니다.