---
title: "Visual Studio의 일반 컨트롤 패턴 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3e893949-6398-42f1-9eab-a8d8c2b7f02d
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# Visual Studio의 일반 컨트롤 패턴
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

##  <a name="BKMK_CommonControls"></a> 공용 컨트롤  
  
### 개요  
 공용 컨트롤은 대부분의 Visual Studio의 사용자 인터페이스를 구성 합니다. Visual Studio 인터페이스에 사용 되는 가장 일반적인 컨트롤 따라야는 [Windows 데스크톱 상호 작용 지침](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)합니다. 이 문서는 Visual Studio에 고유 하며 특수 한 상황 또는 해당 Windows 지침을 확대 하는 세부 정보에 설명 합니다.  
  
#### 이 항목의 공용 컨트롤  
  
-   [스크롤 막대](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_Scrollbars)  
  
-   [입력된 필드](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_InputFields)  
  
-   [콤보 상자 및 드롭다운 목록](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ComboBoxesAndDropDowns)  
  
-   [확인란](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CheckBoxes)  
  
-   [라디오 단추](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_RadioButtons)  
  
-   [그룹 프레임](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_GroupFrames)  
  
-   [텍스트 컨트롤](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
-   [단추, 하이퍼링크](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
-   [트리 뷰](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TreeViews)  
  
#### 비주얼 스타일  
 컨트롤의 스타일을 지정 하는 경우를 고려해 야 할 가장 먼저 테마가 지정 된 UI 컨트롤 사용 여부는 합니다. 표준 UI 테마가 지정 된 비 UI는 컨트롤과 따라야 [표준 Windows 데스크톱 스타일](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx), 즉 re 템플릿이 없는 하 고 기본 컨트롤 모양에 표시 됩니다.  
  
-   **표준 \(유틸리티\) 대화 상자:** 테마가 적용 되지 않습니다. Re 템플릿 하지 마십시오. 기본 컨트롤 스타일 기본값을 사용 합니다.  
  
-   **도구 창, 문서 편집기, 디자인 화면 및 테마가 지정 된 대화 상자:** 특수 테마가 지정 된 모양 컬러 서비스를 사용 하 여 사용 합니다.  
  
###  <a name="BKMK_Scrollbars"></a> 스크롤 막대  
 스크롤 막대를 따라야 [Windows 스크롤 막대에 대 한 일반적인 상호 작용 패턴](https://msdn.microsoft.com/en-us/library/windows/desktop/bb787527\(v=vs.85\).aspx) 것은 보강 된 콘텐츠 정보와 같은 코드 편집기에서 하지 않는 한 합니다.  
  
###  <a name="BKMK_InputFields"></a> 입력된 필드  
 일반적인 상호 작용이 동작에 따라는 [텍스트 상자에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742442\(v=vs.85\).aspx)합니다.  
  
#### 비주얼 스타일  
  
-   유틸리티 대화 상자에서 입력된 필드를 스타일 수 해야 합니다. 기본 스타일을 컨트롤에 내장 함수를 사용 합니다.  
  
-   테마가 지정 된 입력된 필드 테마가 지정 된 대화 상자와 도구 창에만 사용 해야 합니다.  
  
#### 특수 한 상호 작용  
  
-   읽기 전용 필드는 배경이 회색 \(비활성\) \(활성\) 기본 전경 하지만.  
  
-   필드 있어야 하는 데 필요한 **\< 필요한 \>** 내에서 워터 마크를 합니다. 드문 경우에서를 제외 하 고 배경색을 변경 하면 안 됩니다.  
  
-   유효성 검사 오류: 참조 [알림 및 Visual Studio에 대 한 진행률](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)  
  
-   입력된 필드에 표시 된 창의 너비를 적합 하지도 임의로 경로 같은 긴 필드의 길이 일치 하는 내용에 맞게 크기를 지정 해야 합니다. 길이 필드에 얼마나 많은 문자는 사용할 수에 대 한 제한의 사용자에 게 표시 됨  
  
     ![Incorrect input field control width](../../extensibility/ux-guidelines/media/0707-01_incorrectinputfieldcontrol.png "0707\-01\_IncorrectInputFieldControl")   
     **잘못 된 입력된 필드 길이: 이름은 이렇게 긴 됩니다 많지 않습니다.**  
  
     ![Correct input field control width](../../extensibility/ux-guidelines/media/0707-02_correctinputfieldcontrol.png "0707\-02\_CorrectInputFieldControl")   
     **입력된 필드 길이 수정: 입력된 필드는 예상 되는 콘텐츠에 대 한 적절 한 너비입니다.**  
  
###  <a name="BKMK_ComboBoxesAndDropDowns"></a> 콤보 상자 및 드롭다운 목록  
 일반적인 상호 작용이 동작에 따라는 [드롭 다운 목록 및 콤보 상자에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742404\(v=vs.85\).aspx)합니다.  
  
#### 비주얼 스타일  
  
-   유틸리티 대화 상자에서 컨트롤 re 템플릿 하지 않습니다. 기본 스타일을 컨트롤에 내장 함수를 사용 합니다.  
  
-   테마가 지정 된 UI, 콤보 상자 및 드롭다운 컨트롤에 대 한 표준 테마를 따릅니다.  
  
#### 레이아웃  
 콤보 상자 및 드롭다운 크기가 표시 된 창의 너비에 맞게 하지도 임의로 경로 같은 긴 필드의 길이 일치 하는 내용에 맞게 조정 됩니다.  
  
 ![Incorrect drop&#45;down layout](../../extensibility/ux-guidelines/media/0707-03_incorrectdropdownlayout.png "0707\-03\_IncorrectDropDownLayout")  
  
 **드롭다운 목록 컨트롤에 대 한 잘못 된 필드 길이**  
  
 ![Correct drop&#45;down layout](../../extensibility/ux-guidelines/media/0707-04_correctdropdownlayout.png "0707\-04\_CorrectDropDownLayout")  
  
 **드롭다운 목록 컨트롤에 대 한 올바른 필드 길이**  
  
###  <a name="BKMK_CheckBoxes"></a> 확인란  
 일반적인 상호 작용이 동작에 따라는 [확인란에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742401\(v=vs.85\).aspx)합니다.  
  
#### 비주얼 스타일  
  
-   유틸리티 대화 상자에서 컨트롤 re 템플릿 하지 않습니다. 기본 스타일을 컨트롤에 내장 함수를 사용 합니다.  
  
-   테마가 지정 된 UI 확인란 컨트롤에 대 한 표준 테마를 따릅니다.  
  
#### 특수 한 상호 작용  
  
-   확인란와의 상호 작용 하지는 대화 상자를 표시 하거나 다른 영역으로 이동 해야 합니다.  
  
-   확인란이 텍스트의 첫 번째 줄의 기준선을 맞춥니다.  
  
     ![Incorrect check box alignment](../../extensibility/ux-guidelines/media/0707-05_incorrectcheckboxalign.png "0707\-05\_IncorrectCheckBoxAlign")   
     **잘못 된 확인란 맞춤: 가운데 확인란 텍스트에 표시 됩니다.**  
  
     ![Correct check box alignment](../../extensibility/ux-guidelines/media/0707-06_correctcheckboxalign.png "0707\-06\_CorrectCheckBoxAlign")   
     **확인란 맞춤 수정: 확인란 텍스트의 첫 번째 줄의 기준선에 맞춰 정렬 됩니다.**  
  
###  <a name="BKMK_RadioButtons"></a> 라디오 단추  
 일반적인 상호 작용이 동작에 따라는 [라디오 단추에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742436\(v=vs.85\).aspx)합니다.  
  
#### 비주얼 스타일  
 유틸리티 대화 상자에서 스타일 라디오 단추를 하지 않습니다. 기본 스타일을 컨트롤에 내장 함수를 사용 합니다.  
  
#### 특수 한 상호 작용  
 그룹 틀을 라디오 선택 항목을 묶을 때 사용 하 여 필요는 없습니다.  
  
###  <a name="BKMK_GroupFrames"></a> 그룹 프레임  
 일반적인 상호 작용이 동작에 따라는 [그룹 프레임에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742405\(v=vs.85\).aspx)합니다.  
  
#### 비주얼 스타일  
 유틸리티 대화 상자에서 스타일 그룹 프레임 하지 마십시오. 기본 스타일을 컨트롤에 내장 함수를 사용 합니다.  
  
#### 레이아웃  
  
-   밀접 하 게 레이아웃에 그룹 구분을 유지 하기 위해 필요한 경우가 아니면 그룹 틀을 라디오 선택 항목을 묶을 때 사용 하 여 필요는 없습니다.  
  
-   단일 컨트롤에 대 한 그룹 프레임을 사용 하지 마십시오.  
  
-   때로는 그룹 프레임 컨테이너 대신 가로 규칙을 사용 하는 것이 좋습니다.  
  
##  <a name="BKMK_TextControls"></a> 텍스트 컨트롤  
  
### 레이블  
  
#### 활성 레이블 상태  
  
##### 유틸리티 \(표준\) 대화 상자\)  
  
-   일반적으로 레이블 컨트롤에 대 한 Windows 바탕 화면 지침을 따릅니다.  
  
-   유틸리티 대화 상자에서 굵은 글꼴이 아닌, 표준 환경 글꼴 및 텍스트 색에 레이블이 표시 됩니다.[글꼴 및 Visual Studio에 대 한 서식 지정](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)을 참조하세요.  
  
-   타원 항상 레이블을 따라야 합니다.  
  
##### 서명 \(테마가 지정 된\) 대화 상자\)  
 Label 컨트롤 굵은 글꼴이 나 밝은 회색 수 있습니다.  
  
#### 사용할 수 없는 레이블 상태  
 레이블에 연결 된 컨트롤의 모양을 반영 해야 합니다. 예를 들어, 연결 된 컨트롤을 사용 하지 않으면 다음 레이블을 나타나야 회색 및 비활성화 합니다. 이 일반적으로 OS에 의해 처리 하며 특별 한 작업이 수행 되지 않습니다.  
  
#### 동적 레이블  
 현재 선택에 따라 동적 레이블 변경 합니다. 가능 하면 사용자 정보를 표시 하 고 특정 항목을 선택 하지 일반 정보 임을 이해 하는 데 도움이 마스터\/세부 레이아웃의 동적 레이블을 사용 합니다.  
  
 ![Dynamic label used with dynamic content](../../extensibility/ux-guidelines/media/070702-01_dynamiclabel.png "070702\-01\_DynamicLabel")  
  
 **동적 콘텐츠에 사용 된 동적 레이블 예제**  
  
#### 사용 안내 텍스트  
 사용자 UI 목적을 이해 하는 데 도움이 또는 수행할 작업을 나타내기 위해 사용 안내 텍스트에서 일부 인터페이스 요소 활용 합니다.  
  
-   사용 안내 텍스트 대화 상자 위쪽에서 가장 일반적 이기는 하지만 복잡 한 제어 그룹화에 지침을 제공 하는 다른 영역에 나타날 수 있습니다.  
  
-   사용 안내 텍스트 비 대화형 이지만 도움말 항목에 대 한 하이퍼링크를 포함할 수 있습니다.  
  
-   필요한 경우에 하 고만 사용 안내 텍스트를 사용 하 여 필요한 경우.  
  
##### 서식  
 사용 안내 텍스트 환경 글꼴, 표준 \(비 테마\) 제어 텍스트 여야 합니다.[글꼴 및 Visual Studio에 대 한 서식 지정](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)을 참조하세요.  
  
 사용 안내 텍스트 작성에 대 한 자세한 내용은 참조 하십시오. [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology)합니다.  
  
 ![Instructional text formatting](../../extensibility/ux-guidelines/media/070702-02_instructionaltextformatting.png "070702\-02\_InstructionalTextFormatting")  
  
 **Visual Studio 대화 상자에서 사용 안내 텍스트**  
  
#### 정보 텍스트  
 정보 텍스트에는 추가 사용자 정보를 제공 하는 텍스트가입니다. 정적 또는 동적으로 또는 한 알림으로 사용 하는 수 있습니다. 것이 항상 읽기 전용 하지만 사용자에 게 정보를 복사 하는 기능에 대 한 유용한 경우 동적 텍스트 읽기 전용 텍스트 필드와 같은 컨트롤 컨테이너에 배치 해야 합니다.  
  
##### 동적 \(컨텍스트별\) 텍스트  
 사용자가 포커스를 전환 하는 경우와 같은 컨텍스트에 따라 동적 정보 텍스트 변경 됩니다. 항상 그렇지는 않지만 종종 동적 콘텐츠 동적 레이블 쌍을 이룹니다.  
  
 ![Dynamic information text](../../extensibility/ux-guidelines/media/070702-03_informationaldynamictext.png "070702\-03\_InformationalDynamicText")  
  
 **동적 정보 텍스트는 컨텍스트에 따라 변경합니다.**  
  
##### 서식  
 읽기 전용 텍스트 필드를 표시 하는 방법은 두 가지가: \(위 참조\) 화면 UI에서 직접 또는 그룹 프레임이 나 텍스트 상자와 같은 다른 컨트롤에 포함 합니다. 상황에 따라 올바른 중 하나에 해당 합니다. 읽기 전용 정보를 제공 하는 방법을 결정 하 여 기능 디자이너는 합니다.  
  
 텍스트는 읽기 전용 텍스트 상자 내부 수 있습니다. 이 일반적으로 나타냅니다 콘텐츠 선택 고 복사 될 수 있지만 편집할 수 없습니다.  
  
 ![Informational text formatting for read&#45;only fields](../../extensibility/ux-guidelines/media/070702-04_informationalformatting.png "070702\-04\_InformationalFormatting")  
  
 **읽기 전용 필드에 대한 정보 텍스트 서식**  
  
#### 워터 마크  
 단어는 동일할 수, 하는 동안에 워터 마크 및 지침 텍스트 간의 차이점은 컨트롤이 나 창 비어 있지 않으며 가시적인 형태로 확인할 사용 안내 텍스트 항상 때 워터 마크 콘텐츠로 대체 됩니다.  
  
 워터 마크 창 또는 컨트롤 비어 있을 때 사용 해야 합니다. 나타내며이 영역을 채울 하기 위해 필요한 작업 링크는 끌기 소스와 같은 관련 창을 열 수를 포함 될 수 있습니다.  
  
##### 비주얼 스타일  
  
-   워터 마크 창 내에서 가로로 맞춰야 합니다.  
  
-   워터 마크 해야 가운데 맞춤 왼쪽 맞춤 합니다.  
  
-   워터 마크 세로로 가운데 되었거나 영역의 맨 위 근처에 배치 합니다. 에 있는 경우 영역의 맨 위 근처, 충분 한 공간이 있어야 위의 워터 마크를 둘러 되도록 합니다.  
  
-   사용 된 `Environment.GrayText` 토큰 및 표준 환경 글꼴 색입니다. 하이퍼링크는 공유 하는 표준 하이퍼링크 토큰을 사용 해야: `Environment.PanelHyperlink`, `Environment.PanelHyperlinkHover`, `Environment.PanelHyperlinkPressed`, 및 `Environment.PanelHyperlinkDisabled`합니다.  
  
-   백그라운드에서 워터 마크를 선택할 수 없습니다.  
  
-   가능 하면 워터 마크를 시작 하 여 사용자에 대 한 링크를 포함 합니다.  
  
 ![Watermark text in a designer window](../../extensibility/ux-guidelines/media/070702-05_watermark1.png "070702\-05\_Watermark1")  
  
 ![Watermark text in a tool window](../../extensibility/ux-guidelines/media/070702-06_watermark2.png "070702\-06\_Watermark2")  
  
 **Visual Studio의 워터 마크 텍스트의 예**  
  
##  <a name="BKMK_ButtonsAndHyperlinks"></a> 단추, 하이퍼링크  
  
### 개요  
 단추 및 링크 컨트롤 \(하이퍼링크\) 따라야 [하이퍼링크에 대 한 기본 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742406\(v=vs.85\).aspx) 사용 현황, 어조를 조정 하 고 간격입니다.  
  
### 링크 및 단추 선택  
 일반적으로 작업 단추 사용 되었 및 탐색에 대 한 예약 된 하이퍼링크입니다. 모든 경우에 단추를 사용할 수 있지만 역할 링크 단추 및 링크는 몇 가지 조건에서 더 서로 바꿔 사용할 수 있도록 Visual Studio에서 확장 되었습니다.  
  
 명령 단추를 사용 하는 경우:  
  
-   기본 명령  
  
-   입력을 수집 하는 데 사용 되는 창 표시 또는 사항을 선택할 보조 명령 된 경우에  
  
-   삭제 또는 취소할 수 없는 작업  
  
-   마법사 및 페이지 흐름 내에서 커밋 단추  
  
 도구 창에 명령 단추를 방지 하거나 레이블에 대 한 두 개 이상의 단어를 필요한 경우. 링크 레이블을 더 있을 수 있습니다.  
  
 링크를 사용 하는 경우:  
  
-   다른 창, 문서 또는 웹 페이지에 대 한 탐색  
  
-   더 긴 레이블 또는 동작의 의도 설명 하기 위해 짧은 문장 해야 하는 상황  
  
-   작업은 삭제 하거나 취소할 수 없는 단추는 UI에 과부하가 걸려는 밀접 하 게 공백을 제공  
  
-   디 강조 상황에서 보조 명령 많은 명령에 있는  
  
#### 예제  
 ![Infobar command links following a status message](../../extensibility/ux-guidelines/media/070703-01_commandlinkinfobar.png "070703\-01\_CommandLinkInfobar")  
  
 **상태 메시지 정보 표시줄에 사용 된 명령 링크**  
  
 ![Links used in the CodeLens popup](../../extensibility/ux-guidelines/media/070703-02_linksincodelens.png "070703\-02\_LinksInCodeLens")  
  
 **CodeLens 팝업에 사용된 링크**  
  
 ![Links used as secondary commands](../../extensibility/ux-guidelines/media/070703-03_linksassecondarycommands.png "070703\-03\_LinksAsSecondaryCommands")  
  
 **단추가 너무 많은 주의 끌어들이고는 보조 명령에 사용 되는 링크**  
  
### 일반 단추  
  
#### 텍스트  
 작성 지침에 따라 [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology)합니다.  
  
#### 비주얼 스타일  
  
##### 표준 대화 상자  
 Visual Studio에서 대부분의 단추 표준 대화 상자에 나타나고 스타일이 해야 합니다. 운영 체제에 의해 정의 된 대로 표준 단추 모양을 반영 해야 합니다.  
  
##### 테마가 지정 된  
 일부 경우에 단추 스타일의 UI 내에서 사용할 수 있으며 이러한 단추를 적절 하 게 스타일이 지정 해야 합니다. 참조 [대화 상자](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs) 테마가 지정 된 컨트롤에 대 한 내용은 합니다.  
  
### 특수 단추  
  
#### 찾아보기... 단추  
 **\[찾아보기...\]** 단추는 표, 대화 상자 및 도구 창 및 기타 모덜리스 UI 요소에 사용 됩니다. 사용자 컨트롤에 값을 채우는 데 도움이 되는 선택을 표시 됩니다. 이 단추를 길고 짧은의 두 가지 변형이 있습니다.  
  
 ![Long &#91;Browse...&#93; button](../../extensibility/ux-guidelines/media/070703-04_browselong.gif "070703\-04\_BrowseLong")  
  
 **긴 \[찾아보기...\] 단추**  
  
 ![Short ellipsis&#45;only &#91;Browse...&#93; button](../../extensibility/ux-guidelines/media/070703-05_browseshort.gif "070703\-05\_BrowseShort")  
  
 **줄임표 전용 짧은 \[...\] 단추**  
  
 짧은 줄임표 전용 단추를 사용 하는 경우:  
  
-   둘 이상의 긴 경우 **\[찾아보기...\]** 탐색을 위한 여러 필드를 허용 하는 경우와 같은 대화 상자에서 단추입니다. 에 대 한 단기를 사용 하 여 **\[...\]** 이 상황에서 만든 혼란 스러운 액세스 키를 방지 하려면 각 응용 프로그램에 대 한 단추 \(**& 찾아보기** 및 **& 찾아보기** 동일한 대화 상자에서\).  
  
-   밀접 하 게 대화 상자에서 또는 긴 단추를 적절 한 위치가 있습니다.  
  
-   경우 단추는 표 형태 컨트롤에 표시 됩니다.  
  
 단추를 사용 하는 것에 대 한 지침:  
  
-   액세스 키를 사용 하지 마십시오. 키보드를 사용 하 여에 액세스 하려면 사용자는 인접 한 컨트롤에서 탭 해야 합니다. 필드를 채우도록를 이후 즉시가 있는 찾아보기 단추를 탭 순서 인지 확인 합니다. 첫 번째 기간 아래에 밑줄을 사용 하지 마십시오.  
  
-   활성 MSAA \(Microsoft Accessibility\) 설정 **이름** 속성을 **찾아보기...** \(줄임표\) 포함 하도록 하는 화면 판독기 읽기 "점으로" 또는 "기간\-기간별." 없습니다 "찾아보기" 관리 되는 컨트롤에 대 한이 설정을 의미는 **AccessibleName** 속성입니다.  
  
-   줄임표를 사용 하지 마십시오 **\[...\]** 찾아보기 동작을 제외 하 고에 대 한 단추입니다. 예를 들어, 필요한 경우는 **\[새로 만들기...\]** 단추 없지만 공간이 부족 하 여 텍스트에 대 한 대화 상자를 다시 디자인 해야 합니다.  
  
##### 크기 조정 및 간격  
 ![Sizing &#91;Browse...&#93; buttons](../../extensibility/ux-guidelines/media/070703-06_browsesizing.png "070703\-06\_BrowseSizing")  
  
 **\[찾아보기...\] 크기 조정 단추**  
  
 ![Spacing &#91;Browse...&#93; buttons](../../extensibility/ux-guidelines/media/070703-07_browsespacing.png "070703\-07\_BrowseSpacing")  
  
 **\[찾아보기...\] 간격 단추**  
  
#### 그래픽 단추  
 일부 단추는 항상 하는 그래픽 이미지를 사용 하 고 공간을 절약 하 고 지역화 문제를 방지 하는 텍스트를 포함 하지 않도록 해야 합니다. 이러한 필드 선택 및 다른 정렬 가능한 목록에 자주 사용 됩니다.  
  
> [!NOTE]
>  사용자 \(액세스 키가 없는\) 이러한 단추를 탭, 따라서 적절 한 순서에 배치 해야 합니다. 화면 판독기 단추 동작을 올바르게 해석할 수 있도록 소요 되는 동작을 단추 이름 속성을 매핑하십시오.  
  
|||  
|-|-|  
|Add|![Graphical "Add" button](../../extensibility/ux-guidelines/media/070703-08_buttonadd.png "070703\-08\_ButtonAdd")|  
|제거|![Graphical "Remove" button](../../extensibility/ux-guidelines/media/070703-09_buttonremove.png "070703\-09\_ButtonRemove")|  
|모두 추가|![Graphical "Add All" button](../../extensibility/ux-guidelines/media/070703-10_buttonaddall.png "070703\-10\_ButtonAddAll")|  
|모두 제거|![Graphical "Remove All" button](../../extensibility/ux-guidelines/media/070703-11_buttonremoveall.png "070703\-11\_ButtonRemoveAll")|  
|위로 이동|![Graphical "Move Up" button](../../extensibility/ux-guidelines/media/070703-12_buttonmoveup.png "070703\-12\_ButtonMoveUp")|  
|아래로 이동|![Graphical "Move Down" button](../../extensibility/ux-guidelines/media/070703-13_buttonmovedown.png "070703\-13\_ButtonMoveDown")|  
|삭제|![Graphical "Delete" button](../../extensibility/ux-guidelines/media/070703-14_buttondelete.png "070703\-14\_ButtonDelete")|  
  
##### 크기 조정 및 간격  
 단추 그래픽의 짧은 버전의 경우와 동일 하 게에 대 한 크기 조정 된 **\[찾아보기...\]** 단추 \(26 x 23 픽셀\):  
  
 ![Button with and without transparent color showing](../../extensibility/ux-guidelines/media/070703-15_graphicalbuttonspacing.png "070703\-15\_GraphicalButtonSpacing")  
  
 **투명 한 색 표시가 있거나 없는 단추에 그래픽 이미지의 모양**  
  
### 하이퍼링크  
 하이퍼링크는 도움말 항목, 모달 대화 상자 또는 마법사를 여는 것 처럼 탐색 기반 작업에 적합 합니다. 하이퍼링크는 명령에 사용 되는 경우 UI에 표시 되 고 눈에 띄는 변경 항상 표시 되어야 합니다. 일반적으로 \(예: 취소, 저장 및 삭제\) 작업에 적용 하는 작업은 단추를 사용 하 여을 전달 향상 됩니다.  
  
#### 필기 스타일  
 에 따라는 [사용자 인터페이스 텍스트에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx)합니다. "자세한 자세한 정보를" 사용 안 함 "알려 me 자세한," 또는 "Get 도움이 필요" 구문입니다. 대신, 구를 도움말 내용에 따라 기본 답변 관련 된 도움말 링크 텍스트입니다. 예를 들어 "**서버 탐색기에 서버를 추가 하려면 어떻게?**"  
  
#### 비주얼 스타일  
  
-   하이퍼링크는 항상 사용 해야 [VSColor 서비스](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService)합니다. 하이퍼링크의 올바르게을 스타일, 활성화 된 경우에 빨간색 깜박이 또는 방문 중인 후 다른 색을 표시 합니다.  
  
-   상태에 있지 않으면 링크는 문장 조각 전체 문장 내에서 같은 워터 마크를 가져가서 컨트롤에 밑줄을 포함 하지 마십시오.  
  
-   밑줄은 호버에 표시 됩니다. 링크가 활성화 되어 있음을 사용자에 게 피드백 만으로도 약간의 색 변경 하 고 적절 한 링크 커서입니다.  
  
##  <a name="BKMK_TreeViews"></a> 트리 뷰  
  
### 개요  
 트리 뷰에서 부모\-자식 그룹으로 복잡 한 구성 하는 방법을 나열을 제공 합니다. 사용자가 확장 하거나 기본 자식 항목을 표시 하거나 숨기려면 부모 그룹을 축소 합니다. 추가 작업을 제공 하는 트리 뷰 내에서 각 항목을 선택할 수 있습니다.  
  
 이 항목에서는 사용 제한, 적절 한 설계 및 트리 보기의 기능에 설명 합니다.  
  
#### 항목 내용  
  
-   [비주얼 스타일](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TreeViewVisualStyle)  
  
-   [상호 작용](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TreeViewInteractions)  
  
###  <a name="BKMK_TreeViewVisualStyle"></a> 비주얼 스타일  
  
#### 확장기  
 트리 뷰 컨트롤은 Windows 및 Visual Studio에서 사용 하는 확장 디자인을 따라야 합니다. 각 노드는 expander 컨트롤을 사용 하 여 기본 항목을 표시 하거나 숨깁니다. Expander 컨트롤을 사용 하 여 Windows 및 Visual Studio 내에서 다른 트리 뷰를 발생할 수 있는 사용자에 대 한 일관성을 제공 합니다.  
  
 ![Correct tree view control](../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705\-1\_TreeViewCorrect")  
  
 **Expander 컨트롤을 사용 하 여 트리 보기 노드의 올바른: 적절 한 스타일**  
  
 ![Incorrect tree view nodes](../../extensibility/ux-guidelines/media/070705-2_treeviewincorrect1.png "070705\-2\_TreeViewIncorrect1")  
  
 **트리 뷰 노드에의 한 부적절 한 스타일 잘못 되었습니다:**  
  
#### 선택  
 트리 뷰 내에서 한 노드를 선택 하는 경우 강조 표시가 트리 뷰 컨트롤의 전체 너비에 확장 해야 합니다. 이렇게 하면 사용자는 선택한 항목을 명확 하 게 식별 합니다. 색 선택은 현재 Visual Studio 테마를 반영 해야 합니다.  
  
 ![Correct tree view control](../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705\-1\_TreeViewCorrect")  
  
 **올바른: 선택한 노드의 강조 트리 뷰 컨트롤의 전체 너비에 맞춥니다.**  
  
 ![Incorrect tree view highlighting](../../extensibility/ux-guidelines/media/070705-3_treeviewincorrect2.png "070705\-3\_TreeViewIncorrect2")  
  
 **잘못 되었습니다: 선택한 노드의 강조 트리 뷰 컨트롤의 전체 너비에 맞지 않습니다.**  
  
#### 아이콘  
 항목 간의 차이 시각적으로 식별 하는 데 도움이 되는 경우에 아이콘 트리 뷰 컨트롤에서 사용 해야 합니다. 일반적으로는 아이콘 형식의 요소를 구분 하는 정보를 전달 하는 유형이 다른 목록 에서만에서 아이콘을 사용 해야 합니다. 유형이 같은 목록에서 아이콘을 사용 하 여 소음으로 자주 볼 수 있습니다 피해 야 합니다. 이 경우 그룹 아이콘 \(부모\) 내 항목의 형식을 전달할 수 있습니다. 이 규칙의 예외 경우에 동적 아이콘과 상태를 표시 하는 데 사용 됩니다 것입니다.  
  
#### 스크롤 막대  
 스크롤 막대를 콘텐츠 트리 뷰 컨트롤 내에 포함 하는 경우에 항상 숨깁니다. 것이 허용 되는 스크롤 막대가 숨겨지거나 반투명 스크롤 가능한 창에서 및 트리 뷰를 포함 하는 창에 포커스가 있을 때 표시 또는 트리 호버 따라 자체를 표시 합니다.  
  
 ![Tree view with scroll bars](../../extensibility/ux-guidelines/media/070705-4_scrollbars.png "070705\-4\_Scrollbars")  
  
 **내용이 있는 트리 뷰 컨트롤의 한계를 초과 하는 세로 및 가로 스크롤 막대가 모두 표시 됩니다.**  
  
###  <a name="BKMK_TreeViewInteractions"></a> 상호 작용  
  
#### 상황에 맞는 메뉴  
 트리 뷰 노드에 상황에 맞는 메뉴에서 하위 메뉴 옵션을 나타낼 수 있습니다. 일반적으로이 사용자가 항목을 마우스 오른쪽 단추로 클릭 하거나 선택한 항목에 있는 Windows 키보드에서 메뉴 키를 누를 때 발생 합니다. 노드 포커스 및 선택이 바람직합니다. 그러면 사용자에 속한 하위 메뉴 항목을 식별할 수 있습니다.  
  
 ![Selected tree node and context menu](../../extensibility/ux-guidelines/media/070705-5_contextmenu.png "070705\-5\_ContextMenu")  
  
 **사용자에 게 상황에 맞는 메뉴 향상 포커스 어떤 항목을 생성 된 항목은 선택 되었습니다.**  
  
#### 키보드  
 트리 뷰에서 항목을 선택 하 고 키보드를 사용 하 여 노드를 확장\/축소 하는 기능을 제공 해야 합니다. 이렇게 하면 탐색 우리의 접근성 요구 사항을 충족 합니다.  
  
##### 트리 뷰 컨트롤  
 Visual Studio의 트리 컨트롤은 일반적인 키보드 탐색을 따라야 합니다.  
  
-   **위쪽 화살표:** 트리를 이동 하 여 항목을 선택 합니다.  
  
-   **아래쪽 화살표:** 트리 아래로 이동 하 여 항목을 선택 합니다.  
  
-   **오른쪽 화살표:** 트리에서 노드를 확장 합니다.  
  
-   **왼쪽 화살표:** 트리에서 노드를 축소 합니다.  
  
-   **Enter 키:** 시작 하 고, 로드, 선택된 항목 실행  
  
##### Trid \(트리 보기 및 그리드 보기\)  
 Trid 컨트롤은 표 내 트리 뷰를 포함 하는 복잡 한 제어 합니다. 확장, 축소, 및 트리를 탐색한 다음 내용을 추가 하 여 트리 뷰로 동일한 키보드 명령을 따라야 합니다.  
  
-   **오른쪽 화살표:** 노드를 확장 합니다. 노드가 확장 된 후 이동 하는 가장 가까운 오른쪽 열에서 계속 해야 합니다. 행의 끝에 탐색 중지 해야 합니다.  
  
-   **탭:** Navigates 오른쪽에 가장 가까운 셀에 전달 합니다.  행의 끝 탐색 다음 행으로 계속 됩니다.  
  
-   **Shift \+ Tab:** Navigates 왼쪽에서 가장 가까운 셀에 전달 합니다.  행의 시작 부분에 탐색 이전 행의 오른쪽에 있는 셀을 계속합니다.  
  
 ![Trid control in Visual Studio](../../extensibility/ux-guidelines/media/070705-6_trid.png "070705\-6\_Trid")  
  
 **Visual Studio의 trid 컨트롤**