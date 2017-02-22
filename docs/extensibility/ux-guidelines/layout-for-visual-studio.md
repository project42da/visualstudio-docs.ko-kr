---
title: "Visual Studio에 대 한 레이아웃 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c19e3022-047c-43b6-a046-a82717efed4f
caps.latest.revision: 2
caps.handback.revision: 2
ms.author: "gregvanl"
manager: "ghogen"
---
# Visual Studio에 대 한 레이아웃
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

대부분의 Visual Studio 대화 상자는 [유틸리티 대화 상자 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_UtilityDialogLayout), 대화 상자에 따라 표준에는 unthemed는 [Windows 바탕 화면 대화 상자 레이아웃 원칙](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx)합니다. Visual Studio UI를 새로 고칠 수의 이동, 경험으로 제품 정의 설정 하는 새로운 디자인 일부 띄 대화 상자에 있습니다. 이러한 [테마가 지정된 대화 상자 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_ThemedDialogLayout) 테마가 지정 된 모양입니다.  
  
##  <a name="BKMK_UtilityDialogLayout"></a> 유틸리티 대화 상자 레이아웃  
  
-   유틸리티 대화 상자 내에서 모든 컨트롤 위쪽\/왼쪽에서 시작 하 고 아래쪽으로 이동 해야 합니다.  
  
-   하지 센터는 대화 상자에 컨트롤 큰 영역을 채웁니다.  
  
-   환경 글꼴을 사용 하 여 모든 대화 텍스트. 시각적 사양을 작성할 때는 특정 글꼴 및 크기를 선택 하는 대신 환경 글꼴을 지정 합니다.[환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)을 참조하세요.  
  
-   장인의 품질에 대 한 목표를 지원 하기 위해 일관 된 컨트롤 간격 및 배치를 사용 합니다.  
  
-   대화 상자는 많은 수의 컨트롤, 컨트롤의 고유 juxtaposition 또는 둘 다 더 복잡할 수 있습니다. 이러한 복잡 한 경우 사용자에 게 구문 분석 하는 논리 흐름 제어 그룹 간의 적절 한 공간을 허용 합니다.  
  
### 유틸리티 대화 상자 레이아웃 예제  
 모든 치수 \(픽셀\)로 표시 됩니다.  
  
 ![Dialog spacing for labels above controls](../../extensibility/ux-guidelines/media/0801-a_utilityspacingabove.png "0801\-a\_UtilitySpacingAbove")  
  
 **레이블이 컨트롤 위에 있는 유틸리티 대화 상자에 대 한 그림 08.01: 간격 지침**  
  
 ![Dialog spacing for labels to the left of controls](../../extensibility/ux-guidelines/media/0801-b_utilityspacingleft.png "0801\-b\_UtilitySpacingLeft")  
  
 **레이블이 컨트롤 왼쪽에 있는 유틸리티 대화 상자에 대 한 그림 08.01 b: 간격 지침**  
  
### 레이아웃 정보  
  
#### 여백  
  
-   모든 대화 상자에는 12 픽셀 테두리 가장자리 모두 있어야 합니다.  
  
-   그룹 내 여백 프레임의 가장자리 로부터 9 픽셀 이어야 합니다.  
  
-   탭 컨트롤 내의 여백 탭 컨트롤의 가장자리에서 6 픽셀 이어야 합니다.  
  
#### 명령 단추  
  
-   명령 단추 콘텐츠에 없는 대화 프레임에서 작동합니다. 이러한 배치 해야 맨 아래에서 오른쪽 단추를 명확 하 게 구분 설정 하려면 위의 변수 충분 한 공간이 있어야 합니다.  
  
-   대화 상자 내에서 작동 하는 가로 단추가 있으면 대체 명령 단추 구성은 세로로 오른쪽 위에 있습니다. 참조 [내부 명령 단추](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_InteriorCommandButtons) 아래입니다.  
  
-   명령 단추 \(왼쪽\/의 아래쪽 가운데 대화 상자\)의 왼쪽에는 공간에는 작업 대화 상자 컨트롤의 "밴드"의 일부로 간주 됩니다. 공간을 저해 해야 하는 작업만 전체 작업이 나 대화 상자에 관련 된 도움말 링크.  
  
