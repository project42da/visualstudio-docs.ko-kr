---
title: "Visual Studio에 대 한 레이아웃 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c19e3022-047c-43b6-a046-a82717efed4f
caps.latest.revision: "2"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ebb82c49820bdd664324984bd7d3bb88a5bb5fd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="layout-for-visual-studio"></a>Visual Studio에 대 한 레이아웃
대부분의 Visual Studio 대화 상자는 [유틸리티 대화 상자 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_UtilityDialogLayout), 표준에 따라 대화 상자의 unthemed는 [Windows 바탕 화면 대화 상자 레이아웃 원칙](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx)합니다. Visual Studio UI를 새로 고치려면 이동, 순위가 더 높은 대화의 일부 환경으로 제품 정의 설정 하는 새로운 디자인이 되었습니다. 이러한 [테마가 지정 된 대화 상자 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_ThemedDialogLayout) 테마 모양을 갖도록 합니다.  
  
##  <a name="BKMK_UtilityDialogLayout"></a>유틸리티 대화 상자 레이아웃  
  
-   유틸리티 대화 상자 내에서 모든 컨트롤 위쪽/왼쪽에서 시작 하 고 아래쪽으로 전달 해야 합니다.  
  
-   하지: 큰 영역을 채우는 대화 상자에 센터 컨트롤  
  
-   모든 대화 상자 텍스트에 대 한 환경 글꼴을 사용 합니다. 시각적 사양을 작성할 때 특정 글꼴 및 크기를 선택 하는 대신 환경 글꼴을 지정 합니다. 참조 [환경 글꼴](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TheEnvironmentFont)합니다.  
  
-   일관 된 제어 간격 및 배치 장인의 품질에 대 한 목표를 지 원하는 데 사용 합니다.  
  
-   대화 상자 컨트롤, 컨트롤의 고유 juxtaposition 또는 둘 다의 더 큰 숫자에서 더 복잡 해질 수 있습니다. 이러한 복잡 한 경우 사용자에 게 구문 분석 하는 논리 흐름 제어 그룹화 간의 적절 한 공간을 허용 합니다.  
  
### <a name="utility-dialog-layout-examples"></a>유틸리티 대화 상자 레이아웃 예제  
 모든 차원 (픽셀)로 표현 됩니다.  
  
 ![컨트롤 위의 레이블에 대 한 대화 상자 간격 조정](../../extensibility/ux-guidelines/media/0801-a_utilityspacingabove.png "0801 a_UtilitySpacingAbove")  
  
 **레이블이 컨트롤 위에 있는 유틸리티 대화 상자에 대 한 그림 08.01 a: 간격 지침**  
  
 ![컨트롤의 왼쪽에는 레이블에 대 한 대화 상자 간격 조정](../../extensibility/ux-guidelines/media/0801-b_utilityspacingleft.png "0801 b_UtilitySpacingLeft")  
  
 **레이블이 컨트롤 왼쪽에 있는 유틸리티 대화 상자에 대 한 그림 08.01: 간격 지침**  
  
### <a name="layout-details"></a>레이아웃 정보  
  
#### <a name="margins"></a>여백  
  
-   모든 대화 상자에는 모든 가장자리 주위에 12 픽셀 테두리가 있어야 합니다.  
  
-   그룹 내 여백 프레임의 가장자리에서 9 픽셀 이어야 합니다.  
  
-   탭 컨트롤 내에서 여백 탭 컨트롤의 가장자리에서 6 픽셀 이어야 합니다.  
  
#### <a name="command-buttons"></a>명령 단추  
  
-   명령 단추 대화 상자 프레임 콘텐츠에 없는에서 작동합니다. 배치 해야 맨 아래에 오른쪽 하며 명확 하 게 구분 단추를 설정 하려면 위의 변수 충분 한 공간이 있어야 합니다.  
  
