---
title: Visual Studio의 일반 컨트롤 패턴 | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2017
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3e893949-6398-42f1-9eab-a8d8c2b7f02d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8383537a7e9d49f79e98da4dd95a3474803315d8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="common-control-patterns-for-visual-studio"></a>Visual Studio의 일반 컨트롤 패턴
##  <a name="BKMK_CommonControls"></a> 공용 컨트롤  
  
### <a name="overview"></a>개요  
공용 컨트롤 대부분의 Visual Studio의 사용자 인터페이스를 구성 합니다. Visual Studio 인터페이스에 사용 되는 가장 일반적인 컨트롤 따라야는 [Windows 데스크톱 상호 작용 지침](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)합니다. 이 항목은 Visual Studio에 국한 되며 이러한 Windows 지침을 확대 하는 정보 또는 특수 한 상황에 설명 합니다.  
  
#### <a name="common-controls-in-this-topic"></a>이 항목의 공용 컨트롤  
  
-   [스크롤 막대](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_Scrollbars)  
  
-   [입력된 필드](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_InputFields)  
  
-   [콤보 상자 및 드롭다운 목록](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ComboBoxesAndDropDowns)  
  
-   [확인란](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CheckBoxes)  
  
-   [라디오 단추](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_RadioButtons)  
  
-   [그룹 프레임](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_GroupFrames)  
  
