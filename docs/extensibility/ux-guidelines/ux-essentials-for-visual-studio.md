---
title: "Visual Studio 용 UX Essentials | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a793cf7a-f230-43ce-88d0-fa5d6f1aa9c7
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# Visual Studio 용 UX Essentials
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

## 최선의 방법  
  
### 1. Visual Studio 환경 내에서 일관 되어야 합니다.  
  
-   셸 내에서 기존 상호 작용 패턴을 따릅니다.  
  
-   셸의 시각적 언어 및 장인 요구와 일치 하도록 기능을 디자인 합니다.  
  
-   존재 하는 경우 공유 명령 및 컨트롤을 사용 합니다.  
  
-   Visual Studio 계층 구조 및 컨텍스트를 설정 및 UI 드라이브 방법을 이해 합니다.  
  
### 2. 글꼴 및 색에 대 한 환경 서비스를 사용 합니다.  
  
-   UI 옵션 대화 상자의 글꼴 및 색 페이지에서 사용자 지정에 대 한 노출 되는 현재 환경 글꼴 설정을 따라야 합니다.  
  
-   UI 요소에는 공유 환경 토큰 또는 기능별 토큰을 사용 하 여 VSColor 서비스를 사용 해야 합니다.  
  
### 3. 모든 이미지를 새 VS 스타일으로 일치 하도록 해야 합니다.  
  
-   아이콘, 문자 모양 및 기타 그래픽에 대 한 Visual Studio 디자인 원칙을 따릅니다.  
  
-   그래픽 요소에 텍스트를 배치 하지 마십시오.  
  
### 4. 사용자 중심 관점에서 디자인 합니다.  
  
-   내의 개별 기능 하기 전에 작업 흐름을 만듭니다.  
  
-   사용자가 잘 알고 있어야 하 고 지식을 하려면 사양에서 명시적으로 만들어야 합니다.  
  
-   UI를 검토할 때 세부 정보 뿐만 아니라 완벽 한 환경을 평가 합니다.  
  
-   작동 하 고 매력적인 로캘이나 언어에 관계 없이 그대로 있도록 UI를 디자인 합니다.  
  
## 화면 해상도  
  
### 최소 해상도  
 Visual Studio Dev14에 대 한 최소 해상도 1280 x 1024입니다. 즉, 인지 *가능한* 최적의 사용자 환경을 것이 해상도에서 Visual Studio를 사용 합니다. 모든 측면 1280 x 1024 보다 낮은 해상도로 사용할 수 있는 된다는 보장이 없습니다.  
  
 초기 대화 크기 1000이 최소 해상도 96dpi에서 내에서 IDE의 프레임 내에 포함 하도록 높이 픽셀을 넘지 않아야 합니다.  
  
### 고밀도 표시  
 Visual Studio에서 UI 배율은 Windows는 기본적으로 지원 되는 모든 DPI에서 잘 작동 해야 합니다: 150%, 200%, 및 250%입니다.  
  
## 패턴 방지  
 Visual Studio는 우리의 지침 및 모범 사례에 따라 UI의 많은 예제를 포함 합니다. 일관성을 유지 하기 위한 노력을 개발자가 자주 작성 중인 어떤 비슷합니다 제품 UI 디자인 패턴에서 빌린 합니다. 하지만 이것이 바람직합니다는 우리 드라이브 일관성 사용자 상호 작용 및 시각적 디자인에도 유용 않는 경우에 따라 제공 우선 순위 지정을 제거 하거나 일정 제약으로 인해 기준을 충족 하지 않는 몇 가지 세부 정보가 포함 된 기능입니다. 이러한 경우에 사용 하지 않는 것 팀이 이러한 "안티패턴" 중 하나를 복사 하는 Visual Studio 환경 내에서 잘못 되었거나 일치 하지 않는 UI를 증가 하기 때문에 있습니다.  
  
### 기본적으로 오류 상태에서 표시 하는 필수 필드\/설정  
  
#### 기능 팀의 목표  
  
-   추가 했다고 구성 해야 하는 요소에는 사용자에 게 경고 합니다.  
  
-   입력 해야 하는 영역에 사용자의 주를 그립니다.  
  
#### 안티패턴 솔루션  
 사용자가 시작한 작업 하는 즉시 및 이러한 작업을 완료 하기 전에 즉시 구성 해야 하는 영역 옆에 있는 중요 한 중지 아이콘을 배치 합니다.  
  