-   대화 상자 내에서 작동 하는 가로 단추 인 대체 명령 단추 구성은 오른쪽 위에 있는 세로 스택입니다. 참조 [내부 명령 단추](../../extensibility/ux-guidelines/layout-for-visual-studio.md#BKMK_InteriorCommandButtons) 아래 합니다.  
  
-   명령 단추 (왼쪽/의 아래쪽 가운데 대화 상자)의 왼쪽에는 공간에는 작업 대화 상자 컨트롤의 "밴드"의 일부로 간주 됩니다. 해당 공간 침해 해야 하는 작업만 전체 작업 또는 대화 상자와 관련 된 도움말 링크입니다.  
  
-   명령 단추 75 x 23 픽셀 이어야 합니다.  
  
-   명령 단추에는 더 많이 떨어져 있는 6 픽셀 이어야 합니다.  
  
 ![기본 단추 맞춤](../../extensibility/ux-guidelines/media/0801-c_buttonalign.png "0801 c_ButtonAlign")  
  
 **그림 08.01 c: 기본 단추 맞춤**  
  
#### <a name="labels"></a>레이블  
  
-   왼쪽 맞춤 모든 레이블이 있습니다.  
  
-   컨트롤 위에 배치 되는 레이블에 있습니다 해야 왼쪽 하위 컨트롤을 사용 하 여 정밀한 ' 및 레이블의 맨 아래에 다른 컨트롤 (예: 콤보 상자) 맨 위에서 5 픽셀 이어야 합니다.  
  
-   컨트롤의 왼쪽에 배치 되는 레이블에 레이블과 입력된 컨트롤 사이의 최소 너비는 10 픽셀입니다. 암시 된 두 번째 열에서 텍스트 상자, 콤보 상자나 기타 컨트롤을 정렬 하기 위해 설정 해야 합니다.  
  
-   문장의 첫 글자는 레이블과 그 뒤에 콜론이 합니다. 참조 [텍스트 스타일](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle)합니다.  
  
#### <a name="distance-between-controls"></a>컨트롤 사이의 간격  
 합리적으로 컨트롤을 쌓습니다. 누적된 컨트롤 사이의 간격에 대 한 절대 지침 되지 않습니다. 컨트롤 간의 다듬기 대화 상자가 약간 달라질 수 있습니다. 권장 간격은 세로 컨트롤/레이블 쌍에 대 한 20 픽셀이 고 가로 컨트롤/레이블 쌍에 대 한 9 픽셀입니다. 가로 쌍에 대 한 최소 제어 간격은 6 픽셀입니다.  
  
 ![컨트롤 사이의 거리를 권장](../../extensibility/ux-guidelines/media/0801-d_controldistance.png "0801 d_ControlDistance")  
  
 **컨트롤 사이의 거리에 대 한 권장 사항을 그림 08.01 d:**  
  
#### <a name="control-indentation"></a>제어 들여쓰기  
 컨트롤에 쌓이는 경우 위의 일반적으로 레이블이 컨트롤의 왼쪽된 가장자리와 가로로 내부 컨트롤을 맞춥니다.  
  
 ![컨트롤 맞춤 중첩](../../extensibility/ux-guidelines/media/0801-e_controlalign.png "0801 e_ControlAlign")  
  
 **그림 08.01 e: 중첩 컨트롤 맞춤**  
  
#### <a name="control-width"></a>컨트롤 너비  
 텍스트 상자 또는 다른 유사한 컨트롤의 너비는 필드에 대 한 평균 입력 미만 이어야 합니다. 평균 영어 단어는 5 자입니다. 예를 들어 긴 경로 이름을 요구 하는 텍스트 상자가 길어야 가로 레이아웃 허용 드롭다운은 동안 플랫폼 이름 가장 긴 항목을 사용할 수 있는 길이 이어야만 합니다.  
  
#### <a name="helper-text"></a>도우미 텍스트  
  
-   대화는 대화의 용도 대 한 자세한 정보를 제공 하는 도우미 텍스트를 표시할 수 있습니다. 이 일반적으로 위쪽에 배치 되며 1-2 문장 될 수 있습니다.  
  
-   줄 길이는 사용자를 구문 분석 하 고 읽기에 대 한 능숙 너비 여야 합니다. 중간 대화 너비가 개 이하의 550 픽셀 이어야 합니다.  
  
####  <a name="BKMK_InteriorCommandButtons"></a>내부 명령 단추  
 더 복잡 한 대화 상자, 내부 제어 대화의 커밋 단추 있는 영향을 줄 수 있는 자체 관련된 단추를 사용할 수 있습니다.  
  
-   세로 맞춤 (열)의 내부 때 단추를 사용 하 여 **확인**/**취소** 오른쪽 아래 모퉁이의 가로 방향으로 나타납니다.  
  
-   가로 맞춤 (행)의 내부 때 단추를 사용 하 여 **확인**/**취소** 오른쪽 위 모퉁이에서 세로 방향으로 나타납니다. 이 상황이 일반적이 지 않습니다.  
  
-   내부 단추 크기의 픽셀 75 x 23의 크기와 일치 하는 표준 단추 크기를 대상으로 해야 **확인**/**취소** 가능 하면 단추입니다. 단추 레이블 표준 단추 크기를 초과 하는 단추를 만드는 경우 해당 집합의 다른 단추 크기에 더 넓은 일치 해야 합니다.  
  
 ![가로 확인 및 취소 단추](../../extensibility/ux-guidelines/media/0801-f_horizokcan.png "0801 f_HorizOKCan")  
  
 **가로 확인/취소 된 세로 내부 단추가 그림 08.01-f:**  
  
 ![세로 확인 및 취소 단추](../../extensibility/ux-guidelines/media/0801-g_vertokcan.png "0801 g_VertOKCan")  
  
 **세로 확인/취소 된 가로 내부 단추가 그림 08.01 g:**  
  
#### <a name="browse-button"></a>[찾아보기...] 단추  
 **[찾아보기...]**  텍스트 상자에 따라 단추 해야 줄임표를 포함 하 여 전체에서 "찾아보기..." 쓰십시오. 공간이 긴밀 하 게 하거나 여러 개 있는 경우 **[찾아보기...]**  단추는 화면에서 단추 줄임표만 줄일 수 있습니다.  
  
##  <a name="BKMK_ThemedDialogLayout"></a>테마가 지정 된 대화 상자 레이아웃  
 Visual Studio에서 테마가 지정 된 대화 상자 어 지는 모양이 및 더 많은 흰색 공간을 제공 합니다. 강조 점점 더 개방 줄 간격 및 글꼴 크기 및 중량의 변형 제공 관심 있는 입력 체계를 제공 합니다. 가능한 경우, chrome 및 제목 표시줄 감소 되거나 제거 된 합니다. 이 대화 상자 레이아웃이 기본 패턴을 따라야 합니다.  
  
1.  대화 상자의 배경색은 흰색입니다.  
  
2.  중간 값 회색에서 1 픽셀 규칙 테두리가 있습니다.  
  
3.  대화 상자 제목 더 이상 제목 표시줄에서 하지만 시각적 효과 강조를 더 크게 포인트를 제공 합니다. (의 글꼴 크기 섹션을 참조 [텍스트 스타일](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).)  
  
4.  레이블, 설명 등의 추가 텍스트와 결합 해야 **환경 글꼴 + 굵게**합니다.  
  
5.  내부 열 연한 회색 1 픽셀 규칙에 의해 구분 됩니다.  
  
6.  기본 링크 한 밑줄이 없는지 합니다. 가리키기 및 누른된 상태에 있어야 밑줄과 색이 바뀝니다.  
  
7.  커밋 단추 (같은 **확인**/**취소**) 오른쪽 아래에 배치 합니다.  
  
