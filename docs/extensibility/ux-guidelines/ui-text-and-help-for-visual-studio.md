---
title: UI 텍스트와 Visual Studio에 대 한 도움말 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: e8747d07-6c90-46cc-b425-55b589f7e9e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 697c794d17f3004b0f37e668ff67afb703490e18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ui-text-and-help-for-visual-studio"></a>UI 텍스트와 Visual Studio에 대 한 도움말
##  <a name="BKMK_UITextAndTerminology"></a> UI 텍스트 및 용어  
 알기 텍스트는 효과적인 UI에 중요 합니다. 소프트웨어 사용자가 읽는 경향이 레이블을 먼저, 즉 작업 완료에 가장 적합 합니다. 덜 빈도로 정적 텍스트를 읽어옵니다. 해당 작업 세션이 대략적인 순서로 UI의 읽기 뒤 전체 창의 빠른 검색을 시작 하는 사용자를 위한 계획:  
  
1.  센터에서 대화형 컨트롤  
  
2.  커밋 단추  
  
3.  어딘가에 대화형 컨트롤  
  
4.  기본 지침  
  
5.  설명 추가  
  
6.  창 제목  
  
7.  기타 정적 텍스트 본문에  
  
### <a name="usage-patterns-for-ui-text"></a>UI 텍스트에 대 한 사용 패턴  
  
#### <a name="title-bar-text"></a>제목 표시줄 텍스트  
 제목 표시줄 텍스트 UI를 생성 하는 명령을 일치 해야 합니다.  
  
#### <a name="instructional-text-helper-text"></a>사용 안내 텍스트 (도우미 텍스트)  
 일부 대화 상자 창이 나 페이지에서 수행할 작업을 설명 하기 위해 두드러진 기본 지침을 제공 하는 것이 좋습니다. 이 경우에 따라 라고 "도우미 text"입니다.  
  
##### <a name="writing-style-rules-for-helper-text"></a>도우미 텍스트에 대 한 규칙  
  
-   분명 설명 하지는 마십시오. 반드시 필요한 경우가 아니면 사용 안내 텍스트를 포함 하지 마십시오.  
  
-   사용 안내 텍스트는 항상 대화 상자 위쪽에 배치 하 고 수행 하는 작업을 참조 해야 합니다.  
  
-   사용자에 게 수행에 필요한 기능 설명 정확 하 게 합니다. 과도 한 통신 및 중복성을 방지 합니다.  
  
-   각 창을 검토 하 고 중복 된 단어와 문을 제거 합니다.  
  
-   짧은 설명 텍스트를 유지 합니다. 추가 정보가 필요한 특정 사용자 또는 시나리오 경우 자세한 개념 온라인 항목에 대 한 링크를 제공 합니다.  
  
-   모든 단어 가중치를 보유 하 고 필요한이 텍스트를 씁니다.  
  
-   에 대 한 기존 Microsoft 지침에 따라 [사용자 인터페이스 텍스트](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) 및 [스타일 및 톤](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx)합니다.  
  
#### <a name="supplemental-instructions"></a>추가 지침  
 추가 지침을 통해 사용자는 컨트롤을 이해 하거나 그룹화를 제어 하는 추가 정보를 제공 합니다. 여기에 입력된 컨트롤에 필요 하지만 어떤 형식을 이해 하는 데 필요한 힌트 텍스트가 포함 될 수 있습니다. 추가 지침을 제한적으로 사용 합니다. 사용자 선택 하는 항목의 결과 완전히 이해 하지 가능성이 큰 경우에 예약 합니다.  
  
 ![Visual Studio의 추가 텍스트](../../extensibility/ux-guidelines/media/0601-b_supplementaltext1.png "0601 b_SupplementalText1")  
  
 **Visual Studio의 추가 텍스트**  
  
 ![Visual Studio의 추가 텍스트](../../extensibility/ux-guidelines/media/0601-c_supplementaltext2.png "0601 c_SupplementalText2")  
  
 **Visual Studio의 추가 텍스트**  
  
