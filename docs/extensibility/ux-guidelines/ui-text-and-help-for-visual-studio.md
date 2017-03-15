---
title: "UI 텍스트와 Visual Studio에 대 한 도움말 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8747d07-6c90-46cc-b425-55b589f7e9e4
caps.latest.revision: 2
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 2
---
# UI 텍스트와 Visual Studio에 대 한 도움말
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

##  <a name="BKMK_UITextAndTerminology"></a> UI 텍스트 및 용어  
 이해할 수 있는 텍스트는 효과적인 UI에 매우 중요 합니다. 소프트웨어 사용자가 읽을 경향이 레이블을 먼저, 즉 가장 관련성이 큰 현재 작업을 완료 합니다. 정적 텍스트 적은 빈도로 읽힙니다. 전체 창에이 대략적인 순서로 UI의 읽기 뒤의 빠른 검색으로 해당 작업 세션을 시작 하는 사용자를 위한 계획:  
  
1.  센터에서 대화형 컨트롤  
  
2.  커밋 단추  
  
3.  어딘가에 대화형 컨트롤  
  
4.  기본 지침  
  
5.  추가 설명  
  
6.  창 제목  
  
7.  기타 정적 텍스트 본문에  
  
### UI 텍스트에 대 한 사용 패턴  
  
#### 제목 표시줄 텍스트  
 제목 표시줄 텍스트에는 UI를 생성 하는 명령을 일치 해야 합니다.  
  
#### 사용 안내 텍스트 \(도우미 텍스트\)  
 일부 대화 상자에서 페이지 또는 창에서 수행할 작업을 설명 하는 유명한 주요 지침을 제공 하는 것이 좋습니다. 이 라고도 "도우미 text"입니다.  
  
##### 도우미 텍스트에 대 한 스타일 규칙 작성  
  
-   하지 명백한 사실에 대해 설명 합니다. 반드시 필요한 경우가 아니면 사용 안내 텍스트를 포함 하지 마십시오.  
  
-   사용 안내 텍스트 항상 대화 상자 위쪽에 놓이고 수행 하는 작업을 참조 해야 합니다.  
  
-   사용자에 게 수행 하는 데 필요한 설명 정확 하 게 합니다. 과도 한 통신 및 중복을 방지 합니다.  
  
-   각 창을 검토 하 고 중복 된 단어와 문을 제거 합니다.  
  
-   사용 안내 텍스트 짧게 유지 합니다. 자세한 정보는 필요한 특정 사용자 또는 시나리오, 자세한 개념 온라인 항목에 대 한 링크를 제공 합니다.  
  
-   모든 단어 가중치를 보유 하 고 필요한는 텍스트를 씁니다.  
  
-   에 대 한 기존 Microsoft 지침에 따라 [사용자 인터페이스 텍스트](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) 및 [스타일 및 톤](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx)합니다.  
  
#### 추가 지침  
 추가 지침은 사용자가 컨트롤을 이해 하거나 그룹화를 제어할 수 있도록 추가 정보를 제공 합니다. 힌트 텍스트 입력된 컨트롤을 예상 하는 어떤 형식을 이해 하는 데 필요한 포함 될 수 있습니다. 필요한 경우에 추가 지침을 사용 합니다. 사용자는 원하는 결과 완전히 이해 하지 가능성이 큰 경우 해당를 예약 합니다.  
  
 ![Supplemental text in Visual Studio](../../extensibility/ux-guidelines/media/0601-b_supplementaltext1.png "0601\-b\_SupplementalText1")  
  
 **Visual Studio의 추가 텍스트**  
  
 ![Supplemental text in Visual Studio](../../extensibility/ux-guidelines/media/0601-c_supplementaltext2.png "0601\-c\_SupplementalText2")  
  
 **Visual Studio의 추가 텍스트**  
  
#### 정보 팁  
 자주 사용 안내 텍스트 길이가 너무 길거나 전체 UI에서 위치를 지정할 수 있습니다 또는 숙련 된 사용자에 게 혼란을 여겨질 새 사용자 에게만 유용할 수 있습니다. 이 경우 정보\/사용 안내 텍스트 정보 팁 아래의 도구 설명으로 배치 되어야 합니다.  
  
 정보 팁 눈에 띄는 아직 작업을 방해 하지 않은 특정 정보 팁 아이콘을 사용 해야와 관련 된 컨트롤은 가까이 배치 되어야 합니다.  
  
 ![InfoTip in Visual Studio](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601\-d\_InfoTip")  
  
 **Visual Studio의 정보 팁의 예**  
  
##### 정보 팁에 대 한 쓰기 스타일 규칙  
  
-   정보 팁 완전 한 문장이 작성 합니다. 특정 동사 문장 대\/소문자 및 문장 부호 필요 합니다.  
  
-   정보 팁을 사용 하 여 기본 명령 또는 정보를 보완 하기 위해. 바로 사용할 경우 서로 다른 단어를 주 아이디어를 다시 설명 하자면, 정보 팁 필요는 없습니다.  
  
-   정보 팁 유지 짧고 간단 합니다. 작은 단어와 일반를 사용 하 여 일상적인 언어를 지원 하 고 사용자를 권장 합니다.  
  
-   에 대 한 기존 Microsoft 지침에 따라 [사용자 인터페이스 텍스트](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) 및 [스타일 및 톤](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx)합니다.  
  
#### 컨트롤 레이블  
 컨트롤 레이블 짧은, 간결 하 고 따릅니다는 [컨트롤에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx)합니다.  
  
 컨트롤 레이블 형식 및 UI 내에서 배치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio에 대 한 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md)합니다.  
  
#### 도움말 링크  
 도움말 링크가 사용 안내 텍스트 내에서 또는 UI의 본문에 배치할 수 있습니다. 내부 대화 상자를 시작 하거나 도움말 링크를 수 있습니다.  
  
##### 도움말 링크에 대 한 비주얼 스타일 규칙  
  
-   하이퍼링크에 대 한 올바른 환경 색을 사용 합니다. 제대로 스타일이 적용 된 하이퍼링크를 클릭 하면 빨간색 간단 하 게 플래시 되지 않습니다. 표시 되 면이 나타내는 값을 환경 색 사용 되지 않는 것이 있습니다.  
  
-   밑줄 호버 또는 링크 단락에 포함 된 경우에 사용 해야 합니다.  
  
-   하이퍼링크에 대 한 visual 및 상호 작용 스타일에 대 한 자세한 내용은 단추, 하이퍼링크를 참조 하십시오.  
  
##### 도움말 링크에 대 한 스타일 규칙 작성  
  
-   대화 상자를 시작 하는 경우 타원에 대 한 표준을 유지: 탐색, 타원 필요한 추가 UI 작업에 대 한 줄임표 없습니다.  
  
     ![Help link in Visual Studio](../../extensibility/ux-guidelines/media/0601-e_helplink.png "0601\-e\_HelpLink")  
  
     **줄임표 \(...\) 도움말 링크 작업 추가 UI에서는 나타냅니다.**  
  
-   사용자의 의도 하지 않은 대로 링크 "학습"로 시작 하지 않아야 합니다. 사용자가 특정 질문에 답하기, 일반 교육을 받지 하는 것입니다.  
  
-   구 도움말 항목은 응답 질문 요청할 수 있도록 연결 합니다.  
  
     잘못 된:  
     "자세한 내용은 Windows Azure 모바일 서비스 가격에 대 한"  
  
     수정:  
     "어떤 가격 옵션은 Windows Azure 모바일 서비스에 사용할 수 있는"?  
  
-   사용 안 함 *...를 클릭* 링크 텍스트를 합니다.  
  
-   하지 링크만 단어 "여기"입니다. 이 값은 하이퍼링크 단어만 음성은 일부 화면 판독기에 대 한 문제가 있습니다.  
  
     잘못 된:  
     "Windows Azure 모바일 서비스에 대 한 정보를 찾을 **여기**"  
  
     수정:  
     "어떤 가격 옵션은 Windows Azure 모바일 서비스에 사용할 수 있는"?  
  
-   도움말 링크에 대 한 정확한 필기 스타일에 대 한 자세한 내용은 참조는 [도움말에 대 한 Windows 바탕 화면 지침](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742494\(v=vs.85\).aspx)합니다.  
  
#### 힌트 텍스트  
 힌트 텍스트 컨트롤 또는 컨트롤 아래 워터 마크로 표시 됩니다. 적절 한 VSColors 토큰을 사용 하 여 올바른 서식이 적용 될 `Environment.GrayText`합니다.  
  
 여러 폼에에서 나타날 수 있습니다.  
  
-   대신 컨트롤 레이블:  
  
     ![Hint text in Visual Studio](../../extensibility/ux-guidelines/media/0601-f_hinttext1.png "0601\-f\_HintText1")  
  
-   동사와 지침을 제공 합니다.  
  
     ![Hint text in Visual Studio](../../extensibility/ux-guidelines/media/0601-g_hinttext2.png "0601\-g\_HintText2")  
  
-   필요한 항목을 나타내는 텍스트:  
  
     ![Hint text in Visual Studio](../../extensibility/ux-guidelines/media/0601-h_hinttext3.png "0601\-h\_HintText3")  
  
#### 워터 마크 텍스트  
 빈 디자인 화면에 무엇을 수행 하 고 해당 하는 경우 다른 관련된 창을 열에 대 한 링크를 제공 합니다. 텍스트 나타내야 합니다.  
  
 ![Watermark text in Visual Studio](../../extensibility/ux-guidelines/media/0601-i_watermarktext.png "0601\-i\_WatermarkText")  
  
 **Visual Studio의 워터 마크 텍스트의 예**  
  
### 일반적인 용어  
  
|용어|설명|주석|  
|--------|--------|--------|  
|로그인\/로그 아웃|동사를 같은 뜻으로 사용과 함께 사용 하는 웹 나타내는 웹 속성에 인증 합니다. 클라이언트 내에서 사용이 한 번 최상위 개념으로 다른 모든 연결을 사용할 수 없는 로밍 하는 라이선스 및와 같은 상위 수준의 기능을 제공 하는 최상위 id를 나타내는 IDE 사용자 연결 여부에 상관 없이 서명 합니다.|IDE 사용자는 최상위 IDE 사용자를 나타내는 것 처럼에 로그인을 나타내는 \/ 로그 아웃 동사를 해야 하는 유일한 기능입니다.|  
|연결\/연결 끊기|기능 온라인 서비스에 단일 연결을 유지 하는 곳에 사용 합니다.|서버 탐색기를 사용할 수 있는 한 번에 하나의 활성 Azure 연결, 연결\/연결 끊기의 예 이며|  
|추가\/제거|비\-삭제 합니다. 추가 하거나 목록에서 항목을 제거할 때 사용 됩니다.|TFS 연결 관리자 서버 목록 대화 상자는 추가\/제거의 예입니다.|  
|삭제|삭제 합니다. 요소가 제거 되 고 영구적으로 삭제 되거나 디스크에서 삭제 하는 경우에 사용 합니다.|결과 디스크에서 파일을 삭제 하는 경우 메시지가 필요 "삭제" 합니다.|  
  
## 오류 메시지  
  
### 개요  
 오류가 발생 합니다. 제한 하면 수행할 수 있는 설정은 구분이 가능한 첫 번째 단계로 피할 수 있는 오류 메시지를 방지 합니다. 그러나 오류가 발생 하는 경우 잘 작성 된 오류 메시지 문제를 완화 하기 위한을 이동할 수 있습니다. 오류 메시지는 확실히 사용자에 게 표시, 이며 때문에 동기 우리가 해결 해야 하는 문제를 나타내는 알림의 가장 중요 한 형식 중 하나입니다. 잘못 작성 된 오류 메시지는 사용자가 자신의 오류의 원인을 결정 하 고 모든 가능한 해결 방법에 둡니다.  
  
 사용자가 주의 하 게 사용 되어 발생 하는 사용자에 게 값을 추가 하는 데 필요한만 메시지를 작성 하므로 혼란 스러운 오류 메시지, 또는 중지 될 수 있습니다. 메시지는 알림 단순히, 경우에 대체 표시를 사용 합니다.  
  