### <a name="themed-dialog-layout-examples"></a>테마가 지정 된 대화 상자 레이아웃 예제  
 ![테마가 지정 된 대화 상자 레이아웃](../../extensibility/ux-guidelines/media/0801-h_themeddialog.png "0801 h_ThemedDialog")  
  
 **그림 08.01 h: 테마가 지정 된 대화 상자**  
  
 ![테마가 지정 된 대화 크기](../../extensibility/ux-guidelines/media/0801-i_themeddialogdimensions.png "0801 i_ThemedDialogDimensions")  
  
 **그림 08.01-i: 테마가 지정 된 대화 상자-차원**  
  
 ![테마가 지정 된 대화 상자 글꼴](../../extensibility/ux-guidelines/media/0801-j_themeddialogfonts.png "0801 j_ThemedDialogFonts")  
  
 **그림 08.01 j: 테마가 지정 된 대화 상자-글꼴**  
  
 ![테마가 지정 된 대화 상자 색](../../extensibility/ux-guidelines/media/0801-k_themeddialogcolors.png "0801 k_ThemedDialogColors")  
  
 **그림 08.01-k: 테마가 지정 된 대화 상자-색**  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에 대 한 응용 프로그램 패턴](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md)   
 [컨트롤 (Windows)](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx)   
 [대화 상자 (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx)