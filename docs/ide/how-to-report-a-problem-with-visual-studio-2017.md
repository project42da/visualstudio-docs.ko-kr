---
title: "Visual Studio 2017의 문제를 보고하는 방법 | Microsoft 문서"
ms.custom: 
ms.date: 11/07/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.technology: vs-acquisition
ms.openlocfilehash: 283fec9bcaa4f678f30f3a0eb0dda667146b03b9
ms.sourcegitcommit: 2c7f48ad6073a81fa927568793633f26cc1f0b15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="how-to-report-a-problem-with-visual-studio-2017"></a>Visual Studio 2017의 문제를 보고하는 방법
Visual Studio에 문제가 발생하는 경우와 관련하여 자세히 알려고 합니다. 진단하고 해결할 수 있도록 문제를 보고하는 방법은 다음과 같습니다.  

## <a name="sign-in-to-visual-studio"></a>Visual Studio에 로그인
아직 로그인하지 않았으면 문제를 보고하기 전에 먼저 Visual Studio에 로그인합니다. 이런 방식으로 경험하고 있는 문제를 보고하고 투표하거나 주석을 달 수 있습니다. 사용자가 게시한 다른 문제에 대해 주문하거나 주석을 달 수도 있습니다.

1.  다음 스크린샷과 같이 도구 오른쪽에 있는 **로그인**을 클릭합니다.
2.  화면의 지침에 따라 로그인합니다.

 ![문제 보고를 위한 로그인](../ide/media/sign-in-new-ux.png "문제 보고를 위한 로그인")  

## <a name="search-and-vote-for-similar-problems"></a>유사한 문제 검색 및 투표  
###  <a name="search_and_vote"></a>  

1.  문제를 검색하고 다른 사용자가 이미 보고했는지 확인합니다.
2.  다른 사용자가 이미 보고한 경우 "투표"하여 알려 주시기 바랍니다.  

  ![검색 및 유사한 문제에 투표](../ide/media/search-and-vote.png "검색 및 유사한 문제에 투표")

## <a name="report-a-new-problem"></a>새 문제 보고
###  <a name="report_new_problem"></a>
1.  원하는 항목을 찾지 못한 경우 화면 맨 아래에서 **새 문제 보고** 단추를 클릭합니다.
2.  올바른 Visual Studio 팀에게 전달될 수 있도록 문제에 대한 설명이 포함된 제목을 입력합니다.
3.  추가 세부 정보와 문제를 재현을 위한 단계(가능한 경우)를 제공합니다.

  ![새 문제 보고](../ide/media/report-new-problem.png "새 문제 보고")

## <a name="provide-a-screenshot-and-attachments-optional"></a>스크린샷 및 첨부 파일 제공(선택 사항)
###  <a name="provide_screenshots"></a>
 현재 화면을 Microsoft로 보내려면 선택합니다. **추가 파일 첨부** 단추를 클릭하여 추가 스크린샷 또는 다른 파일을 첨부할 수 있습니다.  

## <a name="provide-a-trace-and-heap-dump-optional"></a>추적 및 힙 덤프 제공(선택 사항)  
###  <a name="provide_a_trace_and_heap_dump"></a>  

추적 및 힙 덤프 파일은 문제를 진단하는 데 유용합니다. **문제 보고** 도구를 사용하여 재현 단계를 기록하여 데이터를 Microsoft로 보내 주시면 감사하겠습니다.  방법은 다음과 같습니다.

1.  **레코드** 탭을 클릭합니다.
2.  **기록 시작**을 클릭합니다. 도구를 실행할 수 있는 권한을 제공합니다.

  ![추적 및 힙 덤프 파일을 제공하도록 기록 시작 클릭] (../ide/media/record-dialog-box.png "추적 및 힙 덤프 파일 제공")

3.  **단계 레코더** 도구가 나타나면 문제를 재현하는 단계를 수행합니다.
4.  완료되면 **기록 중지** 단추를 클릭합니다.
5.  Visual Studio에서 기록된 정보를 수집하여 패키징하는 동안 몇 분 정도 기다립니다.

## <a name="submit-the-report"></a>보고서 제출  
###  <a name="submit_the_report"></a>  
 **제출** 단추를 클릭하여 이미지와 추적 또는 덤프 파일과 함께 보고서를 보냅니다. **제출** 단추가 회색으로 표시되는 경우 보고서의 제목과 설명을 입력했는지 확인합니다.  

## <a name="alternate-reporting"></a>대체 보고
###  <a name="alternate_reporting"></a>  
 Visual Studio 설치를 완료할 수 없거나 Visual Studio 내에서 피드백 도구에 액세스할 수 없는 경우에는 Visual Studio 설치 관리자에서도 피드백 도구를 사용할 수 있습니다. Visual Studio 설치 관리자의 오른쪽 위 모서리에 있는 피드백 아이콘을 클릭한 다음이 이 문서에 설명된 단계를 수행합니다.

 ![Visual Studio 설치 관리자의 피드백 제공 단추를 탭하여 피드백 도구를 열 수 있습니다.](../install/media/report-a-problem.png)

## <a name="see-also"></a>참고 항목  
 [의견 보내기](../ide/talk-to-us.md)