### 오류 메시지 작성에 대 한 규칙  
  
-   오류 메시지를 생성할 때는 대상 그룹에 대 한 적절 한 오류 수준을 선택 합니다. 해당 하는 경우 사용자는 작업을 제공 하는 간단한 요약에 대 한 목표 걸릴 수 있습니다. 사용자가 알 필요가 있는 모든 상태 그렇지 않습니다.  
  
-   건설적인 지원을 제공 합니다. 읽기 및 명령을 포함 하는 오류 메시지에 대해 작동 하는 것이 쉽습니다.  
  
-   두 개의 음수 기호가 사용 하지 마십시오.  
  
-   자동화 된 수행 하 고 수동 문법과 맞춤법 작성 하는 모든 오류 메시지를 확인 합니다.  
  
-   복잡 한 오류 메시지에 대 한 순차 통신을 하지 마십시오. 오류 메시지에 대 한 F1 후크를 사용 하지 마십시오. 메시지 자체에 충분 해야 합니다.  
  
-   올바른 아이콘을 사용 합니다.  
  
-   질문을 더 쉽게 이해 하 고 "삭제" 및 "취소"와 같은 명확한 방법을 사용할 수 있는 단추를 사용 합니다.  
  
-   경고에 대 한 수 있는 진행의 결과 명확 하 게 합니다. 단추는 결과 나타냅니다.  
  
-   오류에 대 한 사용자가 문제를 해결 하려면 수행할 수 있는 작업을 설명 합니다. 단추를 작업 또는 "닫기" 라고 합니다. 오류 메시지에 대 한 "확인" 단추를 사용 하지 마십시오.  
  
-   몇 가지 질문이 오류 메시지를 생성할 때:  
  
    -   사용자만이 오류와 함께 문제를 해결 하는 방법에 대해 알 수 있습니까?  
  
    -   사용자는이 오류와 같은 어휘를 사용 합니까?  
  
    -   이 오류 ambigious 아니면 여러 상황에서 공유 되는지 여부 그렇다면 어떻게 수행 하면 안내 필요한 해결책을?  
  
#### 빌드 오류  
 Visual Studio 소프트웨어 개발 도구를 이므로 해당 구성 요소 중 상당수에 컴파일, 변환, 또는 개발자의 작업이 이진 형식으로 변환 하는 단계를 인코딩. 컴파일러가 잘못 작성 된 파일을 처리할 수 없는 경우 또는 컴파일러 옵션이 올바르게 설정 되지 않은 경우 이러한 변환에서 오류가 발생할 수 있습니다.  
  
 Visual Studio 사용자에 게 수많은 빌드 오류를 해결 하는 개발 시간을 투자할 수 있습니다. 종속성 이나 때 오류 메시지가 잘못 작성 된, 오류의 원인을 알아내는 데 어렵게 만들 수 있는 오류의 경우에이 해결 시간 증가 합니다.  
  
 최상의 빌드 오류 자동 완성 기능을 제공 하지에 발생 하는 이유는 애초에 Visual Studio와 IntelliSense 물결선 합니다. 스키마 유효성 검사기와 유사한 도구를 같은 종류의 피드백을 제공합니다. 이러한 메커니즘 사전 빌드 오류 가능성을 절감 하는 올바른 형식의 코드를 작성 하는 사용자를 안내 합니다.  
  
 Visual Studio 도구 창을 사용자 수 읽고 자신의 문서 창에서 발생 한 오류를 통해 탐색 하는 위치를 제공 합니다. 바로 가기 키에는 신속 하 게 많은 양의 코드를 탐색 하 고 문제의 위치 바로 이동할 수 있는 사용자 수 있도록 제공 됩니다. Visual Studio에는 또한 각 빌드 오류를를 사용자 오류에 대 한 자세한 내용은 제공 하는 도움말 항목에 직접 이동할 수 있도록 특정 도움말 키워드\/컨텍스트 ID에 연결 될 수 있습니다.  
  
 명확 하 고 간결 하 게 빌드 오류를 기록 합니다.  
  