-   명령 단추에는 75 x 23 픽셀 이어야 합니다.  
  
-   명령 단추 6 픽셀 만큼 떨어지게 이어야 합니다.  
  
 ![Basic button alignment](../../extensibility/ux-guidelines/media/0801-c_buttonalign.png "0801\-c\_ButtonAlign")  
  
 **그림 08.01 c: 기본 단추 맞춤**  
  
#### 레이블  
  
-   왼쪽에 맞추려면 모든 레이블이 있습니다.  
  
-   레이블이 컨트롤 위에 배치에 대 한 해야 왼쪽\-정렬 아래 제어와 정확 하 게 하 고 레이블 아래에 다른 컨트롤 \(예: 콤보 상자\)의 맨 위에서 5 픽셀 이어야 합니다.  
  
-   컨트롤의 왼쪽에 있는 레이블의 레이블과 입력된 컨트롤 사이의 최소 너비는 10 픽셀입니다. 암시 된 두 번째 열에서 텍스트 상자, 콤보 상자나 기타 컨트롤을 정렬 하기 위해 설정 됩니다.  
  
-   레이블과 문장의 첫 글자는 뒤에 콜론이 옵니다.[텍스트 스타일](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle)을 참조하세요.  
  
#### 컨트롤 사이의 거리  
 컨트롤을 적절 하 게 스택 합니다. 누적된 컨트롤 사이의 간격에 대 한 절대 없는 지침이 있습니다. 컨트롤 간의 다듬기 대화 상자 약간 달라질 수 있습니다. 권장 간격은 20 픽셀 수직 컨트롤\/레이블 쌍에 대 한 및 가로 컨트롤\/레이블 쌍에 대 한 9 픽셀입니다. 가로 쌍에 대 한 최소 제어 간격은 6 \(픽셀\)입니다.  
  
 ![Recommended distance between controls](../../extensibility/ux-guidelines/media/0801-d_controldistance.png "0801\-d\_ControlDistance")  
  
 **컨트롤 사이의 거리에 대 한 그림 08.01 d: 권장 사항**  
  
#### 컨트롤 들여쓰기  
 컨트롤 중첩 될 경우, 위의 작업을 일반적으로 레이블이 컨트롤의 왼쪽된 가장자리를 사용 하 여 가로로 내부 컨트롤을 정렬 합니다.  
  
 ![Nested control alignment](../../extensibility/ux-guidelines/media/0801-e_controlalign.png "0801\-e\_ControlAlign")  
  
 **그림 08.01 e: 중첩 된 컨트롤 맞춤**  
  
#### 컨트롤 너비  
 텍스트 상자 또는 기타 비슷한 컨트롤의 너비 필드에 대 한 평균 입력이 하 여야 합니다. 평균 영어 단어는 5 자입니다. 예를 들어, 긴 경로 이름을 입력 해야 하는 텍스트 상자가 길어야 가로 레이아웃을 허용 하므로 플랫폼 이름만 해야 하는 가장 긴 항목에 사용할 수 있는 길이 대 한 드롭다운 while입니다.  
  
#### 도우미 텍스트  
  
-   대화 상자 대화 상자의 목적에 대 한 자세한 정보를 제공 하는 도우미 텍스트를 표시할 수 있습니다. 이 일반적으로 위쪽에 위치 하며 1\-2 문장을 수 있습니다.  
  
-   줄 길이는 구문 분석을 읽고 사용자에 대 한 것이 편한 너비 여야 합니다. 보통 대화 개 이하의 550 픽셀로 이어야 합니다.  
  
####  <a name="BKMK_InteriorCommandButtons"></a> 내부 명령 단추  
 좀 더 복잡 한 대화 상자, 내부 컨트롤 대화의 커밋 단추가 있는 위치에 영향을 줄 수 있는 자체 관련된 단추를 사용할 수 있습니다.  
  