#### 예: 매니페스트 디자이너 선언  
 선언 목록에 추가 즉시 사용자는 필요한 속성을 설정 될 때까지 유지 하는 오류 상태에 배치 됩니다.  
  
 이 경우 "x"를 포함 하는 경고에 사용 되는 아이콘 않으므로 생각 됩니다, 그리고 공통 제거 되므로 아이콘 옆에 사용할 수 없습니다. 결과적으로, UI 컨트롤을 더 이상 사용 하지 않게 제거 단추를 사용합니다.  
  
 ![Manifest Designer error declaration anti&#45;pattern](../../extensibility/ux-guidelines/media/manifestdesignererrordeclarationsanti-pattern.png "ManifestDesignererrordeclarationsanti\-pattern")  
  
 **기본적으로 오류 상태에 UI를 배치 하는 것은 Visual Studio 방지 패턴입니다.**  
  
#### 대안  
 이 문제를 보다 나은 솔루션을 것입니다.  
  
-   경고 없이 선언을 추가 하는 데 사용할 수 하 고 항목의 속성을 설정 하려면 바로 이동 합니다.  
  
-   경고 아이콘 \(골드 삼각형\)을 추가할 때 포커스가 이동 항목에서 같은 다른 선언 목록에 추가 하거나 디자이너 내에서 탭을 변경 하려고 합니다.  
  
-   선언에서 속성을 설정 하기 전에 탭을 변경 하려고 하는 경우 응용 프로그램이 빌드되지 것입니다 설명 하는 대화 상자 표시 \(또는 어떤 의미\) 경고를 해결 합니다. 사용자는 대화 상자를 해제 하 고 탭을 변경 하는 경우 그래도 다음 아이콘 \(위험 또는 경고를 적절 하 게\)은 탭에 추가 선언 합니다.  
  
### 사용자가 UI를 해제 하기 전에 텍스트 읽기  
  
#### 기능 팀의 목표  
 사용자를 첫 번째는 설명 텍스트를 표시 하지 않고 UI를 해제할 수 없습니다.  
  
#### 안티패턴  
 X의 일반적인 패턴에 대해 결정 VS UI 내에서 다양 한 위치에 비디오 링크를 삽입 하는 팀 UX에 의해 지정 된 대로 단추 및 도구 설명을 설명 닫고 대신 드롭다운 및 "다시 표시 안 함" 링크를 구현 합니다.  
  
 ![Explanatory text anti&#45;pattern &#45; incorrect](../../extensibility/ux-guidelines/media/incorrectuseofmultipleclicks.png "Incorrectuseofmultipleclicks")  
  
 **: 잘못 된 사용자가 UI를 해제 하기 전에 설명 텍스트를 읽기 강제는 안티패턴 Visual Studio 내에서입니다.**  
  
#### 결과  
 간단한 닫기 단추 \(한 번의 클릭\) 하는 대신 사용자를 두 번 클릭을 사용 하 여 단순히 비디오 링크가 표시 되는 모든 위치에서 UI를 해제할 해야 합니다.  
  
#### 대안  
 이러한 상황에 대 한 올바른 디자인 Internet Explorer, Office 및 Visual Studio에 일반적인 패턴을 수행 하는 것: 가리키기, 사용자가 도구 설명을 볼 수 고 한 번의 클릭 UI를 숨깁니다.  
  
 ![Explanatory text anti&#45;pattern &#45; correct](../../extensibility/ux-guidelines/media/explanatorytextanti-pattern-correct.png "Explanatorytextanti\-pattern\-correct")  
  
 **: 비디오 링크 가리키기, 추가 정보와 함께 도구 설명이 표시 됩니다, 정상적으로 올바르고 "X"를 클릭 하면 사용자가 개입할 필요 없이 메시지를 해제 해야 합니다.**  
  
### 명령 모음을 사용 하 여 설정에 대 한  
 ![Command bar anti&#45;pattern &#45; Figure A](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurea.png "Commandbaranti\-pattern\-FigureA")  
  
 **그림 a: 명령 모음 안티패턴**  
  
 **그림 A** 백신이 패턴을 나타내는: 단순히 명령에 적용 되는 명령 단추 아래에 있는 설정을 입력 합니다. 이 스케치에서은 외에도 디버깅 시작 명령\-형식 브라우저, 디버깅 하지 않고 시작 및 한 단계씩 코드 실행에 대 한 보기\-하는 선택한 설정을 그대로 따릅니다.  
  
 ![Command bar anti&#45;pattern &#45; Figure B](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figureb.png "Commandbaranti\-pattern\-FigureB")  
  
 **그림 2: 좀 나아 보이긴 하지만 여전히는 명령 모음 안티패턴**  
  
 약간 더 우수 하지만 여전히 바람직하지 지정 하는 것이 유형의 설정의 도구 모음에서와 같이 **그림 B**합니다. 분할 단추 적은 공간을 차지 하 고 드롭다운을 통해 향상 되므로 하는 동안 두 디자인 여전히 사용 하는 도구 모음 명령을 실제로 이외의 내용이 승격 하 합니다.  
  
 ![Command bar anti&#45;pattern &#45; Figure C](../../extensibility/ux-guidelines/media/commandbaranti-pattern-figurec.png "Commandbaranti\-pattern\-FigureC")  
  
 **Visual Studio 명령 모음 패턴의 그림 c: 올바른 사용**  
  
 **그림 C**, 설정을 일련의 명령에 연결 됩니다. 설정 되 고 전역 설정이 없습니다 우리 명령 4 개 사이의 전환 하기만 하 고 도구 모음에서 명령을 허용 되는 경우에만입니다.  
  
### 컨트롤 패턴 방지  
 일부 패턴 방지은 단순히 잘못 된 사용 또는 프레젠테이션 컨트롤 또는 컨트롤 그룹입니다.  
  
#### 하이퍼링크 하지을 그룹 레이블로 사용 되는 밑줄 표시  
 하이퍼링크에 대 한 밑줄 텍스트를 사용 해야 합니다.  
  
 **잘못 되었습니다.**  
  
 ![Underlining anti&#45;pattern in group labels](../../extensibility/ux-guidelines/media/0102-g_grouplabelincorrect.png "0102\-g\_GroupLabelIncorrect")  
  
 **밑줄이 그어진 되지 않은 텍스트를 하이퍼링크는 Visual Studio 방지 패턴입니다.**  
  
 **좋은:**  
  
 ![Underlining anti&#45;pattern in group labels &#40;correct&#41;](../../extensibility/ux-guidelines/media/0102-h_grouplabelcorrect.png "0102\-h\_GroupLabelCorrect")  
  
 **올바르게 스타일의 비 하이퍼링크 텍스트 되지 않은 환경 글꼴로 표시 합니다.**  
  
#### 팝업 대화 상자에서 확인란 결과 클릭 하면  
 즉시 "Windows Azure 응용 프로그램 게시" 마법사에서 "모든 역할에 대 한 원격 데스크톱 사용" 확인란을 클릭 하면 Visual Studio 안티패턴 팝업 대화 상자에서 나타납니다. 또한 확인란 필드를 채우지 확인란이 선택 되 고 후 다른 상호 작용 방지 패턴입니다.  
  
 ![Checkbox pop&#45;up anti&#45;pattern](../../extensibility/ux-guidelines/media/0102-i_checkboxpopup.png "0102\-i\_CheckboxPopup")  
  
 **Visual Studio 안티패턴 되는 확인란을 클릭 하는 대화 상자를 표시 합니다.**  
  
### 하이퍼링크 안티패턴  
 다음 예제에서는 두 개의 패턴을 포함합니다.  
  
1.  호버 켜기 빨간색 전경 글꼴 서비스에서 올바른 공유 색 사용 되 고 되지 않음을 의미 합니다.  
  
2.  개념 항목에 대 한 링크에 대 한 적절 한 텍스트 아닙니다 "자세히". 사용자의 목표는 하지 자세한 내용, 원하는 결과 잘 이해 하는 것입니다.  
  
 ![Hyperlink anti&#45;patterns](../../extensibility/ux-guidelines/media/0102-j_hyperlinkincorrect.png "0102\-j\_HyperlinkIncorrect")  
  
 **컬러 서비스를 무시 하 고 "자세히" 하이퍼링크를 사용 하는 Visual Studio 방지 패턴입니다.**  
  
 **향상 된 솔루션:** 링크를 클릭 하 여 사용자를 묻는 것 질문을 야기 합니다.  
  
-   Windows Azure 서비스는 어떻게 작동 하는가?  
  
-   Windows Azure 모바일 서비스 프로젝트를 사용 하는 경우 필요 합니까?  
  
#### "여기를 클릭" 링크를 사용 하 여  
 하이퍼링크는 자체 설명적 이어야 합니다. 에 "클릭"를 사용 하는 안티패턴 유사한 다른 변형이 있습니다.  
  
 **불량:** "여기를 클릭을 새 프로젝트를 만드는 방법에 대 한 지침은."  
  
 **좋은:** "어떻게 만듭니까 새 프로젝트?"