-   **평이한 언어를 사용 하 여** 거의 없거나 전혀 없이 컴파일러 용어로 문제를 설명 하는 합니다. 빌드 오류 텍스트가 과도 하 게 기술 되지 않아야 합니다.  
  
-   **가능한 원인에 간략하게 설명 합니다.** 예를 들어 "속성과 값 사이 콜론은 ' \(속성\): \(값\)' 선언 합니다."  
  
-   잠재적 수정 사항에 대 한 세부 정보를 제공 합니다. 공간이 충분 하지 않은 추가 세부 정보에 해당 하는 도움말 항목 해질 수 있습니다.  
  
### 잘 작성 된 오류 메시지의 구성 요소  
  
#### 오류 메시지에 대 한 셸 대화 서비스를 사용 합니다.  
 셸 대화 서비스를 사용 하면 메시지의 모양을 제어할 수 있습니다 — 특히에서 글꼴 — 개별 요소에 크게 변경 하지 않고 있습니다. 사용 된 **IErrorInfo** 메커니즘 하 고 보고를 사용 하 여 **IVsUIShell::SetErrorInfo\/ReportErrorInfo**합니다.  
  
#### 효과적이 고 적절 한 알림 표시를 선택 합니다.  
 즉각적인 조치가 \(동기 알림\) 데이터의 손실을 방지 하기 위해 필요한 경우 모달 대화 상자를 사용 하 여 중요 한 경고와 함께 합니다. 위험 아이콘은 닫는 읽지도 않고 메시지에서 발생할 수 있습니다 부정적인 결과가 발생 하는 상황에 대 한 예약 되어 있습니다. 데이터 손실은 경보 수준 응답을 필요로 하는 중요 한 상황입니다. 중요 아이콘의과 용 desensitizes의 중요성에 대 한 사용자. 오류 메시지는 정보, 모달 대화 상자 \(비동기 알림\)에 대 한 대안을 것이 좋습니다.  
  
#### 에 대 한 잘 정리 되 고 간결한 정보 기술 설명 하는 대신 문제 발생 이유를 제공 합니다.  
 설명에서 기술 세부 정보를 통해 사용자를 느끼지 것입니다 있도록 가능성이 오류 메시지는 무시 합니다. 좋은 메시징의 예:  
  
-   "요청된 된 파일을 열 수 없습니다."  
  
-   "인터넷에 연결할 수 없습니다."  
  
#### 문제를 해결 하는 방법에 대 한 정보를 제공 합니다.  
 문제를 해결 하는 방법의 사용자를 제안 합니다. 솔직히 사용자와 경우 제안이 없습니다. 기술 지원 또는 커뮤니티 지원 등의 다른 온라인 원본에 대 한 직접 링크를 제공 합니다. 사용자가 특정 문제에 관련 된 온라인 정보를 가리키도록 해 보십시오. 오류 ID에 대 한 특정 오류에 대 한 토론 스레드에 사용자를 연결 하는 것이 좋습니다. 좋은 메시징의 예:  
  
-   "인터넷에 연결 되 고이 작업을 다시 시도 했는지 확인 하십시오."  
  
-   "파일이 있으며를 열 권한이 있는지 확인 합니다."  
  
#### 이 설정은 더 간결 하 고 짧은 메시지를 작성 합니다.  
 오류 메시지가 알릴 수 설명 되 고 솔루션을 제공 되지만 여전히 너무 장황 하다 면 무시 됩니다. 한 가지 해결 세부 정보 단추와 점진적 공개를 사용 하는 것입니다. 예를 들어, 간단한 설명\/솔루션을 지정 하 고 세부 정보 단추 아래에서 자세한 정보를 관리 합니다. 사용자가 오류에 대 한 자세한 정보를 읽을 수를 선택 하는 경우에 그렇게 할 수 있습니다.  
  
 메시지의 언어는 다음과 같아야 합니다.  
  
-   **도메인에 적합 한 합니다.** 사용자 이해 하 게 하는 언어를 사용 합니다. 고객에 게 개발자 인 경우에 없는 경우가 많습니다 컨텍스트 및 용어 했습니다.  
  
