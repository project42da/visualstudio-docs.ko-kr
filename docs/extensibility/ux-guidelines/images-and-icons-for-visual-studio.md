---
title: "이미지와 Visual Studio에 대 한 아이콘 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f410325e-9cf2-4f39-b6d7-b672121c2691
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 이미지와 Visual Studio에 대 한 아이콘
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

##  <a name="a-namebkmkimageuseinvisualstudioa-image-use-in-visual-studio"></a><a name="BKMK_ImageUseInVisualStudio"></a> Visual Studio에서 이미지 사용  
 아트 워크를 만들기 전에 고려 하는 데에 1, 000 + 이미지의 사용은 [Visual Studio 이미지 라이브러리](http://www.microsoft.com/en-my/download/details.aspx?id=35825)합니다.  
  
### <a name="types-of-images"></a>이미지 형식  
  
-   **아이콘**합니다. 명령, 계층, 템플릿 및 등에 나타나는 작은 이미지. Visual Studio에서 사용 되는 기본 아이콘 크기는 16 x 16 PNG. 아이콘 이미지 서비스에서 자동으로 생성 된 HDPI 지원에 대 한 XAML 형식을 생성 합니다.  
  
     **참고:** 이미지는 메뉴 시스템으로 사용 하는 동안 모든 명령에 대 한 아이콘 만들지 마십시오. 참조 [메뉴와 Visual Studio 명령](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md) 명령 아이콘을 가져와야 하는지 여부를 볼 수 있습니다.  
  
-   **미리 보기입니다.** 새 프로젝트 대화 상자와 같은 대화 상자에서 미리 보기 영역에 사용 된 이미지입니다.  
  
-   **대화 상자 이미지입니다.** 대화 상자 또는 마법사 설명이 포함 된 그래픽 또는 메시지 표시기에 표시 되는 이미지입니다. 사용자의 주의 (알림, 경고)를 얻거나 어려운 개념을 설명 하는 데 필요한 경우에 및 자주 사용 합니다.  
  
-   **애니메이션된 이미지입니다.** 진행률 표시기, 상태 표시줄 및 작업 대화 상자에 사용 합니다.  
  
-   **커서가 없습니다.** 여기서는 개체 삭제 될 수 있습니다 등과 하 고 마우스를 사용 하는 작업이 허용 되는지 여부를 지정 하는 데 사용 합니다.  
  
##  <a name="a-namebkmkicondesigna-icon-design"></a><a name="BKMK_IconDesign"></a> 디자인 아이콘  
  
### <a name="overview"></a>개요  
 Visual Studio는 클린 기 하 도형 및 긍정/부정 (빛/진한) 50/50 균형 있고 직접적이 고 이해 하기 쉽게 메타포를 사용 하 여 최신 스타일 아이콘을 사용 합니다. 중요 아이콘 디자인 센터 명확성, 단순화, 및 컨텍스트를 가리킵니다.  
  
-   **명확성:** 의미와과 가까운 거리에 해당 아이콘을 제공 하는 핵심 비유에 집중 합니다.  
  
-   **간소화:** 의 핵심 의미에 아이콘을 줄이기 위해을 받으십시오. 테마 필요한 요소에만와 없는 포함 합니다.  
  
-   **컨텍스트:** 는 아이콘의 핵심 비유를 구성 하는 요소를 결정 하는 데 중요 개념 개발 하는 동안 아이콘의 역할의 모든 측면을 고려해 야 합니다.  
  
 아이콘을 방지 하려면 디자인 점의 개수를 사항이.입니다.  
  
-   적절 한 경우를 제외 하 고 UI 요소를 나타내는 아이콘을 사용 하지 마십시오. UI 요소는 일반, 분명 하 게, 아니고 고유 더 이론적으로 또는 기호화 된 접근 방식을 선택 합니다.  
  
-   문서, 폴더, 화살표 및 돋보기 효과 만들기와 같은 공통 요소를 남용 하지 마십시오. 아이콘의 의미에 필수적인 경우에 이러한 요소를 사용 합니다. 예를 들어, 오른쪽을 향한 돋보기 검색만 나타내야 탐색 및 찾기.  
  
-   하지만 일부 레거시 아이콘 요소 관점의 사용을 지속적으로 만들지 마십시오 새 아이콘 관점 요소에 매개 변수가 없으면 명확성 부족 하지 않으면.  
  
-   아이콘에 너무 많은 정보를 cram 하지 마십시오. 쉽게 인식 하거나 인식할 수 있는 기호로 배웠습니다를 실행할 수 있는 간단한 이미지는 지나치게 복잡 한 이미지 보다 훨씬 더 유용 합니다. 아이콘과 전반적인 성능을 파악할 수 없습니다.  
  
### <a name="icon-creation"></a>아이콘 만들기  
  
#### <a name="concept-development"></a>개념 개발  
 Visual Studio는 다양 한 아이콘 형식 UI 내 있습니다. 아이콘 유형을 개발 하는 동안 주의 합니다. 아이콘 요소에 대 한 명확 하지 않거나 일반적이 지 않은 UI 개체를 사용 하지 마십시오. 선택의 경우 이러한 바로 가기와 같은 스마트 태그 아이콘으로 합니다. 왼쪽에서 태그를 추상의 의미는 오른쪽에 모호한, UI 기반 버전 보다 더욱 명확 합니다.  
  
|||  
|-|-|  
|**기호 이미지의 올바른 사용**|**기호화 된 이미지를 잘못 사용 했습니다.**|  
|![올바른 스마트 태그 아이콘](../../extensibility/ux-guidelines/media/0404-01_smarttagcorrect.png "0404-01_SmartTagCorrect")|![잘못된 스마트 태그 아이콘](../../extensibility/ux-guidelines/media/0404-02_smarttagincorrect.png "0404-02_SmartTagIncorrect")|  
  
 표준, 쉽게 인식할 수 있는 UI 요소 아이콘에 대 한 작업 실행을 수행 하는 인스턴스가 있습니다. 창도 이와 같이 추가 합니다.  
  
|||  
|-|-|  
|**아이콘에 올바른 UI 요소**|**아이콘에 잘못 된 UI 요소**|  
|![올바른 창 추가 아이콘](../../extensibility/ux-guidelines/media/0404-03_addwindowcorrect.png "0404-03_AddWindowCorrect")|![잘못된 창 추가 아이콘](../../extensibility/ux-guidelines/media/0404-04_addwindowincorrect.png "0404-04_AddWindowIncorrect")|  
  
 아이콘의 의미 하는 데 중요 하지 않은 문서를 기본 요소로 사용 하지 마십시오. 문서 없이 새로 고침으로 인해 문서 요소는 의미를 하는 데 필요한 추가 문서 (아래) 의미 요소 손실 됩니다.  
  
|||  
|-|-|  
|**문서 아이콘의 올바른 사용**|**잘못 사용 하면 문서 아이콘**|  
|![올바른 문서 아이콘](../../extensibility/ux-guidelines/media/0404-05_documenticoncorrect.png "0404-05_DocumentIconCorrect")|![잘못된 문서 아이콘](../../extensibility/ux-guidelines/media/0404-06_documenticonincorrect.png "0404-06_DocumentIconIncorrect")|  
  
 "Show"의 개념은 표시 되는 항목을 같은 모든 파일 표시 예제와 마찬가지로 가장 잘 표현 하는 아이콘으로 나타나야 합니다. 리소스 뷰 예제와 같이 필요한 경우 "보기"의 개념을 나타내기 위해 렌즈 메타포를 사용할 수 있습니다.  
  
|||  
|-|-|  
|**"표시"**|**"보기"**|  
|![표시 아이콘](../../extensibility/ux-guidelines/media/0404-07_show.png "0404-07_Show")|![뷰 아이콘](../../extensibility/ux-guidelines/media/0404-08_view.png "0404-08_View")|  
  
 오른쪽을 향한 나타내는 검색 하도록 유리 아이콘 확대, 찾기, 및 찾아보기입니다. 더하기 기호 또는 빼기 기호 왼쪽 위치 변형 해야 나타내는 유일한 확대/축소 합니다.  
  
|||  
|-|-|  
|**"검색"**|**"확대/축소"**|  
|![검색 아이콘](../../extensibility/ux-guidelines/media/0404-09_search.png "0404-09_Search")|![확대/축소 아이콘](../../extensibility/ux-guidelines/media/0404-10_zoom.png "0404-10_Zoom")|  
  
 트리 보기에서 폴더 아이콘와 한정자를 사용 하지 마십시오. 사용 가능한 경우 한정자만 사용 합니다.  
  
|||  
|-|-|  
|**올바른 트리 뷰 아이콘**|**잘못 된 트리 뷰 아이콘**|  
|![올바른 트리 뷰 아이콘 &#40; 1 &#41;](../../extensibility/ux-guidelines/media/0404-11_treeviewcorrect1.png "0404-11_TreeViewCorrect1") ![올바른 트리 뷰 아이콘 &#40; 2 &#41;](../../extensibility/ux-guidelines/media/0404-12_treeviewcorrect2.png "0404-12_TreeViewCorrect2")|![잘못 된 트리 뷰 아이콘 &#40; 1 &#41;](../../extensibility/ux-guidelines/media/0404-13_treeviewincorrect1.png "0404-13_TreeViewIncorrect1") ![잘못 된 트리 뷰 아이콘 &#40; 2 &#41;](../../extensibility/ux-guidelines/media/0404-14_treeviewincorrect2.png "0404-14_TreeViewIncorrect2")|  
  
### <a name="style-details"></a>스타일 세부 정보  
  
#### <a name="layout"></a>레이아웃  
 표준 16 x 16 아이콘에 대 한 예제와 같이 요소를 스택:  
  
 ![16 x 16 아이콘에 대한 레이아웃 스택](../../extensibility/ux-guidelines/media/0404-15_layoutstack.png "0404-15_LayoutStack")  
  
 **16 x 16 아이콘에 대 한 레이아웃 스택**  
  
 상태 알림 요소는 독립 실행형 아이콘으로 사용 되는 더 합니다. 그러나는 알림을 해야에 쌓을 수는 기본 요소와 같은 작업 완료 아이콘으로 컨텍스트 가지가 있습니다.  
  
 ![Visual Studio의 독립 실행형 알림](../../extensibility/ux-guidelines/media/0404-16_standalonenotificationicons.png "0404-16_StandaloneNotificationIcons")  
  
 **독립 실행형 알림 아이콘**  
  
 ![작업 완료 아이콘](../../extensibility/ux-guidelines/media/0404-17_taskcomplete.png "0404-17_TaskComplete")  
  
 **작업 완료 아이콘**  
  
 프로젝트 아이콘은 일반적으로 여러 크기를 포함 하는.ico 파일. 대부분 16 x 16 아이콘에 같은 요소가 들어 있습니다. 32 x 32 버전에 해당 하는 경우 해당 프로젝트 형식을 비롯 한 자세한 내용은.  
  
 ![Visual Studio의 프로젝트 아이콘](../../extensibility/ux-guidelines/media/0404-18_iconprojectthreesizes.png "0404-18_IconProjectThreeSizes")  
  
 **16 x 16 및 32 x 32 VB Windows 컨트롤 라이브러리 프로젝트 아이콘**  
  
 픽셀 프레임 내의 아이콘을 가운데로 맞춥니다. 가능 하지 않은 경우 프레임의 오른쪽 또는 맨 위에 있는 아이콘을 정렬 합니다.  
  
 ![픽셀 프레임 내의 가운데에 맞춰진 아이콘](../../extensibility/ux-guidelines/media/0404-19_iconcentered.png "0404-19_IconCentered")  
  
 **픽셀 프레임 내의 가운데에 맞춰진 아이콘**  
  
 ![픽셀 프레임의 오른쪽 위에 맞춰진 아이콘](../../extensibility/ux-guidelines/media/0404-20_icontopright.png "0404-20_IconTopRight")  
  
 **아이콘 위에 정렬 프레임의 오른쪽**  
  
 ![픽셀 프레임의 위쪽 가운데에 맞춰진 아이콘](../../extensibility/ux-guidelines/media/0404-21_icontopalign.png "0404-21_IconTopAlign")  
  
 **가운데에 맞춰지고 프레임의 위쪽에 정렬 아이콘**  
  
 이상적인 맞춤과 균형을 얻으려면 동작 문자 모양으로 아이콘의 기본 요소를 방해 하지 마십시오. 위쪽에 있는 문자 모양의 기본 요소의 왼쪽 위치입니다. 추가 요소를 추가할 때 정렬 하 고 아이콘의 균형 것이 좋습니다.  
  
|||  
|-|-|  
|**올바르게 정렬 및 분산**|**잘못 된 맞춤 및 분산**|  
|![올바른 아이콘 균형 및 맞춤](../../extensibility/ux-guidelines/media/0404-22_alignbalancecorrect.png "0404-22_AlignBalanceCorrect")|![잘못된 아이콘 균형 및 맞춤](../../extensibility/ux-guidelines/media/0404-23_alignbalanceincorrect.png "0404-23_AlignBalanceIncorrect")|  
  
 공유 하는 요소 집합에 사용 되는 아이콘에 대 한 크기 패리티를 확인 합니다. 잘못 된 쌍의 원과 화살표 크기를 초과한 기록한 일치 하지 마십시오.  
  
|||  
|-|-|  
|**정확한 크기 패리티**|**잘못 된 크기 패리티**|  
|![올바른 아이콘 크기 및 패리티](../../extensibility/ux-guidelines/media/0404-24_sizeparitycorrect.png "0404-24_SizeParityCorrect")|![잘못된 아이콘 크기 및 패리티](../../extensibility/ux-guidelines/media/0404-25_sizeparityincorrect.png "0404-25_SizeParityIncorrect")|  
  
 일관 된 선 및 시각적 가중치를 사용 합니다. 나란히 비교를 사용 하 여 작성 하는 아이콘 다른 아이콘을 비교 하는 방법을 평가 합니다. 전체 16 x 16 프레임을 사용 하 여 15 x 또는 더 작은 15를 사용 하지 마십시오. 음수와 양수-(진한 광원) 비율을 50/50 이어야 합니다.  
  
|||  
|-|-|  
|**올바른 음수-긍정 비율**|**잘못 된 음수-긍정 비율**|  
|![아이콘 및 # 40에 대 한 시각적 중량; 1 &#41; 수정](../../extensibility/ux-guidelines/media/0404-26_visualweightcorrect1.png "0404-26_VisualWeightCorrect1")<br /><br /> ![아이콘 및 # 40에 대 한 시각적 중량; 2 &#41; 수정](../../extensibility/ux-guidelines/media/0404-27_visualweightcorrect2.png "0404-27_VisualWeightCorrect2")<br /><br /> ![아이콘 및 # 40에 대 한 시각적 중량; 3 &#41; 수정](../../extensibility/ux-guidelines/media/0404-28_visualweightcorrect3.png "0404-28_VisualWeightCorrect3")|![아이콘에 대한 잘못된 시각적 중량감](../../extensibility/ux-guidelines/media/0404-29_visualweightincorrect.png "0404-29_VisualWeightIncorrect")|  
  
 요소 무결성을 유지 하면서 요소를 바인딩할 간단 하 고 이와 비슷한 모양과 보색 각도 사용 합니다. 가능한 경우 90 ° 또는 45도 각도 사용 합니다.  
  
 ![올바른 아이콘 각도](../../extensibility/ux-guidelines/media/0404-30_iconanglescorrect.png "0404-30_IconAnglesCorrect")  
  
#### <a name="perspective"></a>원근감  
 명확 하 고 이해할 수 있는 아이콘을 유지 합니다. 필요한 경우에 광원 및 큐브를 사용 합니다. 큐브 뷰를 사용 하 여 아이콘 요소에는 피해 야 하지만 일부 요소 없이 인식할 수 있는있지 않습니다. 이러한 경우 스타일이 적용 된 관점 요소의 명확성을 통신합니다.  
  
 ![3 &#45; 점 원근감](../../extensibility/ux-guidelines/media/0404-31_3pointperspective.png "0404-31_3PointPerspective")  
  
 **3 점 원근감**  
  
 ![1 &#45; 점 원근감](../../extensibility/ux-guidelines/media/0404-32_1pointperspective.png "0404-32_1PointPerspective")  
  
 **1 점 원근감**  
  
 대부분의 요소 해야 하거나 오른쪽으로 각 진 합니다.  
  
 ![오른쪽으로 각진 아이콘](../../extensibility/ux-guidelines/media/0404-33_angledright.png "0404-33_AngledRight")  
  
 개체에 필요한 명확성을 추가 하는 경우에 광원을 사용 합니다.  
  
|||  
|-|-|  
|**올바른 광원**|**잘못 된 광원**|  
|![아이콘에 대한 올바른 광원](../../extensibility/ux-guidelines/media/0404-34_lightsourcescorrect.png "0404-34_LightSourcesCorrect")|![아이콘에 대한 잘못된 광원](../../extensibility/ux-guidelines/media/0404-35_lightsourcesincorrect.png "0404-35_LightSourcesIncorrect")|  
  
 가독성 향상 하거나 메타포를 보다 잘 설명 하는 데만 윤곽선을 사용 합니다. 음수 양수 (진한 광원) 균형 50/50 이어야 합니다.  
  
|||  
|-|-|  
|**윤곽선의 올바른 사용**|**윤곽선의 잘못 된 사용**|  
|![올바른 윤곽선](../../extensibility/ux-guidelines/media/0404-36_outlinescorrect.png "0404-36_OutlinesCorrect")|![잘못된 윤곽선](../../extensibility/ux-guidelines/media/0404-37_outlinesincorrect.png "0404-37_OutlinesIncorrect")|  
  
#### <a name="icon-types"></a>아이콘 형식  
 **셸 및 명령 모음** 아이콘의 경우 다음 요소 중 세 개 이하의 구성: 하나의 자료, 하나의 한정자, 한 가지 동작 또는 상태입니다.  
  
 ![셸 및 명령 모음 아이콘](../../extensibility/ux-guidelines/media/0404-38_shellicons.png "0404-38_ShellIcons")  
  
 **셸 및 명령 모음 아이콘의 예**  
  
 **도구 창 명령 모음** 아이콘의 경우 다음 요소 중 세 개 이하의 구성: 하나의 자료, 하나의 한정자, 한 가지 동작 또는 상태입니다.  
  
 ![도구 창 명령 모음 아이콘](../../extensibility/ux-guidelines/media/0404-39_toolwindowcommandbaricons.png "0404-39_ToolWindowCommandBarIcons")  
  
 **도구 창 명령 모음 아이콘의 예**  
  
 **트리 뷰 명확성** 아이콘의 경우 다음 요소 중 세 개 이하의 구성: 하나의 자료, 하나의 한정자, 한 가지 동작 또는 상태입니다.  
  
 ![트리 뷰 중의성 해결기 아이콘](../../extensibility/ux-guidelines/media/0404-40_treeviewicons.png "0404-40_TreeViewIcons")  
  
 **예제 트리 명확성 아이콘 표시**  
  
 **상태 기반 값 분류** 는 다음과 같은 상태에 있는 아이콘: 활성, 비활성화, 활성 및 비활성 사용할 수 없습니다.  
  
 ![&#45; 기반된 분류 값 아이콘](../../extensibility/ux-guidelines/media/0404-41_statebasedtaxonomy.png "0404-41_StateBasedTaxonomy")  
  
 **상태 기반 값 분류 아이콘의 예**  
  
 **IntelliSense** 아이콘의 경우 다음 요소 중 세 개 이하의 구성: 하나의 자료, 하나의 한정자 및 하나의 상태입니다.  
  
 ![IntelliSense 아이콘](../../extensibility/ux-guidelines/media/0404-42_intellisenseicons.png "0404-42_IntelliSenseIcons")  
  
 **IntelliSense 아이콘의 예**  
  
 **작은 (16 x 16) 프로젝트** 아이콘 세 개 이상의 요소가 있어야 합니다.: 한 자료 및 하나의 한정자입니다.  
  
 ![16x16 프로젝트 아이콘 &#40; 1 &#41;](../../extensibility/ux-guidelines/media/0404-43_16x16project1.png "0404-43_16x16Project1") ![16x16 프로젝트 아이콘 &#40; 2 &#41;](../../extensibility/ux-guidelines/media/0404-44_16x16project2.png "0404-44_16x16Project2") ![16x16 프로젝트 아이콘 &#40; 3 &#41;](../../extensibility/ux-guidelines/media/0404-45_16x16project3.png "0404-45_16x16Project3")  
  
 **작은 (16 x 16) 프로젝트 아이콘의 예**  
  
 **큰 (32 x 32) 프로젝트** 아이콘 4 개까지 다음과 같은 요소로 구성 됩니다: 하나의 자료, 1 ~ 2 한정자 및 언어별로 오버레이 사용 합니다.  
  
 ![32x32 프로젝트 아이콘](../../extensibility/ux-guidelines/media/0404-46_32x32project.png "0404-46_32x32Project")  
  
 **큰 (32 x 32) 프로젝트 아이콘의 예**  
  
### <a name="production-details"></a>프로덕션 세부 정보  
 Windows Presentation Foundation (WPF)를 사용 하 여 모든 새 UI 요소를 만들어야 하며 WPF에 대 한 모든 새 아이콘은 32 비트 PNG 형식 이어야 합니다. 24 비트 PNG은 투명도 지원 하지 않는 하 되므로 아이콘에 대 한 권장 하지는 레거시 형식입니다.  
  
 96DPI 해상도 저장 합니다.  
  
#### <a name="file-types"></a>파일 형식  
  
-   **32 비트 PNG:** 아이콘에 대 한 기본 설정된 된 형식입니다. (픽셀) 단일 래스터 이미지를 저장할 수 있는 데이터 손실 없이 압축 파일 형식입니다. 32 비트 PNG 파일에는 알파 채널 투명도, 감마 보정 및 인터레이스 지원합니다.  
  
-   **32 비트 BMP:** 비 WPF 컨트롤에 대 한 합니다. 또는 XP 하이 컬러, 32 비트 BMP은 RGB/A 이미지 형식, 알파 채널 투명도와 트루 컬러 이미지. 알파 채널을 사용 하면 추가 (4)으로 비트맵 내에서 저장 하는 Adobe Photoshop에서 지정 된 투명도 계층이 색 채널입니다. 검은색 배경 아트 워크 프로덕션에 더 빠른 시각적 색 농도 단서를 제공 하는 모든 32 비트 BMP 파일에 추가 됩니다. 이 검은색 배경 UI에서 마스킹 하도록 영역을 나타냅니다.  
  
-   **32 비트 ICO:** 프로젝트 아이콘 및 항목을 추가 합니다. 모든 ICO 파일은 알파 채널 투명도 있는 32 비트 트루 컬러 (RGB/A). ICO 파일 여러 크기 및 색 농도 저장할 수 있으므로 Vista 아이콘 16 x 16, 32 x 32, 48 x 48, 및 256 x 256 이미지 크기를 포함 하는 ICO 형식으로 많습니다. Windows 탐색기에서 제대로 표시를 위해 ICO 파일 해야 수 저장로 다운 각 이미지 크기에 대 한 심도 있는 8 비트 및 24 비트 색입니다.  
  
-   **XAML:** 디자인 화면 및 Windows 표시기 (adorner). XAML 아이콘 크기 조정, 회전, 관리 및 투명도 지원 벡터 기반 이미지 파일이 있습니다. 일반적이 지 않은 Visual Studio에서 오늘 되지만 유연성으로 인해 더 많이 사용 된다고 합니다.  
  
-   **SVG**  
  
-   **24 비트 BMP:** Visual Studio 명령 모음에 대 한 합니다. True-색 RGB 이미지 형식 24 비트 BMP는 녹아웃 아웃 투명도 계층에 대 한 색상 키로 투명도 레이어가 자홍 (R = 255, G = 0, B = 255)를 사용 하 여 생성 하는 아이콘 규칙입니다. 24 비트 BMP, 모든 자홍 표면은 배경색을 사용 하 여 표시 됩니다.  
  
-   **24 비트 GIF:** Visual Studio 명령 모음에 대 한 합니다. 지 원하는 투명도 true 색 RGB 이미지 형식입니다. GIF 파일 마법사 아트 워크 및 GIF 애니메이션에 자주 사용 됩니다.  
  
### <a name="icon-construction"></a>아이콘 생성  
 Visual Studio에서 가장 작은 아이콘 크기는 16 x 16입니다. 가장 큰 공통으로 사용 하는 32 x 32. 아이콘을 디자인할 때 전체 16 x 16, 24 x 24 또는 32 x 32 프레임 가득 찰 필요가 염두에 둬야 합니다. 읽을 수 있고 일관성 아이콘 구성이 사용자 인식에 필수적입니다. 아이콘을 작성할 때 다음 사항을 준수 합니다.  
  
-   아이콘은 명확 하 고 일관성 이해할 수 있도록 해야 합니다.  
  
-   이 단일 아이콘으로 상태 알림 요소를 사용 하 고 하지 않는 아이콘 기본 요소에 겹쳐서 표시 것이 좋습니다. 특정 컨텍스트에서 UI 상태 요소는 기본 요소와 쌍을 이룰 수를 요구할 수 있습니다.  
  
-   프로젝트 아이콘은 일반적으로 여러 크기를 포함 하는.ico 파일. 16x16, 24x24 및 32x32 크기 아이콘을 업데이트 하는 중입니다. 대부분 16 x 16 및 24 x 24 아이콘에 같은 요소가 포함 됩니다. 32 x 32 아이콘 프로젝트 언어 유형에 해당 하는 경우를 포함 한 자세한 정보를 포함 합니다.  
  
-   32 x 32 아이콘에 대 한 기본 요소에는 2 픽셀 선 두께 일반적으로. 세부 정보 요소에 대 한 1 또는 2 픽셀 선 두께 사용할 수 있습니다. 현명한 판단을 사용 하 여 더 적합 한 것을 결정 합니다.  
  
-   16 x 16에 대 한 요소와 24 x 24 아이콘 사이는 최소한 1 픽셀 간격 수 있으며 32 x 32 아이콘에 대 한 2 픽셀 간격 요소 간의 및 한정자와 기본 요소를 사용 합니다.  
  
 ![16x16, 24x24 및 32x32 크기 아이콘을 위한 요소 간격](../../extensibility/ux-guidelines/media/0404-47_elementspacing.png "0404-47_ElementSpacing")  
  
 **16x16, 24x24 및 32x32 크기 아이콘을 위한 요소 간격 크기**  
  
#### <a name="color-and-accessibility"></a>색 및 내게 필요한 옵션  
 Visual Studio 호환성 지침 제품의 모든 아이콘 색 및 대비 위한 접근성 요구 사항을 전달 된다는 필요 합니다. 아이콘 반전을 통해 얻을 수 고를 디자인할 때 알아야 할 제품에서 프로그래밍 방식으로 반전 됩니다.  
  
 Visual Studio 아이콘의 색을 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [이미지에서 색을 사용 하 여](../../extensibility/ux-guidelines/images-and-icons-for-visual-studio.md#BKMK_UsingColorInImages)합니다.  
  
##  <a name="a-namebkmkusingcolorinimagesa-using-color-in-images"></a><a name="BKMK_UsingColorInImages"></a> 이미지에서 색을 사용 하 여  
  
### <a name="overview"></a>개요  
 Visual Studio에서 아이콘은 주로 단색 합니다. 색은 특정 정보를 전달 하는 데 예약 되어 및 데코레이션에 하지 않습니다. 색을 사용 합니다.  
  
-   동작을 나타내려면  
  
-   상태 알림을 사용자에 게 경고  
  
-   언어 정보를 지정 하려면  
  
-   IntelliSense에서 항목을 구분 하기 위해  
  
### <a name="accessibility"></a>접근성  
 Visual Studio 호환성 지침 아이콘을 모두 체크 색 및 대비에 대 한 내게 필요한 옵션 요구 사항에 제품 전달에 필요 합니다. 거친 하 고 이러한 요구 사항을 충족 하는 비주얼 언어 색상표의 색입니다.  
  
#### <a name="color-inversion-for-dark-themes"></a>어두운 테마에 대 한 색 반전  
 Visual Studio 어두운 테마의 올바른 대비 비율로 표시 아이콘을 만들려면 반전 프로그래밍 방식으로 적용 됩니다. 이 가이드에 있는 색 선택한 일부 올바르게 선택 반전 되도록 합니다. 이 팔레트 색의 사용이 제한 하거나 반전을 적용 될 때 예기치 않은 결과가 생깁니다.  
  
 ![색이 반전된 아이콘의 예](../../extensibility/ux-guidelines/media/0405-01_darkthemeinversion.png "0405-01_DarkThemeInversion")  
  
 **해당 색이 반전 된 아이콘의 예**  
  
### <a name="base-palette"></a>기본 색상표  
 모든 표준 아이콘 세 가지 기본 색을 포함합니다. 아이콘 없음 그라데이션 포함 또는 3D 도구 아이콘에 대 한 하나 또는 두 개의 예외 그림자 됩니다.  
  
|용도|이름|값 (밝은 테마)|견본|예제|  
|-----------|----------|---------------------------|------------|-------------|  
|배경/진한|VS BG|424242 / 66,66,66|![견본 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|![기본 색상표 예](../../extensibility/ux-guidelines/media/0405-02_basepaletteexample.png "0405-02_BasePaletteExample")|  
|전경/사용 요구가 적음|VS FG|F0EFF1 240,239,241 /|![견본 F0EFF1](../../extensibility/ux-guidelines/media/0405_f0eff1.png "0405_F0EFF1")||  
|윤곽선|VS 아웃|F6F6F6 246,246,246 /|![견본 F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")||  
  
 기본 색 외에 각 아이콘 추가 한 확장 된 색상표 색을 포함할 수 있습니다.  
  
### <a name="extended-palette"></a>확장 된 색상표  
  
#### <a name="action-modifiers"></a>작업 한정자  
 아래 표시 된 네 가지 색 작업 한정자에 필요한 동작의 유형을 나타냅니다.  
  
|용도|이름|값 (모든 테마)|견본|  
|-----------|----------|--------------------------|------------|  
|양수|VS 작업 녹색|388A34 56,138,52 /|![견본 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|음수|VS 작업 빨간색|A1260D 161,38,13 /|![견본 A1260D](../../extensibility/ux-guidelines/media/0405_a1260d.png "0405_A1260D")|  
|Neutral|VS 작업 파랑|00539 C 0,83,156 /|![견본 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|/ 새로 만들기|VS 작업 주황색|C27D1A 194,156,26 /|![견본 C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
  
##### <a name="examples"></a>예제  
 녹색 "추가"와 같은 양의 작업 한정자에는 "실행", "재생","및"유효성 검사 합니다."  
  
|||||  
|-|-|-|-|  
|![실행 아이콘](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405-03_ActionModifierRun") **실행**|![Execute query 아이콘](../../extensibility/ux-guidelines/media/0405-04_executequery.png "0405-04_ExecuteQuery") **쿼리 실행**|![모든 단계 재생 아이콘](../../extensibility/ux-guidelines/media/0405-05_playallsteps.png "0405-05_PlayAllSteps") **모든 단계 재생**|![추가 컨트롤 아이콘](../../extensibility/ux-guidelines/media/0405-06_addcontrol.png "0405-06_AddControl") **컨트롤 추가**|  
  
 빨간색에는 음수 작업 한정자와 같은 "삭제", "Stop", "취소" 및 "닫기"입니다.  
  
|||||  
|-|-|-|-|  
|![관계 삭제 아이콘](../../extensibility/ux-guidelines/media/0405-07_deleterelationship.png "0405-07_DeleteRelationship") **관계 삭제**|![열 삭제 아이콘](../../extensibility/ux-guidelines/media/0405-08_deletecolumn.png "0405-08_DeleteColumn") **열 삭제**|![쿼리 중지 아이콘](../../extensibility/ux-guidelines/media/0405-09_stopquery.png "0405-09_StopQuery") **쿼리 중지**|![오프 라인 연결 상태 아이콘](../../extensibility/ux-guidelines/media/0405-10_connectionoffline.png "0405-10_ConnectionOffline") **오프 라인 연결**|  
  
 파란색은 한정자 가장 일반적으로 "열기", "다음" "이전"와 같은 화살표로 표시 "가져오기" 및 "Export" 중립 작업에 적용 됩니다.  
  
|||||  
|-|-|-|-|  
|![필드 아이콘으로](../../extensibility/ux-guidelines/media/0405-11_gotofield.png "0405-11_GoToField") **필드로 이동**|![확인 &#45; 일괄 처리 된 아이콘에](../../extensibility/ux-guidelines/media/0405-12_batchedcheckin.png "0405-12_BatchedCheckIn") **일괄 처리에서 체크 인**|![주소 편집기 아이콘](../../extensibility/ux-guidelines/media/0405-13_addresseditor.png "0405-13_AddressEditor") **주소 편집기**|![연결 편집기 아이콘](../../extensibility/ux-guidelines/media/0405-14_associationeditor.png "0405-14_AssociationEditor") **연결 편집기**|  
  
 어두운 "gold"는 "New" 한정자에 주로 사용 됩니다.  
  
|||||  
|-|-|-|-|  
|![새 프로젝트 아이콘](../../extensibility/ux-guidelines/media/0405-15_newproject.png "0405-15_NewProject") **새 프로젝트**|![새 그래프 아이콘 만들기](../../extensibility/ux-guidelines/media/0405-16_createnewgraph.png "0405-16_CreateNewGraph") **새 그래프 만들기**|![새 단위 테스트 아이콘](../../extensibility/ux-guidelines/media/0405-17_newunittest.png "0405-17_NewUnitTest") **새 단위 테스트**|![새 목록 항목 아이콘](../../extensibility/ux-guidelines/media/0405-18_newlistitem.png "0405-18_NewListItem") **새 목록 항목**|  
  
#### <a name="special-cases"></a>특별 한 경우  
 특별 한 경우 색이 지정 된 작업 한정자를 사용할 수 있습니다 하지 독립적으로 독립 실행형 아이콘으로. 아이콘에 대 한 사용 되는 색 아이콘 연관 된 작업을 반영 합니다. 이 사용 하이 여 포함 한 아이콘의 작은 하위 집합으로 제한 됩니다.  
  
||||||  
|-|-|-|-|-|  
|![실행 아이콘](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405-03_ActionModifierRun") **실행**|![중지 아이콘](../../extensibility/ux-guidelines/media/0405-19_stop.png "0405-19_Stop") **중지**|![삭제 아이콘](../../extensibility/ux-guidelines/media/0405-20_delete.png "0405-20_Delete") **삭제**|![저장 아이콘](../../extensibility/ux-guidelines/media/0405-21_save.png "0405-21_Save") **저장**|![뒤로 탐색 아이콘](../../extensibility/ux-guidelines/media/0405-22_navigateback.png "0405-22_NavigateBack") **위로 이동**|  
  
### <a name="code-hierarchy-palette"></a>코드 계층 색상표  
  
#### <a name="folder"></a>폴더  
  
|용도|이름|값 (모든 테마)|견본|예제|  
|-----------|----------|--------------------------|------------|-------------|  
|폴더|폴더|DCB67A 220,182,122 /|![견본 DCB67A](../../extensibility/ux-guidelines/media/0405_dcb67a.png "0405_DCB67A")|![폴더 색 아이콘](../../extensibility/ux-guidelines/media/0405-23_foldercolor.png "0405-23_FolderColor")|  
  
#### <a name="visual-studio-languages"></a>Visual Studio 언어  
 각 공용 언어 또는 Visual Studio에서 사용할 수 있는 플랫폼에는 연결 된 색 있습니다. 이 색은 기본 아이콘 또는 복합 아이콘의 오른쪽 위 모서리에 표시 되는 언어 한정자에 사용 됩니다.  
  
|용도|이름|값 (모든 테마)|견본|  
|-----------|----------|--------------------------|------------|  
|ASP, HTML, WPF|ASP HTML WPF 파랑|0095D 7 0,149,215 /|![견본 0095D7](../../extensibility/ux-guidelines/media/0405_0096d7.png "0405_0096D7")|  
|C++|CPP 자주색|9B4F96 155,79,150 /|![견본 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|C#|CS 녹색 (VS 동작 녹색)|388A34 56,138,52 /|![견본 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|CSS|CSS 빨간색|BD1E2D 189,30,45 /|![견본 BD1E2D](../../extensibility/ux-guidelines/media/0405_bd1e2d.png "0405_BD1E2D")|  
|F#|FS 자주색|672878 / 103,40,120|![견본 672878](../../extensibility/ux-guidelines/media/0405_672878.png "0405_672878")|  
|JavaScript|JS 주황색|F16421 241,100,33 /|![견본 F16421](../../extensibility/ux-guidelines/media/0405_f16421.png "0405_F16421")|  
|VB|VB 파랑 (VS 동작 파랑)|00539 C 0,83,156 /|![견본 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|TypeScript|TS 주황색|E04C06 224,76,6 /|![견본 E04C06](../../extensibility/ux-guidelines/media/0405_e04c06.png "0405_E04C06")|  
|Python|PY 녹색|879636 / 135,150,54|![견본 879636](../../extensibility/ux-guidelines/media/0405_879636.png "0405_879636")|  
  
##### <a name="examples-of-icons-with-language-modifiers"></a>언어 한정자가 포함 된 아이콘의 예  
  
|||||||  
|-|-|-|-|-|-|  
|![Visual Basic 아이콘](../../extensibility/ux-guidelines/media/0405-25_vb.png "0405-25_VB") **VB**|![&#35; 아이콘](../../extensibility/ux-guidelines/media/0405-26_csharp.png "0405-26_CSharp") **C#**|![C# 43; & #43입니다. 아이콘](../../extensibility/ux-guidelines/media/0405-27_cplusplus.png "0405-27_CPlusPlus") **c + +**|![&#35; 아이콘](../../extensibility/ux-guidelines/media/0405-28_fsharp.png "0405-28_FSharp") **F #**|![JavaScript 아이콘](../../extensibility/ux-guidelines/media/0405-29_javascript.png "0405-29_JavaScript") **JavaScript**|![Python 아이콘](../../extensibility/ux-guidelines/media/0405-30_python.png "0405-30_Python") **Python**|  
|![HTML 아이콘](../../extensibility/ux-guidelines/media/0405-31_html.png "0405-31_HTML") **HTML**|![WPF 아이콘](../../extensibility/ux-guidelines/media/0405-32_wpf.png "0405-32_WPF") **WPF**|![ASP 아이콘](../../extensibility/ux-guidelines/media/0405-33_asp.png "0405-33_ASP") **ASP**|![CSS 아이콘](../../extensibility/ux-guidelines/media/0405-34_css.png "0405-34_CSS") **CSS**|![TypeScript 아이콘](../../extensibility/ux-guidelines/media/0405-35_typescript.png "0405-35_TypeScript") **TypeScript**||  
  
#### <a name="intellisense"></a>IntelliSense  
 IntelliSense 아이콘은 단독 색상표를 사용 합니다. 이 색은 IntelliSense 팝업 목록에서 여러 항목을 신속 하 게 구분할 수 있도록 하는 데 사용 됩니다.  
  
|용도|이름|값 (모든 테마)|견본|  
|-----------|----------|--------------------------|------------|  
|이벤트 클래스|VS 작업 주황색|C27D1A 194,125,26 /|![견본 C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
|확장 메서드를 대리자 메서드를 모듈|VS 작업 자주색|652 D 90 101,45,144 /|![견본 652D90](../../extensibility/ux-guidelines/media/0405_652d90.png "0405_652D90")|  
|필드, 열거형 항목, 매크로, 구조체, 공용 구조체 값 형식, 연산자, 인터페이스|VS 작업 파랑|00539 C 0,83,156 /|![견본 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|개체|VS 작업 녹색|388A34 56,138,52 /|![견본 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|상수, 예외, 열거형 항목, 지도, 지도 항목, 서식 파일, 네임 스페이스, 형식 정의|배경 (VS BG)|424242 / 66,66,66|![견본 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|  
  
##### <a name="examples-of-intellisense-icons"></a>IntelliSense 아이콘의 예  
  
||||||  
|-|-|-|-|-|  
|![IntelliSense 클래스 아이콘](../../extensibility/ux-guidelines/media/0405-36_intellisenseclass.png "0405-36_IntelliSenseClass") **클래스**|![IntelliSense private 이벤트 아이콘](../../extensibility/ux-guidelines/media/0405-37_intellisenseprivateevent.png "0405-37_IntelliSensePrivateEvent") **Private 이벤트**|![IntelliSense 대리자 아이콘](../../extensibility/ux-guidelines/media/0405-38_intellisensedelegate.png "0405-38_IntelliSenseDelegate") **위임**|![IntelliSense 메서드 친구 아이콘](../../extensibility/ux-guidelines/media/0405-39_intellisensemethodfriend.png "0405-39_IntelliSenseMethodFriend") **Friend 메서드**|![필드 아이콘](../../extensibility/ux-guidelines/media/0405-40_field.png "0405-40_Field") **필드**|  
|![IntelliSense 보호 열거형 항목 아이콘](../../extensibility/ux-guidelines/media/0405-41_intellisenseprotectedenumitem.png "0405-41_IntelliSenseProtectedEnumItem") **열거형 항목 보호**|![IntelliSense 개체 아이콘](../../extensibility/ux-guidelines/media/0405-42_intellisenseobject.png "0405-42_IntelliSenseObject") **개체**|![IntelliSense 템플릿 아이콘](../../extensibility/ux-guidelines/media/0405-43_intellisensetemplate.png "0405-43_IntelliSenseTemplate") **템플릿**|![IntelliSense 예외 바로 가기 아이콘](../../extensibility/ux-guidelines/media/0405-44_intellisenseexceptionshortcut.png "0405-44_IntelliSenseExceptionShortcut") **예외 바로 가기**||  
  
### <a name="notifications"></a>알림  
 Visual Studio에서 알림 상태를 나타내는 데 사용 됩니다. 알림 팔레트 검정색 또는 흰색 전경 채우기 옵션 뿐만 아니라 다음과 같은 네 가지 색을 사용 하 여 다음 상태 수준 사용 하 여 알림을 정의 합니다.  
  
|용도|이름|값 (모든 테마)|견본|  
|-----------|----------|--------------------------|------------|  
|상태: 중립|알림 파랑 (VS 파랑)|1BA1E2 27,161,226 /|![견본 1BA1E2](../../extensibility/ux-guidelines/media/0405_1ba1e2.png "0405_1BA1E2")|  
|상태: 양수|알림 녹색 (VS 녹색)|339933 / 51,153,51|![견본 339933](../../extensibility/ux-guidelines/media/0405_339933.png "0405_339933")|  
|상태: 음수|알림 빨강 (VS 빨간색)|E51400 229,20,0 /|![견본 E51400](../../extensibility/ux-guidelines/media/0405_e51400.png "0405_E51400")|  
|상태: 경고|알림 노란색 (VS 주황색)|FFCC00 255,204,0 /|![견본 FFCC00](../../extensibility/ux-guidelines/media/0405_ffcc00.png "0405_FFCC00")|  
|전경 채우기|알림 검정 (검정)|000000 / 0,0,0|![견본 &#35; 000000](../../extensibility/ux-guidelines/media/0405_000000.png "0405_000000")|  
|전경 채우기|알림 흰색 (흰색)|FFFFFF 255,255,255 /|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
  
#### <a name="examples-of-notification-icons"></a>알림 아이콘의 예  
  
|||||  
|-|-|-|-|  
|![경고 아이콘](../../extensibility/ux-guidelines/media/0405-45_alert.png "0405-45_Alert") **경고**|![경고 아이콘](../../extensibility/ux-guidelines/media/0405-48_warning.png "0405-48_Warning") **경고**|![완료 아이콘](../../extensibility/ux-guidelines/media/0405-46_complete.png "0405-46_Complete") **완료**|![중지 아이콘](../../extensibility/ux-guidelines/media/0405-47_stop.png "0405-47_Stop") **중지**|  
  
### <a name="visual-studio-online"></a>Visual Studio Online  
 일반적으로 Visual Studio Online으로 이루어져 브라우저에서 호스팅되는 기능이 있습니다. 다른 환경에서 색 다르지만 스타일 그대로 유지 됩니다.  
  
|그룹화|용도|이름|값 (모든 테마)|견본|  
|-----------|-----------|----------|--------------------------|------------|  
|TFS|배경|TFSO BG|656565/ 101, 101, 101|![견본 656565](../../extensibility/ux-guidelines/media/0405_656565.png "0405_656565")|  
|TFS|윤곽선|TFSO 아웃|FFFFFF / 255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Napa|배경|White|FFFFFF / 255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Monaco|배경|White|FFFFFF / 255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|배경|White|FFFFFF / 255, 255, 255|![견본 FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|보통|F12 Grey_Primary|555555 / 85, 85, 85|![견본 555555](../../extensibility/ux-guidelines/media/0405_555555.png "0405_555555")|  
|F12|가리키기|F12 Blue_Hover|2279BF 34,121,191 /|![견본 2279BF](../../extensibility/ux-guidelines/media/0405_2279bf.png "0405_2279BF")|  
|F12|사용 안 함|F12 LtGrey_Disabled|ABABAC 171,171,172 /|![견본 ABABAC](../../extensibility/ux-guidelines/media/0405_ababac.png "0405_ABABAC")|  
|F12|호버 배경|호버 bg|D9EBF7 217,235,247 /|![견본 D9EBF7](../../extensibility/ux-guidelines/media/0405_d9ebf7.png "0405_D9EBF7")|  
|F12|누름된 배경|Bg 누름된|B2D7F0 178,215,240 /|![견본 B2D7F0](../../extensibility/ux-guidelines/media/0405_b2d7f0.png "0405_B2D7F0")|  
|F12|윤곽선|VS 아웃|F6F6F6 246,246,246 /|![견본 F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")|  
|F12|정보|정보|00BCF2 0,188,242 /|![견본 00BCF2](../../extensibility/ux-guidelines/media/0405_00bcf2.png "0405_00BCF2")|  
|F12|경고|경고|F28300 242,131,0 /|![견본 F28300](../../extensibility/ux-guidelines/media/0405_f28300.png "0405_F28300")|  
|F12|오류 / 음수|Error_Negative|E81123 232,17,35 /|![견본 E81123](../../extensibility/ux-guidelines/media/0405_e81123.png "0405_E81123")|  
|F12|시작 / 양의|Start_Positive|009E49 0,158,73 /|![견본 009E49](../../extensibility/ux-guidelines/media/0405_009e49.png "0405_009E49")|  
|F12|광고 유형|광고 유형|9B4F96 155,79,150 /|![견본 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|F12|이벤트 표시|이벤트 표시|A51F00 165,31,0 /|![견본 A51F00](../../extensibility/ux-guidelines/media/0405_a51f00.png "0405_A51F00")|  
|F12|사용자 표시|사용자 표시|F16220 241,98,32 /|![견본 F16220](../../extensibility/ux-guidelines/media/0405_f16220.png "0405_F16220")|  
  
#### <a name="examples-of-visual-studio-online-icons"></a>Visual Studio Online 아이콘의 예  
  
|TFS 온라인||||  
|----------------|-|-|-|  
|![TFS 온라인 팀 아이콘](../../extensibility/ux-guidelines/media/0405-49_tfsonlineteam.png "0405-49_TFSOnlineTeam") **온라인 팀**|![TFS 정보 아이콘](../../extensibility/ux-guidelines/media/0405-50_tfsinformation.png "0405-50_TFSInformation") **정보**|![TFS 기록 아이콘](../../extensibility/ux-guidelines/media/0405-51_tfshistory.png "0405-51_TFSHistory") **기록**|![TFS 분기 아이콘](../../extensibility/ux-guidelines/media/0405-52_tfsbranch.png "0405-52_TFSBranch") **분기**|  
  
|Napa||||  
|----------|-|-|-|  
|![Napa 콘텐츠 아이콘](../../extensibility/ux-guidelines/media/0405-53_napacontent.png "0405-53_NapaContent") **콘텐츠**|![Napa office 메일 아이콘](../../extensibility/ux-guidelines/media/0405-54_napaofficemail.png "0405-54_NapaOfficeMail") **메일**|![Napa SharePoint 아이콘](../../extensibility/ux-guidelines/media/0405-55_napasharepoint.png "0405-55_NapaSharePoint") **SharePoint**|![Napa 작업 창 아이콘](../../extensibility/ux-guidelines/media/0405-56_napataskpane.png "0405-56_NapaTaskPane") **작업창**|  
  
|Monaco||||  
|------------|-|-|-|  
|![Monaco 파일 아이콘](../../extensibility/ux-guidelines/media/0405-57_monacofiles.png "0405-57_MonacoFiles") **파일**|![Monaco Git 아이콘](../../extensibility/ux-guidelines/media/0405-58_monacogit.png "0405-58_MonacoGit") **Git**|![Monaco 검색 아이콘](../../extensibility/ux-guidelines/media/0405-59_monacosearch.png "0405-59_MonacoSearch") **검색**|![Monaco 텍스트 아이콘](../../extensibility/ux-guidelines/media/0405-60_monacotext.png "0405-60_MonacoText") **텍스트**|  
  
|F12||||  
|---------|-|-|-|  
|![F12 깔끔한 코드 아이콘](../../extensibility/ux-guidelines/media/0405-61_f12prettycode.png "0405-61_F12PrettyCode") **상당히 코드**|![F12 경고 아이콘](../../extensibility/ux-guidelines/media/0405-62_f12warning.png "0405-62_F12Warning") **경고**|![F12 에뮬레이션 아이콘](../../extensibility/ux-guidelines/media/0405-63_f12emulate.png "0405-63_F12Emulate") **Emulate**|