-   세로 맞춤 \(열\)의 내부 때 단추를 사용 하 여 **확인**\/**취소** 오른쪽 아래 모서리에서 가로로 조정 됩니다.  
  
-   가로 맞춤 \(행\)의 내부 때 단추를 사용 하 여 **확인**\/**취소** 오른쪽 위 모퉁이에서 세로 방향으로 합니다. 이 상황은 일반적입니다.  
  
-   내부 단추 크기의 75 x 23 픽셀의 크기와 일치 하는 표준 단추 크기를 대상으로 해야 **확인**\/**취소** 가능 하면 단추입니다. 단추 레이블 표준 단추 크기를 초과 하는 단추를 만드는 경우 해당 집합의 다른 단추는 큰 크기로 일치 해야 합니다.  
  
 ![Horizontal OK and Cancel buttons](../../extensibility/ux-guidelines/media/0801-f_horizokcan.png "0801\-f\_HorizOKCan")  
  
 **가로 확인\/취소 된 세로 내부 단추 그림 08.01 f:**  
  
 ![Vertical OK and Cancel buttons](../../extensibility/ux-guidelines/media/0801-g_vertokcan.png "0801\-g\_VertOKCan")  
  
 **세로 확인\/취소 된 가로 내부 단추가 그림 08.01 g:**  
  
#### \[찾아보기...\] 단추  
 **\[찾아보기...\]** "찾아보기..." 텍스트 상자에 따라 단추를 나열 해야 전체, 가변 매개 변수를 포함합니다. 공간이 밀접 하 게 하거나 여러 개 있는 경우 **\[찾아보기...\]** 만 줄임표 단추는 화면에서 단추 줄일 수 있습니다.  
  
##  <a name="BKMK_ThemedDialogLayout"></a> 테마가 지정된 대화 상자 레이아웃  
 Visual Studio에서 테마가 지정 된 대화 상자에는 어 지는 모양이 및 더 많은 흰색 공간을 제공 합니다. 입력 체계 강조 점점 개방성 줄 간격 및 글꼴 크기 및 중량의 변형 제공 관심을 제공 합니다. 가능한 경우, chrome 및 제목 표시줄 감소 되거나 제거 된 합니다. 이 대화 상자 레이아웃은이 기본 패턴을 따라야 합니다.  
  
1.  대화 상자의 배경색은 흰색입니다.  
  
2.  중간 값 회색에서 1 픽셀 규칙 테두리가 있습니다.  
  
3.  대화 상자 제목을 더 이상는 제목 표시줄에 있지만 더 큰 포인트 크기에서 중요 한 점 및 시각적 효과 제공 합니다. \(글꼴 크기 섹션을 참조 [텍스트 스타일](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).\)  
  
4.  레이블, 설명 등의 추가 텍스트와 결합 해야 **환경 글꼴 \+ 굵게**합니다.  
  
5.  내부 열 밝은 회색으로 1 픽셀 규칙에 의해 구분 됩니다.  
  
6.  기본 링크에는 밑줄 없이 합니다. 가리키기 및 누름된 상태 있으며 밑줄과 색 변경  
  
7.  커밋 단추 \(같은 **확인**\/**취소**\) 오른쪽 아래 모퉁이 있습니다.  
  
### 테마가 지정 된 대화 상자 레이아웃 예제  
 ![Themed dialog layout](../../extensibility/ux-guidelines/media/0801-h_themeddialog.png "0801\-h\_ThemedDialog")  
  
 **그림 08.01\-h: 테마가 지정 된 대화 상자**  
  
 ![Themed dialog dimensions](../../extensibility/ux-guidelines/media/0801-i_themeddialogdimensions.png "0801\-i\_ThemedDialogDimensions")  
  
 **그림 08.01 i: 테마가 지정 된 대화 상자\-차원**  
  
 ![Themed dialog fonts](../../extensibility/ux-guidelines/media/0801-j_themeddialogfonts.png "0801\-j\_ThemedDialogFonts")  
  
 **그림 08.01 j: 테마가 지정 된 대화 상자\-글꼴**  
  
 ![Themed dialog colors](../../extensibility/ux-guidelines/media/0801-k_themeddialogcolors.png "0801\-k\_ThemedDialogColors")  
  
 **그림 08.01\-k: 테마가 지정 된 대화 상자 색**  
  
## 참고 항목  
 [Visual Studio에 대 한 응용 프로그램 패턴](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)   
 [컨트롤 \(Windows\)](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)   
 [대화 상자 \(Windows\)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx)