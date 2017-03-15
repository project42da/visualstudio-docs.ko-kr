---
title: "Visual Studio 2017의 문제를 보고하는 방법 | Microsoft 문서"
ms.custom: 
ms.date: 2016-10-05
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bee01179-cde5-4419-9095-190ee0ba5902
caps.latest.revision: 4
author: TerryGLee
ms.author: tglee
manager: ghogen
robots: noindex,nofollow
translationtype: Human Translation
ms.sourcegitcommit: b81a082de053b11e8dbe05317f69d4bcb603f4de
ms.openlocfilehash: 5aac18786f3952648eeea4e7d0258a5e59c497c2

---
# <a name="how-to-report-a-problem-with-visual-studio-2017-rc"></a>Visual Studio 2017 RC의 문제를 보고하는 방법
Visual Studio에서 문제가 발생하는 경우 Microsoft에서 문제를 진단하여 해결할 수 있도록 알려 주시기 바랍니다.  **문제 보고** 도구에서 단추만 몇 번 클릭하면 문제에 대한 자세한 정보를 수집한 후 Microsoft로 보낼 수 있습니다.  

 Microsoft는 사용자의 개인 정보를 소중히 여깁니다. Microsoft에서 사용자가 보낸 데이터를 취급하는 방법에 대한 자세한 내용은 [Microsoft Visual Studio 제품군 개인정보처리방침](https://www.visualstudio.com/en-us/dn948229)을 참조하세요.  

## <a name="open-the-report-a-problem-tool"></a>문제 보고 도구 열기  
 제목 표시줄에서 **빠른 실행** 옆에 있는 사용자 피드백 아이콘을 클릭하거나 **도움말 &#124; 의견 보내기 &#124; 문제 보고**를 클릭합니다.  

 ![문제 보고 메뉴 항목](../ide/media/report-a-problem-menu-item.png "문제 보고 메뉴 항목")  

## <a name="search-and-vote-for-similar-problems"></a>유사한 문제 검색 및 투표  
###  <a name="search_and_vote"></a>  

1.  문제를 검색하고 다른 사용자가 이미 보고했는지 확인합니다.
2.  다른 사용자가 이미 보고한 경우 "투표"하여 알려 주시기 바랍니다.  

  ![VS15-FeedbackTool-SearchForSimilarReportedProblems](../ide/media/feedbacktool-searchforsimilarreportedproblems.png "유사한 문제 검색 및 투표")


## <a name="report-a-new-problem"></a>새 문제 보고
###  <a name="report_new_problem"></a>
1.  Visual Studio **문제 보고** 도구의 왼쪽 아래에 있는 "**+**" 단추를 클릭합니다.  
2.  올바른 Visual Studio 팀에게 전달될 수 있도록 문제에 대한 설명이 포함된 제목을 입력합니다.  
3.  추가 세부 정보와 문제를 재현을 위한 단계(가능한 경우)를 제공합니다.  

  ![VS15-FeedbackTool-ReportANewProblem](../ide/media/feedbacktool-reportanewproblem.jpg "새 문제 보고")

## <a name="provide-a-screenshot-and-attachments-optional"></a>스크린샷 및 첨부 파일 제공(선택 사항)
###  <a name="provide_screenshots"></a>
 현재 화면을 Microsoft로 보내려면 선택합니다. **추가 파일 첨부** 단추를 클릭하여 추가 스크린샷 또는 다른 파일을 첨부할 수 있습니다.  

## <a name="provide-a-trace-and-heap-dump-optional"></a>추적 및 힙 덤프 제공(선택 사항)  
###  <a name="provide_a_trace_and_heap_dump"></a>  

추적 및 힙 덤프 파일은 문제를 진단하는 데 매우 유용합니다.   **문제 보고** 도구를 통해 재현 단계를 기록하고 데이터를 Microsoft로 보내 주시면 감사하겠습니다.  방법은 다음과 같습니다.

1.  **레코드** 탭을 클릭합니다.
2.  **기록 시작**을 클릭합니다. 도구를 실행할 수 있는 권한을 제공합니다.
3.  **단계 레코더** 도구가 나타나면 문제를 재현하는 단계를 수행합니다.
4.  완료되면 부동 창에서 **기록 중지** 단추를 클릭합니다.
5.  Visual Studio에서 기록된 정보를 수집하여 패키징하는 동안 몇 분 정도 기다립니다.  완료되면 다음과 유사한 대화 상자가 표시됩니다.   

  ![VS15-FeedbackTool-AddAttachments-TraceAndHeapDumpFiles](../ide/media/feedbacktool-addattachments-traceandheapdumpfiles.jpg "추적 및 힙 덤프 파일 제공")


## <a name="submit-the-report"></a>보고서 제출  
###  <a name="submit_the_report"></a>  
 **제출** 단추를 클릭하여 이미지와 추적 또는 덤프 파일과 함께 보고서를 보냅니다. **제출** 단추가 회색으로 표시되는 경우 보고서의 제목과 설명을 입력했는지 확인합니다.  

## <a name="see-also"></a>참고 항목  
 [의견 보내기](../ide/talk-to-us.md)



<!--HONumber=Feb17_HO4-->


