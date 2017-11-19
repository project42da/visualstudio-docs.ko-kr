---
title: "Visual Studio에 대 한 UX Essentials | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a793cf7a-f230-43ce-88d0-fa5d6f1aa9c7
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 368540b909536523515ea610e509b22600628f81
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ux-essentials-for-visual-studio"></a>Visual Studio에 대 한 UX Essentials
## <a name="best-practices"></a>최선의 구현 방법  
  
### <a name="1-be-consistent-within-the-visual-studio-environment"></a>1. Visual Studio 환경 내에서 일관 되어야 합니다.  
  
-   기존에 따라 [상호 작용 패턴](interaction-patterns-for-visual-studio.md) 셸에서 합니다.  
  
-   셸 비주얼 언어와 일치 하도록 기능을 디자인 및 [장인 요구 사항](evaluation-tools-for-visual-studio.md)합니다.  
  
-   사이트가 있는 경우 공유 명령 및 컨트롤을 사용 합니다.  
  
-   Visual Studio 계층 구조와 컨텍스트를 설정 하 고 UI 드라이브 방법을 이해 합니다.  
  
### <a name="2-use-the-environment-service-for-fonts-and-colors"></a>2. 글꼴 및 색에 대 한 환경 서비스를 사용 합니다.  
  
-   UI에 현재 따라야 [환경 글꼴](fonts-and-formatting-for-visual-studio.md) 옵션 대화 상자에서 글꼴 및 색 페이지에서 사용자 지정에 대 한 노출 되는 경우가 아니면 설정 합니다.  
  
-   UI 요소를 사용 해야 합니다는 [VSColor 서비스](colors-and-styling-for-visual-studio.md)를 사용 하 여 공유 환경 토큰 또는 기능별 토큰입니다.  
  
### <a name="3-make-all-imagery-consistent-with-the-new-vs-style"></a>3. 모든 이미지를 새 VS 스타일을 일관 되 게 합니다.  
  
-   아이콘, 문자 모양 및 기타 그래픽에 대 한 Visual Studio 디자인 원칙을 따릅니다.  
  
-   그래픽 요소에 텍스트를 배치 하지 마십시오.  
  
### <a name="4-design-from-a-user-centric-perspective"></a>4. 사용자 중심 관점에서 디자인 합니다.  
  
-   내 개별 기능 하기 전에 작업 흐름을 만듭니다.  
  
-   사용자가 잘 알고 있어야 하 고이 정보를 사용자 사양에서 명시적으로 확인 합니다.  
  
-   UI를 검토할 때는 세부 정보 뿐만 아니라 전체 환경을 평가 합니다.  
  
-   기능 및 로캘 또는 언어에 관계 없이 편리 하 게 유지 되도록 UI를 디자인 합니다.  
  
## <a name="screen-resolution"></a>화면 해상도  
  
### <a name="minimum-resolution"></a>최소 해상도  
 - Visual Studio d e v 14 최소 해결책은 **1280 x 720**합니다. 즉, 인지 *가능한* 최적의 사용자 환경을 것이 해상도에서 Visual Studio를 사용 하도록 합니다. 모든 측면 1280 x 720 보다 낮은 해상도에서 사용할 수 있는 된다는 보장이 없습니다.  
  
 - Visual Studio에 대 한 대상 해상도 **1366x768**합니다. 이것은 promise 우리는 낮은 해상도 *좋은* 사용자 경험 합니다.

 - 초기 대화 높이 해야 **700 픽셀 보다 작은**이므로 96dpi에서 IDE 프레임의 최소 해상도 맞게 합니다.
  
### <a name="high-density-displays"></a>고밀도 표시  
 Visual Studio에서 UI 모든 DPI 배율 즉시 Windows 지원 계수에서 제대로 작동 해야 합니다: 150%, 200% 및 %250입니다.  
  
## <a name="anti-patterns"></a>안티패턴  
 Visual Studio 우리의 지침 및 모범 사례에 따라 UI의 많은 예제를 포함 합니다. 일관성을 유지 하기 위해, 개발자가 작성 중인 어떤 비슷합니다 제품 UI 디자인 패턴에서 빌릴 경우가 많습니다. 이 사용자 상호 작용 및 시각적 디자인의 일관성이 드라이브 우리도 유용 않는 경우에 따라 출시 우선 순위 지정을 제거 하거나 일정 제약 조건으로 인해 기준을 충족 하지 않는 몇 가지 세부 사항은로 기능 하는 좋은 방법은 합니다. 이러한 경우 바람직하지 팀 이러한 "안티패턴" 중 하나를 복사 하는 데 Visual Studio 환경 내에서 잘못 되었거나 일치 하지 않는 UI를 마이그레이션하거나 때문에 합니다.  
  
### <a name="required-fieldssettings-shown-in-error-state-by-default"></a>기본적으로 오류 상태에 표시 하는 필수 필드/설정  
  
#### <a name="feature-team-goals"></a>기능 팀의 목표  
  
-   가 구성 해야 하는 요소를 추가 했습니다 있는지에 대 한 경고를 표시 합니다.  
  
-   사용자의 주를를 입력 해야 하는 영역을 그립니다.  
  