-   **만 해당 합니다.** 막연 한 단어를 방지 하 고 관련 된 개체의 특정 이름 및 위치를 지정 합니다. 예를 들어, 오류 메시지 "문자가 잘못 되었습니다."와 같은 유용 하지 않습니다. 문자? "파일을 찾을 수 없습니다." 어떤 파일이 있습니까?  
  
-   **친절 함.** 사용자를 탓 하거나 있도록 탓 하지 마십시오. 부적절 하거나 공격적인 언어 방지 \(중단, 실행, 심각한, 잘못 된 종료\). 주로 shouting로 표시 되며 같이 읽을 수 없는 대문자 텍스트를 하지 마십시오. 유머를 사용 하지 마십시오.  
  
-   **수정 합니다.** 올바른 맞춤법 및 문법 \(곱한 알파\)에 사용 합니다. 오타가 미숙한 되며 당혹 스러운 됩니다.  
  
-   **컨텍스트에 따라 적절 한 합니다.** 적절 한 단추 텍스트를 사용 합니다. "확인" 단추를 방지 하 고 "계속" 또는 "예\/아니요"를 대신 사용  
  
### 오류 메시지 예  
  
|양호|잘못 되었습니다.|  
|--------|---------------|  
|"는 번호로 전화를 걸는 서비스에서 더 이상. 번호를 확인 하 고 다시 전화 하거나 하십시오 연산자에 대 한 0 다이얼. "|-   "\(449\) 오류: 잘못 된 수"<br />-   "이 처리 되지 않은 예외 오류가 나타냅니다 작업이 성공적으로 완료 되었음을."<br /><br /> ![Bad error message in Visual Studio](../../extensibility/ux-guidelines/media/0602-a_errordialog.png "0602\-a\_ErrorDialog")|  
  
## 도움말 액세스  
  
### 개요  
 Msdn에서 설명서 외에 Visual Studio 사용자 UI에서 사용자를 지원 하기 위해 여러 액세스 지점에 있습니다. 이러한 액세스 지점은 지속적으로 사용할 수 있도록 기능 팀 환경에서 제공 하는 도움말 시스템을 활용 해야 합니다. 이러한 액세스 점은 다음과 같습니다.  
  
-   **대화 상자에서 텍스트 강의 및 보완 합니다.** 방향 또는 바닥 또는 마우스 포인터를 놓고 정보 팁 아이콘에서 사용할 수 있는 UI에서 설명을 제공 하는 정적 텍스트입니다.  
  
-   **F1 도움말** \(편집기에만 해당\). Visual Studio 편집기 내에서 사용자는 언제 든 지 F1 키를 누르면 열립니다. 현재 선택 영역에 특정 도움말 항목을 신뢰할 수 있습니다. 적절 한 고 유익한 F1와 연관 된 항목 인지 확인 합니다.  
  
-   **도움말 항목에 대 한 하이퍼링크입니다.** 대화 상자, 도구 창 또는 기술, 기능 또는 작업을 수행 하는 방법에 대 한 정보에 대 한 자세한 사용자를 지원 하기 위해 항목을 시작 하는 디자인 화면 내에서 하이퍼링크입니다.  
  
-   **스마트 태그 및 건물 대화 상자와 같은 도우미 UI 메커니즘** 이러한 메커니즘에는 사용자는 UI 요소를 이해를 돕기 또는 스마트 태그 또는 작성기 대화 상자 등의 작업을 용이 하 게 합니다.  
  
-   **UI 도움말 단추가** \(사용 되지 않음\). 관련 된 F1 도움말 항목에 대 한 액세스를 제공 하는 제목 표시줄에 표시기를 표시 합니다.  
  
### 텍스트  
  
#### 대화 상자에서 지침 및 추가 텍스트  
 복잡 한 작업을 지 원하는 대화 상자에서 복잡 한 컨트롤 근처 또는 대화 상자의 위쪽에서 종종 ui에서 사용 안내 텍스트를 제공 해야 하는 있을 수 있습니다. 참조 [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) 스타일 작성에 대 한 내용은 합니다.  
  
