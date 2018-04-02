---
title: Visual Studio 2017의 문제를 보고하는 방법 | Microsoft 문서
ms.custom: ''
ms.date: 03/11/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.technology: vs-acquisition
ms.workload:
- multiple
ms.openlocfilehash: 6fa988ce97968949036a74ff473cfe11dd3b669e
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-report-a-problem-with-visual-studio-2017"></a>Visual Studio 2017의 문제를 보고하는 방법

Visual Studio에 문제가 발생하는 경우와 관련하여 자세히 알려고 합니다. 진단하고 해결할 수 있도록 문제를 보고하는 방법은 다음과 같습니다.

## <a name="sign-in-to-visual-studio"></a>Visual Studio에 로그인

아직 로그인하지 않았으면 문제를 보고하기 전에 먼저 Visual Studio에 로그인합니다. 이런 방식으로 경험하고 있는 문제를 보고하고 투표하거나 주석을 달 수 있습니다. 사용자가 게시한 다른 문제에 대해 주문하거나 주석을 달 수도 있습니다.

1. Visual Studio에서 **도움말** > **피드백 보내기** > **문제 보고**를 선택합니다.
2. 로그인되지 않은 경우 다음 스크린샷과 같이 도구 오른쪽에 있는 **로그인**을 선택합니다.
3. 화면의 지침에 따라 로그인합니다.

 ![문제 보고를 위한 로그인](../ide/media/sign-in-new-ux.png "문제 보고를 위한 로그인")  

## 유사한 문제 검색 및 투표<a name="search_and_vote"></a>

1. 문제를 검색하고 다른 사용자가 이미 보고했는지 확인합니다.
2. 다른 사용자가 이미 보고한 경우 "투표"하여 알려 주시기 바랍니다.

  ![검색 및 유사한 문제에 투표](../ide/media/search-and-vote.png "검색 및 유사한 문제에 투표")

## 새 문제 보고<a name="report_new_problem"></a>

1. 원하는 항목을 찾지 못한 경우 화면 맨 아래에서 **새 문제 보고** 단추를 선택합니다.
2. 올바른 Visual Studio 팀에게 전달될 수 있도록 문제에 대한 설명이 포함된 제목을 입력합니다.
3. 추가 세부 정보와 문제를 재현을 위한 단계(가능한 경우)를 제공합니다.

  ![새 문제 보고](../ide/media/report-new-problem.png "새 문제 보고")

## 스크린샷 및 첨부 파일 제공(선택 사항)<a name="provide_screenshots"></a>

 현재 화면을 Microsoft로 보내려면 선택합니다. **추가 파일 첨부** 단추를 선택하여 추가 스크린샷 또는 다른 파일을 첨부할 수 있습니다.

## 추적 및 힙 덤프 제공(선택 사항)<a name="provide_a_trace_and_heap_dump"></a>

추적 및 힙 덤프 파일은 문제를 진단하는 데 유용합니다. **문제 보고** 도구를 사용하여 재현 단계를 기록하여 데이터를 Microsoft로 보내 주시면 감사하겠습니다. 방법은 다음과 같습니다.

1. **레코드** 탭을 선택합니다.
2. **기록 시작**을 선택합니다. 도구를 실행할 수 있는 권한을 제공합니다.

  ![추적 및 힙 덤프 파일을 제공하도록 "기록 시작" 선택] (../ide/media/record-dialog-box.png "추적 및 힙 덤프 파일 제공")

3. **단계 레코더** 도구가 나타나면 문제를 재현하는 단계를 수행합니다.
4. 완료되면 **기록 중지** 단추를 선택합니다.
5. Visual Studio에서 기록된 정보를 수집하여 패키징하는 동안 몇 분 정도 기다립니다.

## 보고서 제출<a name="submit_the_report"></a>

 **제출** 단추를 선택하여 이미지와 추적 또는 덤프 파일과 함께 보고서를 보냅니다. **제출** 단추가 회색으로 표시되는 경우 보고서의 제목과 설명을 입력했는지 확인합니다.

## 대안 보고 <a name="alternate_reporting"></a>

### <a name="report-a-problem-by-using-the-visual-studio-installer"></a>Visual Studio 설치 관리자를 사용하여 문제 보고

Visual Studio 설치를 완료할 수 없거나 Visual Studio 내에서 피드백 도구에 액세스할 수 없는 경우 Visual Studio 설치 관리자를 사용하여 문제를 보고할 수 있습니다. 이렇게 하려면 Visual Studio 설치 관리자의 오른쪽 위에서 피드백 아이콘을 선택합니다.

 ![Visual Studio 설치 관리자의 피드백 제공 단추를 탭하여 피드백 도구를 열 수 있습니다.](../install/media/report-a-problem.png)

### <a name="search-for-problems-and-solutions-by-using-the-visual-studio-developer-community"></a>Visual Studio 개발자 커뮤니티를 사용하여 문제 및 솔루션 검색

문제를 보고하기 위해 Visual Studio를 사용할 수 없거나 원하지 않는 경우 Visual Studio 개발자 커뮤니티에 문제가 이미 보고되고 솔루션이 게시됐을 수 있습니다. 자세한 내용은 [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/) 페이지를 참조하세요.

#### <a name="provide-product-feedback-or-a-suggestion"></a>제품 피드백 또는 제안 제공

보고할 문제가 없지만 제품 피드백 또는 제안을 제공하려는 경우 따로 위치가 정해져 있습니다. 자세한 내용은 [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-ide) 페이지를 참조하세요.

## <a name="see-also"></a>참고 항목

* [의견 보내기](../ide/talk-to-us.md)
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)