#### <a name="anti-pattern-solution"></a>안티패턴 솔루션  
 사용자에는 작업을 시작 하는 즉시 및 작업 완료 전에 중지 중요 아이콘 즉시 구성 해야 하는 영역 옆에 배치 합니다.  
  
#### <a name="example-manifest-designer-declarations"></a>예: 매니페스트 디자이너 선언  
 즉시 목록에 선언을 추가 필수 속성을 설정 하는 사용자 때까지 유지 하는 오류 상태에 배치 합니다.  
  
 이 경우 추가 문제 때문에 않습니다 경고에 사용 되는 아이콘을 포함 한 "&times;" 아이콘을 옆에 있는 공용 제거 아이콘을 사용할 수 없습니다. 결과적으로, UI 컨트롤을 더 이상 사용 하지 않게 제거 단추를 사용합니다.  
  
 ![Visual Studio 안티패턴은 기본적으로 UI 오류 상태에 배치 합니다. ] (../../extensibility/ux-guidelines/media/manifestdesignererrordeclarationsanti-pattern.png "ManifestDesignererrordeclarationsanti 패턴")<br />Visual Studio 안티패턴은 기본적으로 UI 오류 상태에 배치 합니다.
  
#### <a name="alternatives"></a>대체 방법  
 이 문제를 보다 나은 솔루션을 합니다.  
  
-   사용자 경고 없이 선언을 추가 하도록 허용 하 고 항목의 속성을 설정 즉시 이동 합니다.  
  
-   경고 아이콘 (금 삼각형)를 추가할 때 포커스가 이동은 항목에서와 같은 다른 선언 목록에 추가 하거나 디자이너 내에서 탭을 변경 하려고 합니다.  
  
-   사용자가 모든 선언에 속성을 설정 하기 전에 탭을 변경 하려고 하는 경우 응용 프로그램이 빌드되지 것입니다 설명 하는 대화 상자를 팝 (또는 어떤 의미) 경고를 해결 합니다. 사용자는 대화 상자를 해제 하 고 탭을 변경 하는 경우 그래도 다음 아이콘 (위험 또는 경고, 적절 하 게)에 추가 됩니다 면 선언 탭.  
  
### <a name="multiple-clicks-to-dismiss-ui"></a>UI를 해제 하려면를 여러 번 클릭  
  
#### <a name="feature-team-goals"></a>기능 팀의 목표  
 첫 번째는 설명 텍스트를 표시 하지 않고 UI를 해제 하려면 사용자를 허용 하지 않음.  
  
#### <a name="anti-pattern"></a>안티패턴  
 VS UI 내에서 다양 한 위치에 비디오 링크를 삽입 하는 팀의 일반적인 패턴에 대 한 결정은 "&times;" 연결 "다시 표시 안 함" 및 닫기 단추 및 도구 설명으로, UX로 지정 된 설명과 대신 드롭 다운을 구현 합니다.  