#### 정보 팁  
 자주 사용 안내 텍스트 UI에서 위치에 배치 하려면 너무 긴 또는 숙련 된 사용자에 게 혼란을 여겨질 새 사용자 에게만 유용할 수 있습니다. 이 경우 정보\/사용 안내 텍스트 정보 팁 아래의 도구 설명으로 배치 되어야 합니다.  
  
 정보 팁 눈에 띄는 아직 작업을 방해 하지 않은 특정 정보 팁 아이콘을 사용 해야와 관련 된 컨트롤은 가까이 배치 되어야 합니다.  
  
 ![InfoTip in Visual Studio](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601\-d\_InfoTip")  
  
 **Visual Studio의 정보 팁의 예**  
  
### 대화형 도움말 메커니즘  
  
#### F1 도움말  
 F1 도움말을 제공 하는 것은 필요한 편집기 또는 디자인 화면 내에서 있지만 Visual Studio 환경에서 다른 위치 하지 않습니다.  
  
#### 도움말 항목에 대 한 하이퍼링크  
 하이퍼링크 동작을 수행, IDE 내에서 탐색 또는 브라우저에서 도움말 시작 데 사용할 수 있습니다. 참조 [UI 텍스트 및 용어](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) 언어 및 07.10.01 대 한 자세한 내용은 단추 및 시각 및 레이아웃 지침에 대 한 하이퍼링크입니다.  
  
#### \[?\] 단추 \(사용 되지 않음\) 대화 상자 제목 표시줄에 도움말  
 대부분의 경우 대화 상자의 제목 표시줄에 있는 \[?\] 도움말 단추는 사용 되지 않습니다. UI 항목 더 이상 일부 문서 모델의 이며 따라서 없을 수 있지만 연결할 관련 항목입니다. 기본적으로, 제목 표시줄 단추 F1 도움말을 하는 동일한 결과 더 이상에 필요 하 고 대화 상자에서. 일부 경우에이 계속 사용할 수 있습니다를 사용할 수 있는 자세한 절차 또는 개념 정보는 표시기로 있지만 하이퍼링크 더 일반적으로 최신 UI에 사용 됩니다.  
  
##### 환경을 통해 만든 대화 상자  
 많은 셸 대화 상자를 통해 생성 된 **VBDialogBoxParam** 함수입니다. 이 공유 함수 이동 지원 하기 위해 업데이트 된는 **도움말** 하는 대화 상자에서 단추는 **?** 뒤로 하는 아키텍처를 유지 하면서 단추 호환 되 고 확장 가능 합니다.  
  
 특히,는 **VBDialogBoxParam** 함수 ID가 인 단추에 대 한 대화 상자 템플릿을 살펴보고 **IDHELP** \(9\) 레이블은 또는 **도움말** 또는 **& 도움말**합니다. 도움말 단추가 있으면 숨겨진 및 **WS\_EX\_CONTEXTHELP** 스타일은 대화 상자를 배치에 추가 **?** 대화 상자의 제목 표시줄에 단추입니다.  
  
 대화 상자를 만든 대화 proc 스택에 푸시합니다 및 명명 된는 전처리 대화 proc와 대화 상자를 호출 **DialogPreProc**합니다. 때는 **?** 전송 단추를 클릭 한 **WM\_SYSCOMMAND** 의 **SC\_CONTEXTHELP** 대화 상자에 있습니다.**DialogPreProc** 이 명령은 캡처하고 하 여 변경 된 **WM\_HELP** 원래 대화 프로시저에 전달 되는 메시지  
  
 대부분의 환경 생성 대화 상자는 대화 상자에는 도움말 단추가 있습니다. 대화 상자 표시 되 면 도움말 단추 이며 자동 숨김만 **?** 단추의 기능입니다. 하는 경우는 **?** 단추 적이 제거 하거나 Windows 변경이 솔루션을 사용 하면 신속 하 게 원래 도움말 단추를 다시 이동할 수 있습니다.  
  
 이 솔루션에서는 버그를 일으킬 수 있는 4 개의 가정 합니다.  
  
-   대화 상자의 도움말 단추는 **IDHELP** \(9\).  
  
-   대화 상자 도움말 단추는 숨겨져 정확히 표시 합니다.  
  
-   대화 상자에서 해당 winproc를 대체 하지 않아야 합니다.  
  
-   대화 상자는 다른 대화 상자 내에서 포함 되지 않습니다.  
  
 대화 상자에 msenv 내에 상주 하 고 사용 하지 않는 경우 **VBDialogBoxParam**, 를 활용 하 여 조사 **VBDialogBoxParam** 자신만 처리기를 구현 하기 전에 합니다.  
  
##### 다른 패키지를 통해 만든 대화 상자  
 Msenv 외부에 있는 대화 상자에 대 한 고유한 솔루션을 구현할 수 있습니다. VSPackage에서 공유 대화 상자 클래스의 경우 제목 표시줄에 단추를 이동 하거나 각 대화 상자에서 처리기를 구현할 것이 좋습니다. 다음 코드는 시작할 수 있도록 하는 구현의 기초:  
  
```  
struct DLGPROCITEM { FARPROC proc; // The info used to create the dialog. DLGPROCITEM* procPrev; }; DLGPROCITEM* g_dlgProcStack = NULL; // A dialog starter/wrapper function is used to push the new // dialog proc to the top of our dialog proc stack. int SomeDialogStarterFunction(hinst, id, proc, etc) { if (g_dlgProcStack == NULL) { g_dlgProcStack = new DLGPROCITEM; g_dlgProcStack->procPrev = NULL; } else { DLGPROCITEM* procItem = new DLGPROCITEM; g_dlgProcStack->procPrev = g_dlgProcStack; g_dlgProcStack = procItem; } } // Pop this dialog proc off the dialog proc stack. DialogBoxIndirectParam...(...) { DLGPROCITEM* procItem = g_dlgProcStack->procPrev; delete g_dlgProcStack; g_dlgProcStack = procItem; } // A wrapper dialog procedure will allow us to capture the // SC_CONTEXTHELP button on the title bar from Windows and // forward it as a simple WM_HELP message back to the dialog. INT_PTR CALLBACK DialogPreProc(HWND hwndDlg, UINT uMsg, WPARAM wParam, LPARAM lParam) { if (uMsg == WM_SYSCOMMAND && wParam == SC_CONTEXTHELP) { uMsg = WM_HELP; wParam = 0; lParam = 0; } return CallWindowProc((WNDPROC)g_dlgProcStack->proc, hwndDlg, uMsg, wParam, lParam); }  
```  
  
##### 관리 코드에서 도움말 단추  
 창 제목 표시줄 도움말 단추 기본 동작 재정의 하는 것은 관리 코드에서 쉽습니다. 다음은이 동작을 보여 주는 완전 한 데모 응용 프로그램입니다. 폼의 재정의 해야 하는 본질적으로 **WndProc** 메서드와 F1 도움말을 해제 한 다음 실행 요청는 **SC\_CONTEXTHELP** 메시지를 가로채는 합니다.  
  
```  
using System; using System.Windows.Forms; public class HelpForm : Form { private const int SC_CONTEXTHELP = 0xF180; private const int WM_SYSCOMMAND = 0x0112; public HelpForm() { this.ClientSize = new System.Drawing.Size(300, 250); this.HelpButton = true; this.MaximizeBox = false; this.MinimizeBox = false; this.Name = "HelpForm"; this.Text = "Help Form"; } protected override void WndProc(ref Message m) { if (m.Msg == WM_SYSCOMMAND && SC_CONTEXTHELP == (int)m.WParam) ShowHelp(); else base.WndProc(ref m); } private void ShowHelp() { MessageBox.Show("F1 Help goes here."); } [STAThread] static void Main() { Application.EnableVisualStyles(); Application.EnableRTLMirroring(); Application.Run(new HelpForm()); } }  
```  
  
## 참고 항목  
 [글꼴 및 Visual Studio에 대 한 서식 지정](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)   
 [Visual Studio에 대 한 레이아웃](../../extensibility/ux-guidelines/layout-for-visual-studio.md)   
 [알림 및 Visual Studio에 대 한 진행률](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)