#### <a name="infotips"></a>정보 팁  
 종종 사용 안내 텍스트 길이가 너무 길거나 전체 UI에서 위치를 지정할 수 있습니다 또는 숙련 된 사용자에 게 혼란 이라고 여겨질 새 사용자 에게만 유용할 수 있습니다. 이 경우 정보/사용 안내 텍스트 정보 팁에서 도구 설명으로 배치 되어야 합니다.  
  
 정보 팁 띄는 아직 방해가 되는 특정 정보 팁 아이콘을 사용 해야 관련 된 컨트롤은 가까이 배치 되어야 합니다.  
  
 ![Visual Studio의 정보 팁](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601 d_InfoTip")  
  
 **Visual Studio에서 정보 팁의 예**  
  
##### <a name="writing-style-rules-for-infotips"></a>정보 팁에 대 한 스타일 규칙 작성  
  
-   완전 한 문장이로 정보 팁을 기록 됩니다. 특정 동사 문장 대/소문자 및 문장 부호 필요 합니다.  
  
-   기본 명령 또는 정보를 보완 하기 위해 정보 팁을 사용 합니다. 방금 다른 단어를 주 아이디어를 다시 설명 한다면를 사용할 경우 정보 팁을 필요 하지 않습니다.  
  
-   정보 팁을 짧고 보기 좋게 유지 합니다. 작은 단어와 일반를 사용 하 여 일상적인 언어를 지원 하 고 사용자를 권장 합니다.  
  
-   에 대 한 기존 Microsoft 지침에 따라 [사용자 인터페이스 텍스트](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) 및 [스타일 및 톤](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx)합니다.  
  
#### <a name="control-labels"></a>컨트롤 레이블  
 컨트롤 레이블 짧은, 간결 하 고 해야 따라는 [컨트롤에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx)합니다.  
  
 컨트롤 레이블 형식 및 UI 내에서 배치 하는 방법에 대 한 자세한 내용은를 참조 [Visual Studio에 대 한 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md)합니다.  
  
#### <a name="help-links"></a>도움말 링크  
 도움말 링크가 사용 안내 텍스트 내에서 또는 UI의 본문에 배치할 수 있습니다. 도움말 링크를 제공 하거나 내부 대화 상자를 시작할 수 있습니다.  
  
##### <a name="visual-style-rules-for-help-links"></a>도움말 링크에 대 한 비주얼 스타일 규칙  
  
-   하이퍼링크에 대 한 올바른 환경 색을 사용 합니다. 제대로 스타일이 적용 된 하이퍼링크를 클릭 하면 빨간색 간단 하 게 플래시 되지 않습니다. 환경 색 사용 하지 않을 경우 표시 한 다음이 표시 합니다.  
  
-   밑줄은 가리키기 또는 링크 단락에 포함 된 경우에 사용 해야 합니다.  
  
-   시각적 개체 및 상호 작용 스타일 하이퍼링크에 대 한 자세한 내용을된 보려면 단추, 하이퍼링크를 참조 하십시오.  
  
##### <a name="writing-style-rules-for-help-links"></a>도움말 링크에 대 한 규칙  
  
-   대화 상자를 시작 하는 경우에 타원의 표준을 유지: 탐색, 타원 필요한 추가 UI 작업에 대 한 줄임표 없습니다.  
  
     ![Visual Studio의 도움말 링크](../../extensibility/ux-guidelines/media/0601-e_helplink.png "0601 e_HelpLink")  
  
     **도움말 링크에 줄임표 (...)는 작업을 추가 UI를 해야 하는 것을 나타냅니다.**  
  
-   사용자의 의도 아니므로 링크 "학습"로 시작 하지 않아야 합니다. 사용자는 일반 교육을 받지, 특정 질문에 대답 하려고 합니다.  
  
-   구 도움말은 질문 항목은 응답 있도록 연결 됩니다.  
  
     잘못 된:  
     "Windows Azure 모바일 서비스 가격에 대해 자세히 알아보려면"  
  
     맞는:  
     가격 책정 옵션에 대해 사용할 수 있는 "Windows Azure 모바일 서비스에 대 한"?  
  
-   사용 하지 마십시오 *클릭...*  링크 텍스트입니다.  
  
-   하지 링크만 단어 "여기"입니다. 이것은 하이퍼링크 단어만 음성은 일부 화면 읽기 프로그램에 대 한 문제가 있습니다.  
  
     잘못 된:  
     "Windows Azure 모바일 서비스에 대 한 자세한 내용은 **여기**"  
  
     맞는:  
     가격 책정 옵션에 대해 사용할 수 있는 "Windows Azure 모바일 서비스에 대 한"?  
  
-   도움말 링크에 대 한 올바른 필기 스타일에 대 한 자세한 내용은 참조는 [도움말에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742494\(v=vs.85\).aspx)합니다.  
  
#### <a name="hint-text"></a>힌트 텍스트  
 컨트롤 내에서 컨트롤 또는 아래 워터 마크로 힌트 텍스트가 표시 됩니다. 적절 한 VSColors 토큰을 사용 하 여 올바른 서식이 적용 될 `Environment.GrayText`합니다.  
  
 여러 폼에에서 나타날 수 있습니다.  
  
-   대신 컨트롤 레이블:  
  
     ![Visual Studio의 텍스트 힌트](../../extensibility/ux-guidelines/media/0601-f_hinttext1.png "0601 f_HintText1")  
  
-   동사와 지침을 제공:  
  
     ![Visual Studio의 텍스트 힌트](../../extensibility/ux-guidelines/media/0601-g_hinttext2.png "0601 g_HintText2")  
  
-   필요한 항목을 나타내는 텍스트:  
  
     ![Visual Studio의 텍스트 힌트](../../extensibility/ux-guidelines/media/0601-h_hinttext3.png "0601 h_HintText3")  
  
#### <a name="watermark-text"></a>워터 마크 텍스트  
 빈 디자인 화면에서 텍스트 작업 수행 수 있을 뿐만 아니라 해당 하는 경우 다른 관련된 창을 열에 대 한 링크를 제공 나타내야 합니다.  
  
 ![Visual Studio의 텍스트를 워터 마크](../../extensibility/ux-guidelines/media/0601-i_watermarktext.png "0601 i_WatermarkText")  
  
 **Visual Studio의 워터 마크 텍스트의 예**  
  
### <a name="common-terminology"></a>공용 용어  
  
|용어|설명|주석|  
|----------|-----------------|-------------|  
|로그인/로그 아웃|동사를 웹 속성에 대 한 인증을 나타내기 위해 웹과 동의어를 사용 합니다. 클라이언트 내에서 사용이 한 번 최상위 개념으로 다른 모든 연결을 사용할 수 없는 로밍 하는 라이선스 등의 더 높은 수준의 기능을 제공 하는 최상위 id를 나타내는 IDE 사용자 연결 및 서명 합니다.|IDE 사용자 로그인을 나타내는 / 로그 아웃 동사를 해야 하는 유일한 기능은 최상위 수준 IDE 사용자를 나타냅니다.|  
|연결/연결 끊기|기능 온라인 서비스에 단일 연결을 유지 하는 위치에서 사용 합니다.|사용할 수 있는 한 번에 하나의 활성 Azure 연결, 서버 탐색기는 연결/연결 끊기의 예시입니다.|  
|추가/제거|비-삭제 합니다. 추가 하거나 목록에서 항목을 제거할 때 사용 합니다.|TFS 연결 관리자 서버 목록 대화 상자는 추가/제거의 예시입니다.|  
|삭제|삭제 합니다. 요소가 제거 되 고 영구적으로 삭제 되거나 디스크에서 삭제 하는 경우에 사용 합니다.|결과 디스크에서 파일을 삭제 하는 경우에 한 프롬프트가 필요 일반적으로 "delete" 합니다.|  
  
## <a name="error-messages"></a>오류 메시지  
  
### <a name="overview"></a>개요  
 오류가 발생 합니다. 사용자 수행할 수 있는 제한 사항을 설정 하는 것은 피할 수 있는 오류 메시지에 붙여 구분이 가능한 첫 번째 단계입니다. 그러나 오류가 발생 하는 경우 잘 작성 된 오류 메시지 문제를 완화 하기 위한을 이동할 수 있습니다. 오류 메시지는 풀링할 때 가장 중요 한 유형의 때문에 동기 해결 해야 하는 문제가 있는 사용자가 볼 알림 중 하나입니다. 잘못 작성 된 오류 메시지는 사용자가 자신의 오류의 원인을 결정 하 고 모든 가능한 해결 방법에 둡니다.  
  
 사용자에 게 사용 되어 주의 또는 사용자에 게 값을 추가 하는 데 필요한만 메시지를 작성 발생 하므로 오류 메시지, 혼란 스 러 중지 될 수 있습니다. 메시지는 알림 단순히, 대체 표시를 사용 합니다.  
  
### <a name="rules-for-creating-an-error-message"></a>오류 메시지 작성에 대 한 규칙  
  
-   오류 메시지를 생성할 때는 대상 그룹에 대 한 적절 한 오류 수준을 선택 합니다. 해당 하는 경우 사용자를 만들 수 있는 동작을 제공 하는 간단한 요약에 대 한 목표입니다. 사용자가 알 필요가 있는 모든 상태 하지 않습니다.  
  
-   건설적인 지원을 제공 합니다. 읽기 및 명령이 포함 된 오류 메시지가 작업을 수행 하는 것이 쉽습니다.  
  
-   두 개의 음수 기호가 사용 하지 마십시오.  
  
-   자동화 된 수행 하 고 작성 하는 모든 오류 메시지에서 수동 문법 및 철자를 확인 합니다.  
  
-   복잡 한 오류 메시지에 대 한 순차적 통신을 하지 마십시오. 오류 메시지에 대 한 F1 후크를 사용 하지 마십시오. 메시지 자체에 충분 해야 합니다.  
  
-   올바른 아이콘을 사용 합니다.  
  
-   질문을 더 쉽게 이해 하 고 사용 예: "Delete" 및 "취소" 옵션이 지우기 단추  
  
-   경고에 대 한 됩니다 계속의 결과 명확 하 게 합니다. 단추는 결과 나타냅니다.  
  
-   오류에 대 한 사용자가 문제를 해결 하려면 수행할 수 있는 작업에 대해 설명 합니다. 단추 작업 하거나 "닫기"를 표시 해야 오류 메시지에 대 한 "확인" 단추를 사용 하지 마십시오.  
  
-   몇 가지 질문이 오류 메시지를 생성할 때:  
  
    -   사용자만이 오류와 함께 문제를 해결 하는 방법에 대해 알 수 있습니까?  
  
    -   사용자는이 오류와 같은 어휘를 사용 합니까?  
  
    -   이 오류 ambigious 되거나 여러 상황에서 공유? 이 경우 어떻게 수행 하면 사용자를 가이드 필요한 솔루션?  
  
#### <a name="build-errors"></a>빌드 오류  
 Visual Studio 소프트웨어 개발 도구, 많은 구성 요소는 컴파일, 변환 또는 개발자의 작업이 이진 형식으로 변환 하는 단계를 인코딩. 이러한 변환은 컴파일러 잘못 작성 된 파일을 처리할 수 없을 때 또는 컴파일러 옵션이 올바르게 설정 되지 않은 경우 오류가 발생할 수 있습니다.  
  
 Visual Studio 사용자에 게 소요 수많은 빌드 오류를 해결 하는 개발 시간을 단축할 수 있습니다. 이 확인 시간 오류는 종속 요소나 때 오류 메시지가 잘못 작성 된, 오류의 원인을 발견할 수 어렵게 만들 수는 증가 합니다.  
  
 가장 좋은 빌드 오류는 자동 완성 기능을 제공 하지 않는 발생 하는 첫 번째 위치를 의미 하기 때문에 Visual Studio 및 IntelliSense를 나타내는 물결선 합니다. 스키마 유효성 검사기 및 유사한 도구를 같은 종류의 피드백을 제공합니다. 이러한 메커니즘에는 사전 예방적으로 사용자가 빌드 오류 가능성을 절감 하는 올바른 형식의 코드를 생성할 안내 합니다.  
  
 Visual Studio에서는 사용자가 읽을 고 못하면 문서 창에서에 발생 한 오류를 탐색할 수 도구 창을 제공 합니다. 바로 가기 키에는 신속 하 게 많은 양의 코드를 탐색 하 고 문제의 위치 바로 이동할 수 있는 사용자 제공 됩니다. Visual Studio에는 또한 각 빌드 오류를를 사용자 오류에 대 한 더 자세한 정보를 제공 하는 도움말 항목에 직접 이동할 수 있도록 특정 도움말 키워드/컨텍스트 ID를 연결할 수 있습니다.  
  
 쓰기 명확 하 고 간결한 빌드 오류:  
  
-   **일반 언어를 사용 하 여** 거의 또는 전혀 컴파일러 특수 용어와 문제를 설명 하 합니다. 빌드 오류 텍스트가 과도 하 게 기술 되지 않아야 합니다.  
  
-   **가능한 원인에 간략하게 설명 합니다.** 예를 들어 "속성과 값 사이 콜론는 ' (속성): (값)' 선언 합니다."  
  
-   잠재적 수정 사항에 대 한 세부 정보를 제공 합니다. 공간이 충분 하지 않은 추가 세부 정보에서 해당 하는 도움말 항목에 해질 수 있습니다.  
  
### <a name="components-of-a-well-written-error-message"></a>잘 작성 된 오류 메시지의 구성 요소  
  
#### <a name="use-the-shell-dialog-service-for-error-messages"></a>오류 메시지에 대 한 대화 셸 서비스를 사용 합니다.  
 셸 대화 서비스를 사용 하 여 개별 요소에 주요 변경 내용 없이 글꼴 메시지의 모양을 특히 제어할 수 있습니다. 사용 하 여는 **IErrorInfo** 메커니즘 하 고 보고를 사용 하 여 **IVsUIShell::SetErrorInfo/ReportErrorInfo**합니다.  
  
#### <a name="choose-an-effective-and-appropriate-notification-presentation"></a>유효 하 고 적절 한 알림 표시를 선택 합니다.  
 (동기 알림) 데이터의 손실을 방지 하기 위해 즉각적인 동작이 필요한 경우에 중요 한 경고와 함께 모달 대화 상자를 사용 합니다. 위험 아이콘은 닫는 읽기 하지 않고 메시지에서 발생할 수 있습니다 부정적인 결과가 발생 하는 경우에 예약 되어 있습니다. 경보 수준 응답을 필요로 하는 중요 한 상황입니다. 중요 아이콘 남용 되지 않도록 desensitizes의 중요성에는 사용자입니다. 오류 메시지는 사실상에서 정보, 모달 대화 상자 (비동기 알림)에 대 한 대안을 것이 좋습니다.  
  
#### <a name="provide-a-clean-succinct-explanation-of-why-the-problem-occurred-rather-than-a-technical-explanation"></a>잘 정리 되 고 간결한 설명은 기술 설명 하는 대신 문제 발생 이유를 제공 합니다.  
 기술적인 세부 설명에 있는 사용자가 부담을 줄 하면 해당 오류 메시지를 무시할 수 있습니다. 좋은 메시징의 예:  
  
-   "요청된 된 파일을 열 수 없습니다."  
  
-   "인터넷에 연결할 수 없습니다."  
  
#### <a name="provide-information-about-how-to-fix-the-problem"></a>문제를 해결 하는 방법에 대 한 정보를 제공 합니다.  
 문제를 해결 하는 방법의 사용자 제안 사항을 제공 합니다. 제안이 없는 경우 사용자에 게를 수 있습니다. 기술 지원 또는 커뮤니티 지원과 같은 대체 온라인 원본에 대 한 직접 링크를 제공 합니다. 문제와 관련 된 특정 온라인 정보를 사용자가 가리키도록 시도 하십시오. 오류 ID에 대 한 스레드에 해당 특정 오류에 대 한 사용자를 연결 하는 것이 좋습니다. 좋은 메시징의 예:  
  
-   "인터넷에 연결 하 고이 작업을 다시 시도 했는지 확인 하십시오."  
  
-   "파일이 있으며 열 수 있는 권한이 있는지 확인 합니다."  
  
#### <a name="write-a-message-that-is-short-and-to-the-point"></a>이 설정은 더 간결 하 고 짧은 메시지를 작성 합니다.  
 오류 메시지가 알릴 수 설명 되 고 솔루션을 제공 되지만 너무 장황한 것 이면 여전히 무시 됩니다. 한 가지 해결 세부 정보 단추와 점진적 표시를 사용 하는 것입니다. 예를 들어 짧은 설명/솔루션을 지정 하 고 세부 정보 단추 아래의 자세한 세부 정보를 관리 합니다. 를 사용자 오류에 대 한 자세한 정보를 확인할 하도록 선택한 경우이 변경할 수 있습니다.  
  
 메시지의 언어는 다음과 같아야 합니다.  
  
-   **도메인에 적합 한 합니다.** 사용자는 이해 하는 언어를 사용 합니다. 고객 개발자 인 경우에 없는 경우가 많습니다 컨텍스트와 있는 용어입니다.  
  
-   **만 한정 됩니다.** 모호한 단어를 방지 하 고 관련된 개체의 특정 이름 및 위치를 지정 합니다. 예를 들어 오류 메시지가 "문자가 잘못 되었습니다."와 같은 유용 하지 않습니다. 문자? "파일을 찾을 수 없습니다." 어떤 파일이 있습니까?  
  
-   **Courteous 합니다.** 사용자를 비난 하거나 어리석 하지 마십시오. 유해 또는 비속어 언어 방지 (중지, 실행, 심각한, 잘못 된 종료). 대문자 텍스트를 shouting으로 종종 간주 되 고 같이 읽을 수 있는 하지 마십시오. 유머를 사용 하지 마십시오.  
  
-   **맞는.** 올바른 맞춤법 및 문법 (알파)에 사용 합니다. 오타는 비 전문적 및 좀 난처 한 일입니다.  
  
-   **컨텍스트에 적합 합니다.** 적절 한 단추 텍스트를 사용 합니다. "확인" 단추를 방지 하 고 대신 "Continue" 또는 "예/아니요." 사용  
  
### <a name="error-message-examples"></a>오류 메시지 예  
  
|양호|잘못 되었습니다.|  
|----------|---------|  
|"는 서비스에 번호로 전화를 걸 파일이 없습니다. 번호를 확인 하 고 다시 전화를 거 오거나 0 연산자에 대 한 전화 합니다. "|-"(449) 오류: 잘못 된 숫자"<br />-"이 처리 되지 않은 예외가 오류 나타냅니다 작업이 성공적으로 완료 되었음을."<br /><br /> ![Visual Studio에서 잘못 된 오류 메시지](../../extensibility/ux-guidelines/media/0602-a_errordialog.png "0602 a_ErrorDialog")|  
  
## <a name="accessing-help"></a>도움말 액세스  
  
### <a name="overview"></a>개요  
 MSDN의 설명서를 외에도 Visual Studio 사용자에 게 UI에 있는 동안 사용자를 지원 하기 위해 여러 액세스 지점을 합니다. 을 보장 하기 위해 이러한 액세스 포인트는 일관성 있게 제공 하는 기능 팀 환경에서 제공 도움말 시스템을 활용 해야 합니다. 이러한 액세스 점은 다음과 같습니다.  
  
-   **대화 상자에서 지침 및 추가 텍스트입니다.** 방향 또는 바닥 또는 마우스 포인터를 놓고 정보 팁 아이콘에서 사용할 수 있는 UI에서 설명을 제공 하는 정적 텍스트입니다.  
  
-   **F1 도움말** (편집기에만 해당). Visual Studio 편집기 내에서 사용자는 언제 든 지 F1 키를 누르면 하면 현재 선택 영역에 특정 도움말 항목을 신뢰할 수 있습니다. F1와 관련 된 항목 정보를 제공 하 고 적절 한 되는지 확인 합니다.  
  
-   **도움말 항목에 대 한 하이퍼링크입니다.** 대화 상자, 도구 창 또는 기술, 기능, 또는 작업을 수행 하는 방법에 대 한 정보에 대 한 자세한 사용자를 지원 하기 위해 항목을 시작 하는 디자인 화면 내에서 하이퍼링크입니다.  
  
-   **스마트 태그와 구성 대화 상자와 같은 도우미 UI 메커니즘** 이러한 메커니즘 사용자 UI 요소를 이해를 돕기 하거나 스마트 태그 또는 작성기 대화 상자 등의 작업을 용이 하 게 합니다.  
  
-   **UI 도움말 단추** (사용 되지 않음). 관련된 F1 도움말 항목에 대 한 액세스를 제공 하는 제목 표시줄에 표시기를 표시 합니다.  
  
### <a name="text"></a>텍스트  
  
#### <a name="instructional-and-supplemental-text-in-dialogs"></a>대화 상자에서 지침 및 추가 텍스트  
 복잡 한 작업을 지 원하는 대화 상자, 대화 상자 또는 복잡 한 컨트롤 근처 맨 위에 종종 ui에서 사용 안내 텍스트를 제공 해야 한다는 있을 수 있습니다. 참조 [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) 스타일 작성에 대 한 내용은 합니다.  
  
#### <a name="infotips"></a>정보 팁  
 자주 사용 안내 텍스트 UI에서 위치에 배치 하려면 너무 긴 또는 숙련 된 사용자에 게 혼란 이라고 여겨질 새 사용자 에게만 유용할 수 있습니다. 이 경우 정보/사용 안내 텍스트 정보 팁에서 도구 설명으로 배치 되어야 합니다.  
  
 정보 팁 띄는 아직 방해가 되는 특정 정보 팁 아이콘을 사용 해야 관련 된 컨트롤은 가까이 배치 되어야 합니다.  
  
 ![Visual Studio의 정보 팁](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601 d_InfoTip")  
  
 **Visual Studio에서 정보 팁의 예**  
  
### <a name="interactive-help-mechanisms"></a>대화형 도움말 메커니즘  
  
#### <a name="f1-help"></a>F1 도움말  
 F1 도움말은 필요한 편집기 또는 디자인 화면 내에 있지만 Visual Studio 환경에서 다른 위치에 없습니다.  
  
#### <a name="hyperlinks-to-help-topics"></a>도움말 항목에 대 한 하이퍼링크  
 작업을 수행 하 고, IDE 내에서 탐색 또는 브라우저에 도움말을 시작할 하이퍼링크를 사용할 수 있습니다. 참조 [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) 언어 및 07.10.01 대 한 자세한 내용은 단추 및 시각적 개체 및 레이아웃 지침에 대 한 하이퍼링크입니다.  
  
#### <a name="help--buttons-in-dialog-title-bars-deprecated"></a>(사용 되지 않음) 대화 상자 제목 표시줄 단추 [?] 도움말  
 대부분의 경우 대화 상자의 제목 표시줄의 [?] 도움말 단추가 사용 되지 않습니다. UI 항목 더 이상의 일부 예제의 doc 모델 이며 따라서 되지 않을 수에 연결 하 여 관련 항목입니다. 제목 표시줄 단추 된 F1 도움말을와 같은 작업, 기본적으로 대화 상자에서 더 이상 필요 하 고 없습니다. 경우에 따라이 계속 사용할 수 있습니다 사용할 수 있는, 개념적 또는 프로시저에 대 한 자세한 내용은 임을 표시기로 있지만 하이퍼링크는 일반적으로 더 최신 UI에 사용 됩니다.  
  
##### <a name="dialogs-created-through-the-environment"></a>환경을 통해 만든 대화 상자  
 많은 셸 대화 상자 모음을 만듭니다는 **VBDialogBoxParam** 함수입니다. 이 공유 함수 이동 지원 하기 위해 업데이트 된는 **도움말** 하는 대화 상자에서 단추는 **?** 이전 버전과 아키텍처를 유지 하면서 단추 호환 되며 확장 가능 합니다.  
  
 특히,는 **VBDialogBoxParam** 함수 ID가 인 단추에 대 한 대화 상자 템플릿을 확인 **IDHELP** (9) 또는 레이블이 **도움말** 또는 **&도움말**. 도움말 단추가 발견 되 면 열이 숨겨져 및 **WS_EX_CONTEXTHELP** 스타일은 대화 상자를 배치에 추가 **?** 대화 상자의 제목 표시줄에 단추입니다.  
  
 대화 상자를 만들면 대화 proc 스택에 푸시합니다 및 명명 된 전처리 대화 proc와 대화 상자를 호출 **DialogPreProc**합니다. 경우는 **?** 단추를 클릭 하면 보내는 **WM_SYSCOMMAND** 의 **SC_CONTEXTHELP** 대화 상자에 있습니다. **DialogPreProc** 이 명령은 캡처하고 하 여 변경 된 **WM_HELP** 원래 대화 프로시저에 전달 되는 메시지  
  
 대부분의 환경 만든 대화 상자는 대화 상자에는 도움말 단추가 있습니다. 대화 상자를 표시할 때 도움말 단추를 자동으로 숨겨진만 **?** 단추 작동합니다. 경우는 **?** 단추 제거 되거나 변경 Windows에서 현재까지,이 솔루션을 사용 하면 원래 도움말 단추를 신속 하 게 다시 이동할 수 있습니다.  
  
 이 솔루션에서는 버그를 일으킬 수 있는 4 개의 가정 합니다.  
  
-   대화 상자의 도움말 단추는 **IDHELP** (9).  
  
-   대화 상자는 도움말 단추 올바른 찾습니다.  
  
-   대화 상자에서 해당 winproc를 대체 하지 않습니다.  
  
-   대화 상자의 또 다른 대화 상자 내에서 포함 되지 않습니다.  
  
 대화 상자에 msenv 내에 상주 하 고 사용 하지 않는 경우 **VBDialogBoxParam**를 활용 하 여 조사 **VBDialogBoxParam** 자신만 처리기를 구현 하기 전에.  
  
##### <a name="dialogs-created-through-other-packages"></a>다른 패키지를 통해 만든 대화 상자  
 Msenv 외부 상주 하는 대화 상자에 대 한 사용자 고유의 솔루션을 구현할 수 있습니다. VSPackage의 공유 대화 상자 클래스, 제목 표시줄 단추 이동 하거나 각 대화 상자에 처리기 구현을 것이 좋습니다. 다음 코드는 시작할 수 있도록 하는 구현에 대 한 기본:  
  
```  
struct DLGPROCITEM  
{  
    FARPROC proc; // The info used to create the dialog.  
    DLGPROCITEM* procPrev;  
};  
  
DLGPROCITEM* g_dlgProcStack = NULL;  
  
// A dialog starter/wrapper function is used to push the new  
// dialog proc to the top of our dialog proc stack.  
  
int SomeDialogStarterFunction(hinst, id, proc, etc)  
{  
    if (g_dlgProcStack == NULL)  
    {  
        g_dlgProcStack = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = NULL;  
    }  
    else  
    {  
        DLGPROCITEM* procItem = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = g_dlgProcStack;  
        g_dlgProcStack = procItem;  
    }  
}  
  
// Pop this dialog proc off the dialog proc stack.  
  
DialogBoxIndirectParam...(...)  
{  
    DLGPROCITEM* procItem = g_dlgProcStack->procPrev;  
    delete g_dlgProcStack;  
    g_dlgProcStack = procItem;  
}  
  
// A wrapper dialog procedure will allow us to capture the  
// SC_CONTEXTHELP button on the title bar from Windows and  
// forward it as a simple WM_HELP message back to the dialog.  
  
INT_PTR CALLBACK DialogPreProc(HWND hwndDlg, UINT uMsg,  
    WPARAM wParam, LPARAM lParam)  
{  
    if (uMsg == WM_SYSCOMMAND && wParam == SC_CONTEXTHELP)  
    {  
        uMsg = WM_HELP;  
        wParam = 0;  
        lParam = 0;  
    }  
    return CallWindowProc((WNDPROC)g_dlgProcStack->proc,  
        hwndDlg, uMsg, wParam, lParam);  
}  
```  
  
##### <a name="help-buttons-in-managed-code"></a>관리 코드에서 도움말 단추  
 창 제목 표시줄 도움말 단추 기본 동작 재정의 관리 코드에서 쉽습니다. 다음은이 동작을 보여 주는 완전 한 데모 응용 프로그램입니다. 폼의 재정의 해야 하는 본질적으로 **WndProc** 메서드 및 F1 도움말 해제 한 다음 화재 요청는 **SC_CONTEXTHELP** 메시지를 가로채 합니다.  
  
```  
using System;  
using System.Windows.Forms;  
  
public class HelpForm : Form  
{  
    private const int SC_CONTEXTHELP = 0xF180;  
    private const int WM_SYSCOMMAND = 0x0112;  
  
    public HelpForm()  
    {  
        this.ClientSize = new System.Drawing.Size(300, 250);  
        this.HelpButton = true;  
        this.MaximizeBox = false;  
        this.MinimizeBox = false;  
        this.Name = "HelpForm";  
        this.Text = "Help Form";  
    }  
  
    protected override void WndProc(ref Message m)  
    {  
        if (m.Msg == WM_SYSCOMMAND && SC_CONTEXTHELP == (int)m.WParam)  
            ShowHelp();  
        else  
            base.WndProc(ref m);  
    }  
  
    private void ShowHelp()  
    {  
        MessageBox.Show("F1 Help goes here.");  
    }  
  
     [STAThread]  
    static void Main()  
    {  
        Application.EnableVisualStyles();  
        Application.EnableRTLMirroring();  
        Application.Run(new HelpForm());  
    }  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [글꼴 및 Visual Studio에 대 한 서식 지정](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)   
 [Visual Studio에 대 한 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md)   
 [Visual Studio의 알림 및 진행률](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)