-   [텍스트 컨트롤](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
-   [단추, 하이퍼링크](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
-   [트리 뷰](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TreeViews)  
  
#### <a name="visual-style"></a>비주얼 스타일  
컨트롤 스타일 지정 시 고려해 야 할 첫 번째 사항은 테마 UI에서는 컨트롤 사용 여부입니다. 표준 UI 컨트롤은 테마 UI 되며 따라야 [표준 Windows 바탕 화면 스타일](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx), 즉 이러한 re 템플릿이 아닌 되 고 기본 컨트롤 모양에 표시 되어야 합니다.  
  
-   **표준 (유틸리티) 대화 상자:** 테마가 적용 되지 않습니다. 템플릿을 다시 만들면 하지 않습니다. 기본 컨트롤 스타일 기본값을 사용 합니다.  
  
-   **도구 창, 문서 편집기, 디자인 화면 및 테마가 지정 된 대화 상자:** 색 서비스를 사용 하 여 특수 테마 모양을 사용 합니다.  
  
###  <a name="BKMK_Scrollbars"></a> 스크롤 막대  
 스크롤 막대 따라야 [Windows에 대 한 일반적인 상호 작용 패턴 스크롤 막대](https://msdn.microsoft.com/en-us/library/windows/desktop/bb787527\(v=vs.85\).aspx) 코드 편집기에서와 같이 콘텐츠 정보를 보강 하는 이러한, 하지 않는 한 합니다.  
  
###  <a name="BKMK_InputFields"></a> 입력된 필드  
 일반적인 상호 작용 동작에 따라는 [텍스트 상자에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742442\(v=vs.85\).aspx)합니다.  
  
#### <a name="visual-style"></a>비주얼 스타일  
  
-   입력된 필드는 유틸리티 대화 상자에서 스타일이 지정 하지 않아야 합니다. 기본 스타일을 컨트롤에 내장 함수 사용.  
  
-   테마가 지정 된 입력된 필드는 테마가 지정 된 대화 상자와 도구 창에만 사용 해야 합니다.  
  
#### <a name="specialized-interactions"></a>특수 한 상호 작용  
  
-   읽기 전용 필드에는 기본 (활성) 전경 있지만 회색 (비활성) 백그라운드를 갖습니다.  
  
-   필드 있어야 하는 데 필요한  **\<필요한 >** 그 안에서 마찬가지로 워터 마크입니다. 드문 경우에서를 제외 하 고 배경색을 변경 하지 마십시오.  
  
-   유효성 검사 오류: 참조 [알림 및 Visual Studio에 대 한 진행률](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)  
  
-   입력된 필드에 표시 된 창의 너비를 적합 하지 나 임의로 경로 같은 긴 필드의 길이 일치 하는 내용에 맞게 크기를 조정 하 합니다. 길이 필드에서 허용 문자 수에 대 한 제한 사항의 사용자에 게 표시 수도 있습니다.  
  
     ![잘못 된 입력된 필드 길이: 한 이름은 긴 것이 거의있지 않습니다. ] (../../extensibility/ux-guidelines/media/0707-01_incorrectinputfieldcontrol.png "0707 01_IncorrectInputFieldControl")<br />잘못 된 입력된 필드 길이: 한 이름은 긴 것이 거의있지 않습니다.
  
     ![입력된 필드 길이 수정: 입력된 필드는 예상 되는 콘텐츠에 대 한 적절 한 너비입니다. ] (../../extensibility/ux-guidelines/media/0707-02_correctinputfieldcontrol.png "0707 02_CorrectInputFieldControl")<br />입력된 필드 길이 수정: 입력된 필드는 예상 되는 콘텐츠에 대 한 적절 한 너비입니다.
  
###  <a name="BKMK_ComboBoxesAndDropDowns"></a> 콤보 상자 및 드롭다운 목록  
일반적인 상호 작용 동작에 따라는 [드롭 다운 목록 및 콤보 상자에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742404\(v=vs.85\).aspx)합니다.  
  
#### <a name="visual-style"></a>비주얼 스타일  
  
-   유틸리티 대화 상자에서 템플릿을 다시 만들면 컨트롤이 없습니다. 기본 스타일을 컨트롤에 내장 함수 사용.  
  
-   테마 UI에서는 콤보 상자 및 드롭다운 컨트롤에 대 한 표준 테마를 따릅니다.  
  
#### <a name="layout"></a>레이아웃  
콤보 상자 및 드롭다운에 표시 된 창의 너비를 적합 하지 나 임의로 경로 같은 긴 필드의 길이 일치 하는 내용에 맞게 조정 해야.  
  
![: 잘못 된 드롭 다운 너비에 비해 너무 길면 표시 되는 콘텐츠. ] (../../extensibility/ux-guidelines/media/0707-03_incorrectdropdownlayout.png "0707 03_IncorrectDropDownLayout")<br />: 잘못 된 드롭 다운 너비에 비해 너무 길면 표시 되는 콘텐츠.
  
![올바른: 드롭 다운 번역 증가 대 한 허용 하 긴 하지 불필요 하 게 조정 됩니다. ] (../../extensibility/ux-guidelines/media/0707-04_correctdropdownlayout.png "0707 04_CorrectDropDownLayout")<br />올바른: 드롭 다운 번역 증가 대 한 허용 하 긴 하지 불필요 하 게 조정 됩니다. 
  
###  <a name="BKMK_CheckBoxes"></a> 확인란  
일반적인 상호 작용 동작에 따라는 [확인란에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742401\(v=vs.85\).aspx)합니다.  
  
#### <a name="visual-style"></a>비주얼 스타일  
  
-   유틸리티 대화 상자에서 템플릿을 다시 만들면 컨트롤이 없습니다. 기본 스타일을 컨트롤에 내장 함수 사용.  
  
-   테마 UI에서는 확인란 컨트롤에 대 한 표준 테마를 따릅니다.  
  
#### <a name="specialized-interactions"></a>특수 한 상호 작용  
  
-   확인란 상호 작용 하지는 대화 상자를 표시 하거나 다른 영역으로 이동 해야 합니다.  
  
-   확인란 텍스트의 첫 번째 줄의 기준선을 맞춥니다.  
  
     ![: 잘못 된 확인란 가운데에 표시 됩니다는 텍스트입니다. ] (../../extensibility/ux-guidelines/media/0707-05_incorrectcheckboxalign.png "0707 05_IncorrectCheckBoxAlign")<br />: 잘못 된 확인란 가운데에 표시 됩니다는 텍스트입니다.
  
     ![올바른: 확인란 텍스트의 첫 번째 줄으로 정렬 됩니다. ] (../../extensibility/ux-guidelines/media/0707-06_correctcheckboxalign.png "0707 06_CorrectCheckBoxAlign")<br />올바른: 확인란 텍스트의 첫 번째 줄으로 정렬 됩니다.
  
###  <a name="BKMK_RadioButtons"></a> 라디오 단추  
일반적인 상호 작용 동작에 따라는 [라디오 단추에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742436\(v=vs.85\).aspx)합니다.  
  
#### <a name="visual-style"></a>비주얼 스타일  
유틸리티 대화 상자에서 스타일 라디오 단추 하지 않습니다. 기본 스타일을 컨트롤에 내장 함수 사용.  
  
#### <a name="specialized-interactions"></a>특수 한 상호 작용  
긴밀 하 게 레이아웃에 그룹 구분을 유지 하기 위해 필요한 경우가 아니면 그룹 프레임을 묶는 라디오 선택 옵션을 사용 하려면 필요는 없습니다.  
  
###  <a name="BKMK_GroupFrames"></a> 그룹 프레임  
일반적인 상호 작용 동작에 따라는 [그룹 프레임에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742405\(v=vs.85\).aspx)합니다.  
  
#### <a name="visual-style"></a>비주얼 스타일  
유틸리티에서 대화 상자, 그룹 프레임 스타일을 하지 않습니다. 기본 스타일을 컨트롤에 내장 함수 사용.  
  
#### <a name="layout"></a>레이아웃  
  
-   긴밀 하 게 레이아웃에 그룹 구분을 유지 하기 위해 필요한 경우가 아니면 그룹 프레임을 묶는 라디오 선택 옵션을 사용 하려면 필요는 없습니다.  
  
-   단일 컨트롤에 대 한 그룹 프레임을 사용 하지 마십시오.  
  
-   경우에 따라 그룹 프레임 컨테이너 대신 가로 규칙을 사용 하는 것이 좋습니다.  
  
##  <a name="BKMK_TextControls"></a> 텍스트 컨트롤

### <a name="static-text-fields"></a>정적 텍스트 필드

정적 텍스트 필드는 읽기 전용 정보를 제공 및 사용자가 선택할 수 없습니다. 사용자가 클립보드에 복사 하려는 모든 텍스트에 대 한 사용 하지 마십시오. 그러나 읽기 전용 정적 텍스트 상태의 변경 내용을 반영 하도록 변경할 수 있습니다. 그 위에 루트 Namespace 텍스트 상자에 변경 내용을 반영 하려면 정보 그룹 변경 내용 아래에 있는 출력 이름은 정적 텍스트 아래 예제에서는 합니다.

정적 텍스트 정보를 표시 하는 방법은 두 가지가 있습니다.

정적 텍스트 경우에는 포함 하지 않고 대화 상자에서 자체에 충돌 하지 않는 그룹화 될 수 있습니다. 상자에 추가 줄은 반드시 필요한 경우를 결정 합니다. 예는 아래와 같이 표시 되는 그룹 선으로 만든 섹션 아래의 디렉터리 경로.  

![텍스트 컨트롤에 정적 텍스트 정보](../../extensibility/ux-guidelines/media/DisplayingStaticText.png "DisplayingStaticText.png")<br />텍스트 컨트롤에 정적 텍스트 정보

여기서 다른 그룹화 된 영역에 존재 하 고 정보에 포함 되는 가독성을 위해 도움이 될 대화 상자에서 섹션 수 숨기 거 나 표시 시기 및 (에서 같이 **속성 창** 설명 창) 또는 유사한 UI와 일치 해야 합니다 상자 안에 정적 텍스트를 배치 합니다. 이 그룹 상자 단일 규칙은 이어야 하며 색으로 지정 된는 `ButtonShadow`:

![속성 창에서 정적 텍스트](../../extensibility/ux-guidelines/media/PropertiesWindow.png "PropertiesWindow.png")<br />속성 창에서 정적 텍스트

### <a name="read-only-text-box"></a>읽기 전용 텍스트 상자

그러면 사용자가 필드 내의 텍스트 선택 있지만 편집할 수 없습니다. 이 텍스트 상자와 일반적인 3 차원 끌으로 경계가 `ButtonShadow` 채우기입니다.

텍스트 상자가 활성화 될 수 사용자 선택을 확인/취소 확인란 또는 라디오 단추를 선택/선택 취소 하 같은 연결된 된 컨트롤을 변경 하는 경우 (편집). 예를 들어,는 **도구 &gt; 옵션** 아래 표시 된 페이지는 **홈 페이지** 때 텍스트 상자가 활성화 되는 **기본값 사용** 확인란이 선택 되어 있습니다.

![읽기 전용 텍스트 상자에는 비활성 및 활성 상태로](../../extensibility/ux-guidelines/media/ReadOnlyTextBox.png "ReadOnlyTextBox.png")<br />읽기 전용 텍스트 상자에는 비활성 및 활성 상태

### <a name="using-text-in-dialogs"></a>대화 상자에서 텍스트를 사용 하 여

대화 상자에서 텍스트에 대 한 핵심 지침:

-   텍스트 상자, 목록 상자 및 unthemed 대화 상자에 프레임에 대 한 레이블을 동사와 시작, 초기 자본이에 첫 번째 단어만 있고 콜론으로 끝나야 합니다.

    > 테마가 지정 된 대화 상자에 텍스트 컨트롤에 따라 [Windows 데스크톱 UX 관련 지침](https://msdn.microsoft.com/library/windows/desktop/dn742479.aspx) 및 도움말 링크에 물음표를 제외 하 고 끝 문장 부호를 사용 하지 않습니다.

-   옵션 단추 및 확인란에 대 한 레이블을 첫 번째 단어에는 초기 자본이 동사의 시작 하며 끝 문장 부호 없음.

-   문자가 대문자 각 단어 (제목 경우)에 있어야 하는 단추, 메뉴, 메뉴 항목 및 탭에 대 한 레이블.

-   레이블 용어는 다른 대화 상자에서 유사한 레이블에와 일치 해야 합니다.

-   가능 하면 쓰거나 구현에 대 한 개발자에 게 전달 되기 전에 텍스트 승인 기록기/편집기가 있습니다.

-   모든 컨트롤은 특수 한 경우에서를 제외 하 고 레이블이 있으면 어떤 탭 이동에 것으로 충분 합니다.
적절 한 경우 도우미 텍스트를 사용 합니다.

### <a name="helper-text"></a>도우미 텍스트

대화의 목적을 이해 하는 사용자 또는으로 수행할 작업을 나타내기 위해 대화 상자에 포함 되어 있습니다. 도우미 텍스트 사용할지 필요할 때만 간단한 대화 상자 복잡 하 게 만들지 않으려면 합니다. 도우미 텍스트의 두 가지 변형이 대화 상자 및 워터 마크입니다.

도우미 텍스트에 대 한 일반적인 위치 따르고 새로운 영역 소개에 주의 기울여야 합니다. 도우미 텍스트에 대 한 일반적인 시나리오입니다.

-   복잡 한 대화 상자와 상호 작용 하는 방법에 대 한 추가 방향에 게 대화 상자 도우미 텍스트입니다.

-   빈 도구 창 또는 대화 상자, 콘텐츠 표시 된 이유를 설명 하기 위해 워터 마크 텍스트입니다.

-   설명 창 맨 아래에 같은 **속성 창**합니다.

-   시작 하려면 사용자 수행할 동작을 설명 하기 위해 빈 편집기의 텍스트를 워터 마크입니다.
  
### <a name="dialog-helper-text"></a>대화 상자 도우미 텍스트

사용자 경험 디자이너 도우미 텍스트 적합 한지 결정 하는 데 도움이 됩니다. 디자이너는 일반적인 콘텐츠 뿐 아니라 도우미 텍스트가 표시 되는 위치를 정의할 수 있습니다. 사용자 지원 수 쓰기/편집 실제 텍스트입니다.

### <a name="watermarks"></a>워터 마크

대화 상자에서 약간 다른 워터 마크 지침 활용합니다. 대화 상자가 특히 많은 UI 요소 (레이블, 설명 텍스트, 단추 및 텍스트와 다른 컨테이너 컨트롤)을 사용 중 나타날 수 있기 때문에 검정색으로 표시 된 경우 워터 마크 띄게 진한 회색으로 (VSColor: `ButtonShadow`). 워터 마크 흰색 배경으로 목록 상자 같은 컨트롤 안에 표시 되는 일반적으로 (VSColor: `Window`).

-   진한 회색으로 표시 되는 텍스트 (VSColor: `ButtonShadow`). 그러나 중간 회색 또는 기타 색에 표시 되는 워터 마크 (VSColor: `ButtonFace`) 배경과 가독성에 대 한 관련, 검정 텍스트와 함께 (VSColor: `WindowText`).

-   워터 마크를 가운데 맞춤 또는 왼쪽 맞춤 수 있습니다. 맞춤을 내릴 때 표준 디자인 규칙을 적용 합니다. 배경에 워터 마크를 선택할 수 없습니다.

![워터 마크 텍스트 예](../../extensibility/ux-guidelines/media/WatermarkTextExample.gif)<br />워터 마크 텍스트 예

### <a name="context-specific-dynamic-text"></a>상황에 맞는 (동적) 텍스트

동적 텍스트 대화 상자 또는 모덜리스 UI의 두 가지 방법 중 하나만 사용된 될 수 있습니다: 동적 레이블 또는 동적 콘텐츠도 합니다.

-   동적 레이블: 동적 텍스트의 일반적인 용도와 같은 요소 및 오른쪽 표에 표시 된 요소에 대 한 속성의 목록을 포함 하는 대화 상자에서 선택한 항목에 대 한 자세한 정보를 제공 하는 설명이 포함 된 패널입니다. 속성은 눈금 레이블 왼쪽에 있는 항목을 선택 하면 오른쪽에 있는 표에서 해당 항목에 대 한 정보가 표시 되도록 동적 수 있습니다.

-   동적 텍스트: 위치를 이러한 방식으로 특정 정보 및 하지 일반 정보를 표시 해야 하지만 조화 주의 해야 하는 경우에 유용할 수 있습니다.

사용자가 정보를 복사 하는 기능을 사용 하도록 하려는 경우 동적 텍스트 읽기 전용 텍스트 필드에 있어야 합니다.
  
##  <a name="BKMK_ButtonsAndHyperlinks"></a> 단추, 하이퍼링크  
  
### <a name="overview"></a>개요  
단추 및 링크 컨트롤 (하이퍼링크) 따라야 [하이퍼링크에 대 한 기본 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742406\(v=vs.85\).aspx) 사용의 경우 용어를 조정 하 고 간격입니다.  
  
### <a name="choosing-between-buttons-and-links"></a>단추 및 링크 중에서 선택  
일반적으로 작업 단추 사용 되었 및 탐색을 위해 예약 된 하이퍼링크입니다. 단추를 사용 하 여 모든 경우에 수 있지만 링크의 역할 단추 및 링크는 보다 몇 가지 상황에서 서로 바꿀 수 있도록 Visual Studio에서 확장 되었습니다.  
  
명령 단추를 사용 하는 경우:  
  
-   기본 명령  
  
-   입력을 수집 하는 데 사용 되는 창 표시 또는 사항을 선택할 보조 명령 하는 경우에  
  
-   파괴적 이거나 되돌릴 수 없는 작업  
  
-   마법사와 페이지 흐름 내에서 커밋 단추  
  
도구 창의 명령 단추를 방지 또는 레이블에 대 한 두 개 이상의 단어가 필요 합니다. 링크는 레이블이 긴 있을 수 있습니다.  
  
 링크를 사용 하는 경우:  
  
-   다른 창, 문서, 또는 웹 페이지 탐색  
  
-   긴 레이블 또는 동작의 의도 설명 하기 위해 짧은 문장 해야 하는 상황  
  
-   작업은 파괴적 이거나 되돌릴 수 없는 단추는 UI를 가득 채울는 긴밀 하 게 공백을 제공  
  
-   취소가 강조 상황에서는 보조 명령 있는 많은 명령  
  
#### <a name="examples"></a>예제  
![다음 상태 메시지 정보 표시줄에 사용 된 연결 명령](../../extensibility/ux-guidelines/media/070703-01_commandlinkinfobar.png "070703 01_CommandLinkInfobar")<br />다음 상태 메시지 정보 표시줄에 사용 된 명령을 연결
  
![CodeLens 팝업에 사용 된 연결](../../extensibility/ux-guidelines/media/070703-02_linksincodelens.png "070703 02_LinksInCodeLens")<br />CodeLens 팝업에 사용된 링크
  
![여기서 단추에 영향을 줍니다 너무 많은 주의 보조 명령에 사용 되는 링크](../../extensibility/ux-guidelines/media/070703-03_linksassecondarycommands.png "070703 03_LinksAsSecondaryCommands")<br />여기서 단추에 영향을 줍니다 너무 많은 주의 보조 명령에 사용 된 연결
  
### <a name="common-buttons"></a>일반 단추  
  
#### <a name="text"></a>텍스트  
작성 지침에 따라 [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology)합니다.  
  
#### <a name="visual-style"></a>비주얼 스타일  
  
##### <a name="standard-unthemed"></a>표준 (unthemed)  
Visual Studio에서 대부분의 단추 유틸리티 대화 상자에 나타나고 스타일이 해야 합니다. 운영 체제에 의해 정의 된 대로 표준 단추 모양을 반영 해야 있습니다.  
  
##### <a name="themed"></a>테마  
경우에 따라 단추 스타일이 적용 된 UI 내에서 사용할 수 있으며 이러한 단추를 적절 하 게 스타일이 지정 해야 합니다. 참조 [대화 상자의](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs) 테마 컨트롤에 대 한 내용은 합니다.  
  
### <a name="special-buttons"></a>특수 단추  
  
#### <a name="browse-buttons"></a>찾아보기... 단추  
**[찾아보기...]**  단추는 표, 대화 상자, 및 도구 창 및 기타 모덜리스 UI 요소를 사용 합니다. 사용자 컨트롤에 값을 채우는 데 도움이 되는 선택을 표시 됩니다. 긴 흐름과 짧은이 단추의 두 가지 변형이 있습니다.  
  
![긴 [찾아보기...] 단추](../../extensibility/ux-guidelines/media/070703-04_browselong.gif "070703 04_BrowseLong")<br />긴 [찾아보기...] 단추
  
![줄임표 전용 짧은 [...] 단추](../../extensibility/ux-guidelines/media/070703-05_browseshort.gif "070703 05_BrowseShort")<br />줄임표 전용 짧은 [...] 단추
  
짧은 줄임표 전용 단추를 사용 하는 경우:  
  
-   긴 둘 이상 있는 경우 **[찾아보기...]**  검색을 위해 여러 필드를 허용 하는 경우와 같은 대화 상자에서 단추입니다. 에 대 한 단기를 사용 하 여 **[...]**  이러한 상황에서 만든 혼란 스러운 액세스 키를 방지 하기 위해 각 단추 (**& 찾아보기** 및 **& 찾아보기** 동일한 대화 상자에서).  
  
-   긴밀 하 게 대화 상자에서 또는 긴 단추에 적절 한 화면은 합니다.  
  
-   표 형태 컨트롤에 표시 하려면 단추 합니다.  
  
단추를 사용 하기 위한 지침:  
  
-   선택 키를 사용 하지 마십시오. 키보드를 사용 하 여에 액세스 하려면 사용자는 인접 한 컨트롤에서 탭 합니다. 탭 순서를 필드를 채울를 이후 즉시가 모든 찾아보기 단추 인지 확인 합니다. 첫 번째 기간 아래 밑줄을 사용 하지 마십시오.  
  
-   설정 된 활성 MSAA (Microsoft Accessibility) **이름** 속성을 **찾아보기...**  (줄임표)는 포함 하는 화면 하므로 판독기 읽기 "점-점-점" 또는 "기간-시간-기간" 없습니다 "찾아보기" 관리 되는 컨트롤에 대 한 설정을 즉는 **AccessibleName** 속성입니다.  
  
-   줄임표를 사용 하지 마십시오 **[...]**  찾아보기 동작을 제외 하 고에 대 한 단추입니다. 예를 들어, 필요한 경우는 **[새로 만들기...]**  단추 하지만 대화 상자를 다시 디자인 해야 합니다. 다음의 텍스트에 대 한 충분 한 공간이 없는 합니다.  
  
##### <a name="sizing-and-spacing"></a>크기 조정 및 간격  
![단추 [찾아보기...] 크기 조정: 표준 버전은 75 x 23 픽셀, 짧은 버전은 26 x 23 픽셀](../../extensibility/ux-guidelines/media/070703-06_browsesizing.png "070703 06_BrowseSizing")<br />[찾아보기...] 크기 조정 단추
  
![간격 [찾아보기...] 단추: 관련 컨트롤과 표준 찾아보기 단추 7 픽셀 사이 간격, 관련된 컨트롤이 간격과 짧은 찾아보기 단추 5 픽셀](../../extensibility/ux-guidelines/media/070703-07_browsespacing.png "070703 07_BrowseSpacing")<br />[찾아보기...] 간격 조정 단추
  
#### <a name="graphical-buttons"></a>단추 그래픽  
일부 단추는 항상 그래픽 이미지를 사용 하 고 공간을 절약 하 고 지역화 문제를 방지 하는 텍스트를 포함 하지 않습니다 해야 합니다. 이러한 필드 선택 및 다른 정렬 가능한 목록에 종종 사용 됩니다.  
  
> **참고:** 사용자 (키가 없거나 액세스)이이 단추를 탭,으로 붙여 구분이 가능한 순서에 따라 배치 해야 합니다. 지도 `name` 화면 판독기 단추 동작을 제대로 해석 하는 데 소요 되는 작업 하는 단추의 속성입니다.  
  
| 함수 | 단추 |  
| --- | --- |  
| 추가 | ![그래픽 "추가" 단추](../../extensibility/ux-guidelines/media/070703-08_buttonadd.png "070703 08_ButtonAdd") |
| 제거 | ![그래픽 "제거" 단추](../../extensibility/ux-guidelines/media/070703-09_buttonremove.png "070703 09_ButtonRemove") |
| 모두 추가 | ![그래픽 "모두 추가" 단추](../../extensibility/ux-guidelines/media/070703-10_buttonaddall.png "070703 10_ButtonAddAll") |
| 모든 제거 | ![그래픽 "모두 제거" 단추](../../extensibility/ux-guidelines/media/070703-11_buttonremoveall.png "070703 11_ButtonRemoveAll") |
| 위로 이동 | ![그래픽 "위로 이동" 단추](../../extensibility/ux-guidelines/media/070703-12_buttonmoveup.png "070703 12_ButtonMoveUp") |
| 아래로 이동 | ![그래픽 "아래로 이동" 단추](../../extensibility/ux-guidelines/media/070703-13_buttonmovedown.png "070703 13_ButtonMoveDown") |
| 삭제 | ![그래픽 "삭제" 단추](../../extensibility/ux-guidelines/media/070703-14_buttondelete.png "070703 14_ButtonDelete") |
  
##### <a name="sizing-and-spacing"></a>크기 조정 및 간격  
짧은 버전의 경우와 동일 하 게 그래픽 단추는 크기 조정 된 **[찾아보기...]**  단추 (26 x 23 픽셀):  
  
![와 투명 한 색 표시가 있거나 없는 단추에는 그래픽 이미지의 모양을](../../extensibility/ux-guidelines/media/070703-15_graphicalbuttonspacing.png "070703 15_GraphicalButtonSpacing")<br />와 투명 한 색 표시가 있거나 없는 단추에 그래픽 이미지의 모양
  
### <a name="hyperlinks"></a>하이퍼링크  
하이퍼링크는 도움말 항목, 모달 대화 상자 또는 마법사를 여는 등의 탐색 기반 작업에 매우 적합 합니다. 하이퍼링크는 명령에 사용 하는 경우 항상 표시할지 표시 변경 UI에 있습니다. 일반적으로 (예: 취소를 저장 하 고 삭제) 작업에 대 한 커밋 작업은 단추를 사용 하 여을 전달 향상 됩니다.  
  
#### <a name="writing-style"></a>필기 스타일  
에 따라는 [사용자 인터페이스 텍스트에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx)합니다. "자세한 자세한 정보," 사용 안 함 "알 내게 자세한," 또는 "Get 도움말이" 구문입니다. 대신, 구를 도움말 콘텐츠를 통해 확인할 기본 질문 관련 된 도움말 링크 텍스트입니다. 예를 들어 "**서버 탐색기에는 서버는 어떻게 추가 않는?**"  
  
#### <a name="visual-style"></a>비주얼 스타일  
  
-   하이퍼링크는 항상 사용 해야 [VSColor 서비스](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService)합니다. 하이퍼링크의 올바르게을 스타일, 활성 상태인 경우 빨간색 깜박이 또는 방문 후 다른 색을 표시 합니다.  
  
-   컨트롤에에서 있지 않으면 링크 전체 문장 내에서 문장을 조각 처럼 워터 마크 상태를 놓으면에서 밑줄을 포함 하지 마세요.  
  
-   가리키기 밑줄 표시 해서는 안 됩니다. 대신, 링크가 활성화 되어 사용자에 게 피드백은 약간의 색 변경 하 고 적절 한 링크 커서입니다.  
  
##  <a name="BKMK_TreeViews"></a> 트리 뷰  
  
트리 뷰에서 제공 부모-자식 그룹으로 복잡 한 구성 하는 방법을 나열 합니다. 사용자가 확장 하거나 기본 자식 항목을 표시 하거나 숨기려면 부모 그룹을 축소 합니다. 추가 작업을 제공 하는 트리 뷰 내에서 각 항목을 선택할 수 있습니다.  
  
###  <a name="BKMK_TreeViewVisualStyle"></a> 트리 뷰 비주얼 스타일  
  
#### <a name="expanders"></a>확장기  
트리 뷰 컨트롤은 Windows 및 Visual Studio에서 사용 하는 확장 디자인을 따라야 합니다. 각 노드는 expander 컨트롤을 사용 하 여 기본 항목을 표시 하거나 숨깁니다. Expander 컨트롤을 사용 하 여 다른 트리 뷰 창 및 Visual Studio 내에서 발생할 수 있는 사용자에 대 한 일관성을 제공 합니다.  
  
![올바른: expander 컨트롤을 사용 하 여 트리 보기 노드의 적절 한 스타일이](../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705 1_TreeViewCorrect")<br />Expander 컨트롤을 사용 하 여 트리 보기 노드의 적절 한 스타일이 잘못:
  
![잘못 되었습니다: 트리 보기 노드의 잘못 된 스타일](../../extensibility/ux-guidelines/media/070705-2_treeviewincorrect1.png "070705 2_TreeViewIncorrect1")<br />트리 뷰 노드에의 부적절 한 스타일 잘못 되었습니다:
  
#### <a name="selection"></a>선택  
트리 뷰에서 노드를 선택할 때 강조 표시는 트리 뷰 컨트롤의 전체 너비를 확장 해야 합니다. 이렇게 하면 사용자가 선택한 항목을 명확 하 게 식별 합니다. 선택 영역 색 현재 Visual Studio 테마를 반영 해야 합니다.  
  
![올바른: 선택한 노드의 강조 표시의 트리 뷰 컨트롤의 전체 너비를 맞춥니다. ] (../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705 1_TreeViewCorrect")<br />올바른: 선택한 노드의 강조 표시의 트리 뷰 컨트롤의 전체 너비를 맞춥니다.
  
![잘못 되었습니다: 선택한 노드의 강조 표시에는 트리 뷰 컨트롤의 전체 너비를 맞지 않습니다. ] (../../extensibility/ux-guidelines/media/070705-3_treeviewincorrect2.png "070705 3_TreeViewIncorrect2")<br />잘못 되었습니다: 선택한 노드의 강조 표시에는 트리 뷰 컨트롤의 전체 너비를 맞지 않습니다.
  
#### <a name="icons"></a>아이콘  
항목 간의 차이 시각적으로 식별 하는 데 도움이 되는 경우에 아이콘 트리 뷰 컨트롤에서 사용 해야 합니다. 일반적으로 아이콘 아이콘이 있는 유형의 요소를 구분 하는 정보를 전달 하는 유형이 다른 목록 에서만에서 사용할 수 해야 합니다. 유형이 같은 목록에서 아이콘을 사용 하 여 노이즈로 자주 볼 수 있습니다 피해 야 합니다. 이 경우 그룹 아이콘 (부모) 내에서 항목의 형식을 전달할 수 있습니다. 아이콘은 동적 및 상태를 표시 하는 데 사용 하는 경우이 규칙에 예외가입니다.  
  
#### <a name="scroll-bars"></a>스크롤 막대  
스크롤 막대를 콘텐츠 트리 뷰 컨트롤 내에 맞으면에 항상 숨깁니다. 사용할 수 있기 스크롤 막대의 스크롤 가능한 창에서 숨김 또는 반투명 하 게 될 및 트리 뷰를 포함 하 여 창에 포커스가 있을 때 나타나거나 트리의 hover에 따라 자체를 표시 합니다.  
  
![트리 뷰 컨트롤의 한계를 초과 하 게 내용이 되므로 두 세로 및 가로 스크롤 막대가 표시 됩니다. ] (../../extensibility/ux-guidelines/media/070705-4_scrollbars.png "070705 4_Scrollbars")<br />트리 뷰 컨트롤의 한계를 초과 하 게 내용이 되므로 두 세로 및 가로 스크롤 막대가 표시 됩니다.
  
###  <a name="BKMK_TreeViewInteractions"></a> 트리 뷰 상호 작용  
  
#### <a name="context-menus"></a>상황에 맞는 메뉴  
트리 뷰 노드 상황에 맞는 메뉴에서 하위 메뉴 옵션을 표시할 수 있습니다. 일반적으로이 사용자가 항목을 마우스 오른쪽 단추로 클릭 하거나 선택한 항목으로 Windows 키보드에서 메뉴 키를 누를 때 발생 합니다. 노드 포커스 및 선택 유용 합니다. 이렇게 하면 사용자에 속한 하위 메뉴 항목을 식별할 수 있습니다.  
  
![선택한 항목을 사용자에 게 알리도록 상황에 맞는 메뉴 향상 포커스 어떤 항목을 생성 했습니다. ] (../../extensibility/ux-guidelines/media/070705-5_contextmenu.png "070705 5_ContextMenu")<br />선택한 항목을 사용자에 게 알리도록 상황에 맞는 메뉴 향상 포커스 어떤 항목을 생성 했습니다.
  
#### <a name="keyboard"></a>키보드  
트리 뷰에서 항목을 선택 하 고 키보드를 사용 하 여 노드 확장/축소 하는 기능을 제공 해야 합니다. 이렇게 하면 탐색 접근성 요구 사항은 충족 합니다.  
  
##### <a name="tree-view-control"></a>트리 뷰 컨트롤  
Visual Studio의 트리 컨트롤은 일반적인 키보드 탐색을 따라야 합니다.  
  
-   **위쪽 화살표:** 트리를 이동 하 여 항목을 선택 합니다.  
  
-   **아래쪽 화살표:** 트리 아래로 이동 하 여 항목을 선택 합니다.  
  
-   **오른쪽 화살표:** 트리에서 노드를 확장 합니다.  
  
-   **왼쪽된 화살표:** 트리에서 노드를 축소 합니다.  
  
-   **키 입력:** 시작, 로드, 선택된 항목 실행  
  
##### <a name="trid-tree-view-and-grid-view"></a>Trid (트리 보기 및 그리드 보기)  
Trid 컨트롤은 grid 트리 뷰를 포함 하는 복잡 한 제어 합니다. 확장, 축소 하 고 트리를 탐색한 다음 항목이 추가 된 트리 뷰로 동일한 키보드 명령을 허용 해야 합니다.  
  
-   **오른쪽 화살표:** 노드를 확장 합니다. 노드가 확장 된 후 지속 되는 가장 가까운 열 오른쪽으로 이동 합니다. 행의 끝에 탐색 중지 해야 합니다.  
  
-   **탭:** Navigates 오른쪽에 가장 가까운 셀에 전달 합니다.  행의 끝에 다음 행으로 탐색 계속합니다.  
  
-   **Shift + Tab:** Navigates 왼쪽의 가장 가까운 셀에 전달 합니다.  행의 시작 부분에서 탐색 이전 행의 오른쪽에 있는 셀을 계속합니다.  
  
![Visual Studio의 trid 컨트롤](../../extensibility/ux-guidelines/media/070705-6_trid.png "070705 6_Trid")<br />Visual Studio의 trid 컨트롤