#### <a name="example-video-links-in-team-explorer"></a>예: 팀 탐색기에서 비디오 링크
사용자가 UI를 해제 하기 전에 설명 텍스트를 읽을 하는 것은 Visual Studio 내에서 바이러스는 패턴입니다. 올바르게 디자인 된, 비디오 링크가 hover에 및 클릭 하면 추가 정보와 함께 도구 설명이 표시 되는 "&times;" 더 이상의 상호 작용에 대 한 필요 없이 메시지를 해제 해야 합니다.


 ![설명 텍스트 anti #45 패턴 &; #45 잘못 된](../../extensibility/ux-guidelines/media/incorrectuseofmultipleclicks.png "Incorrectuseofmultipleclicks")<br />잘못 된 비디오 링크가 패턴
  
#### <a name="result"></a>결과  
 닫기 단추 (한 번의 클릭)는 단순 하지 않고 사용자는 단순히 비디오 링크가 표시 되는 모든 곳에서 UI를 해제 하려면를 두 번 클릭을 사용 하도록 강제 합니다.  
  
#### <a name="alternatives"></a>대체 방법  
 이러한 상황에 대 한 올바른 디자인 Internet Explorer, Office 및 Visual Studio를 일반 패턴을 따를 것: 가리키기, 사용자가 도구 설명을 볼 수와 한 번의 클릭 UI를 숨깁니다.  
  
 ![설명 텍스트 anti #45 패턴 &; #45 올바른](../../extensibility/ux-guidelines/media/explanatorytextanti-pattern-correct.png "Explanatorytextanti 패턴 해결")<br />올바른 비디오 링크가 패턴
  
### <a name="using-command-bars-for-settings"></a>명령 모음 설정에 대 한 사용  
 **그림 A** 이 안티패턴 나타냅니다: 보다 더 명령에 적용 되는 명령 단추 아래 설정을 추가 합니다. 이 스케치에서은 외에도 디버깅 시작 명령-브라우저, 디버깅 하지 않고 시작 및 한 단계씩 코드 실행에서 보기와 같은-선택한 설정 존중입니다.  

  ![A: 그림 명령 안티패턴 모음](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurea.png "Commandbaranti-패턴-FigureA")<br />A: 그림 명령 모음 안티패턴
  
 조금 더 나은 없지만 바람직하지 지정 하는 것이 유형의 설정의 도구 모음에서와 같이 **그림 B**합니다. 분할 단추 적은 공간을 차지 하 고 드롭다운을 통해 향상 되므로, 두 디자인 계속 사용 하는 도구 모음은 명령을 실제로 아닌 개체를 승격 하 합니다.  
 
 ![그림 b: 나타낼지, 하지만 여전히는 명령 모음 안티패턴](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figureb.png "Commandbaranti-패턴-FigureB")<br />그림 b: 향상 되었지만 여전히는 명령 모음 안티패턴
 
  에 표시 된 올바른 접근 방식에서 **그림 C**, 일련의 명령에 설정을 연결 됩니다. 설정 되 고 전역 설정이 없습니다 및 4 개 명령은 방금 전환 하는 것입니다. 명령을 도구 모음에서 허용 되는 경우에만입니다. 

 ![그림 c: Visual Studio 명령 모음 패턴을 사용 하 여 해결](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurec.png "Commandbaranti-패턴-FigureC")<br />Visual Studio 명령 모음 패턴의 그림 c: 올바른 사용
   
### <a name="control-anti-patterns"></a>컨트롤 패턴  
 일부 패턴은 단순히 잘못 된 사용 또는 컨트롤 또는 컨트롤 그룹을 표시 합니다.  
  
#### <a name="underlining-used-as-a-group-label-not-a-hyperlink"></a>하이퍼링크 하지을 그룹 레이블로 사용 되는 밑줄 표시  
 하이퍼링크에 대 한 밑줄 텍스트를 사용 해야 합니다.  
  
 **잘못 된:**    
 ![밑줄이 그어진된 텍스트 하이퍼링크를 Visual Studio 바이러스 패턴입니다. ] (../../extensibility/ux-guidelines/media/0102-g_grouplabelincorrect.png "0102 g_GroupLabelIncorrect")<br />밑줄이 그어진된 텍스트 하이퍼링크를 Visual Studio 바이러스 패턴입니다.
  
 **좋은:**   
 ![올바르게 스타일의 비 하이퍼링크 텍스트 유사점이 환경 글꼴로 표시 합니다. ] (../../extensibility/ux-guidelines/media/0102-h_grouplabelcorrect.png "0102 h_GroupLabelCorrect")<br />올바르게 스타일의 비 하이퍼링크 텍스트 유사점이 환경 글꼴로 표시 합니다.
  
#### <a name="clicking-on-a-check-box-results-in-a-pop-up-dialog"></a>팝업 대화 상자에서 확인란 결과 사용 하 여 클릭 하면  
 즉시 "Windows Azure 응용 프로그램 게시" 마법사에서 "모든 역할에 원격 데스크톱 사용" 확인란을 클릭 하면 Visual Studio 안티패턴 팝업 대화 상자에서 나타납니다. 또한 확인란 필드를 채우지 확인란을 선택한 후 다른 상호 작용 안티패턴 합니다.  
  
 ![Visual Studio 안티패턴 되는 확인란을 클릭 하는 대화 상자를 표시 합니다. ] (../../extensibility/ux-guidelines/media/0102-i_checkboxpopup.png "0102 i_CheckboxPopup")<br />Visual Studio 안티패턴 되는 확인란을 클릭 하는 대화 상자를 표시 합니다.
  
### <a name="hyperlink-anti-patterns"></a>하이퍼링크 안티패턴  
 다음 예제에서는 두 개의 패턴을 포함합니다.  
  
1.  Hover에 빨간색 켜는 전경 글꼴 서비스에서 올바른 공유 색 사용 되지 않기를 의미 합니다.  
  
2.  개념 항목에 대 한 링크에 대 한 적절 한 텍스트 않습니다 "자세히". 사용자의 목표는 하지 자세한 내용, 원하는 결과 이해 하는 것입니다.  
  
 ![색 서비스를 무시 하 고 "자세히" 하이퍼링크에 대 한 사용 하 여 Visual Studio 안티패턴 됩니다. ] (../../extensibility/ux-guidelines/media/0102-j_hyperlinkincorrect.png "0102 j_HyperlinkIncorrect")<br />색 서비스를 무시 하 고 "자세히" 하이퍼링크에 대 한 사용 하 여 Visual Studio 안티패턴 됩니다.  
  
 **향상 된 솔루션:** 링크를 클릭 하 여 사용자가 대하여 질문 합니다.  
  
-   Windows Azure 서비스는 어떻게 작동 하나요?  
  
-   Windows Azure 모바일 서비스 프로젝트는 경우 필요 합니까?  
  
#### <a name="using-click-here-for-links"></a>"여기를 클릭 하십시오" 링크를 사용 하 여  
 하이퍼링크 이름은 이어야 합니다. "여기를 클릭"을 사용 하는 것이 안티패턴 또는 유사한 변형 않습니다.  
  
 **잘못 된:** "합니다. 새 프로젝트를 만드는 방법에 대 한 합니다."
  
 **확인 된:** "새 프로젝트를 어떻게 만들려면 하나요?"