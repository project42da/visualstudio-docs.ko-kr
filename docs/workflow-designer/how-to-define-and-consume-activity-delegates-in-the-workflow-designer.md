---
title: "방법: Workflow Designer에서 활동 대리자 정의 및 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c68e42ad-3ec0-4c2d-b104-fe36c6d83b5e
caps.latest.revision: 3
ms.author: "sdanie"
manager: "erikre"
caps.handback.revision: 3
---
# 방법: Workflow Designer에서 활동 대리자 정의 및 사용
[!INCLUDE[net_v45](../ide/includes/net_v45_md.md)]는 <xref:System.Activities.Statements.InvokeDelegate> 활동에 대해 기본으로 제공되는 새 디자이너를 포함하고 있습니다.이 디자이너는 <xref:System.Activities.ActivityAction> 또는 <xref:System.Activities.ActivityFunc%601> 같은 <xref:System.Activities.ActivityDelegate>에서 파생되는 활동에 대리자를 할당하는 데 사용할 수 있습니다.  
  
### 활동 대리자 정의  
  
1.  [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.왼쪽에서 **워크플로** 노드를 선택하고 오른쪽에서 **워크플로 콘솔 응용 프로그램** 템플릿을 선택합니다.프로젝트 이름\(원할 경우\)을 지정하고 **확인**을 클릭합니다.  
  
2.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 항목**을 선택합니다.왼쪽에서 **워크플로** 노드를 선택하고 오른쪽에서 **활동** 템플릿을 선택합니다.새 활동 이름을 **MyForEach.xaml**로 지정한 다음 **확인**을 클릭합니다.워크플로 디자이너에서 활동이 열립니다.  
  
3.  워크플로 디자이너에서 **인수** 탭을 클릭합니다.  
  
4.  **인수 만들기**를 클릭합니다.새 인수의 이름을 **Items**으로 지정합니다.  
  
5.  **인수 형식** 열에서 **Array of \[T\]**를 선택합니다.  
  
6.  형식 브라우저에서 **개체**를 선택합니다.**확인**을 클릭합니다.  
  
7.  **인수 만들기**를 다시 클릭합니다.새 인수의 이름을 **Body**로 지정합니다.새 인수의 **방향** 열에서 **속성**을 선택합니다.  
  
8.  인수 형식 열에서 **형식 찾아보기**를 선택합니다.  
  
9. 형식 브라우저에서 **형식 이름** 필드에 **ActivityAction**을 입력합니다.트리뷰에서 **ActivityAction\<T\>**를 선택합니다.나타나는 드롭다운에서 **개체**를 선택하여 **ActivityAction\<Object\>** 형식을 인수에 할당합니다.  
  
10. <xref:System.Activities.Statements.While> 활동을 도구 상자의 **흐름 제어** 섹션에서 디자이너 화면으로 끌어 놓습니다.  
  
11. <xref:System.Activities.Statements.While> 활동을 선택하고 **변수** 탭을 선택합니다.  
  
12. **변수 만들기**를 선택합니다.새 변수의 이름을 **Index**로 지정합니다.  
  
13. **변수 형식** 열에서 **Int32**를 선택합니다.**범위**를 **While**로, **기본** 열은 비워둡니다.  
  
14. <xref:System.Activities.Statements.While> 활동의 **조건** 속성을 **index \< Items.Length;**로 설정합니다.  
  
15. <xref:System.Activities.Statements.InvokeDelegate> 활동을 도구 상자의 **기본 형식** 섹션에서 <xref:System.Activities.Statements.While> 활동의 **Body**로 끌어 놓습니다.  
  
16. 대리자 드롭다운 목록에서 **Body**를 선택합니다.  
  
17. <xref:System.Activities.Statements.InvokeDelegate> 활동의 **속성** 그리드에서 **대리자 인수** 속성의 **…** 단추를 클릭합니다.  
  
18. **Argument**라는 인수의 **값** 열에서 **Items\[Index\]**를 입력합니다.**확인**을 클릭하여 **DelegateArguments** 대화 상자를 닫습니다.  
  
19. <xref:System.Activities.Statements.Assign> 활동을 <xref:System.Activities.Statements.InvokeDelegate> 활동 아래의 가로선으로 끌어 놓습니다.<xref:System.Activities.Statements.Assign> 활동이 만들어지고 <xref:System.Activities.Statements.Sequence> 활동이 **MyForEach** 활동의 **Body** 섹션에 두 활동을 포함하도록 자동으로 만들어집니다.**Body** 섹션은 단일 활동만 포함할 수 있으므로 시퀀스가 필요합니다.새 <xref:System.Activities.Statements.Sequence> 활동을 자동으로 만드는 기능은 [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)]의 새 기능입니다.  
  
20. <xref:System.Activities.Statements.Assign> 활동의 **To** 속성을 **인덱스**로 설정합니다.**할당** 활동의 **값** 속성을 **index\+1**로 설정합니다.  
  
 사용자 지정 **MyForEach** 활동은 이제 활동에 대한 입력으로 컬렉션의 값을 사용하여 **Items** 컬렉션을 통해 전달되는 각 값에 대해 임의의 활동을 한 번 호출합니다.  
  
### 워크플로에서 사용자 지정 활동 사용  
  
1.  **Ctrl\+Shift\+B**를 눌러 프로젝트를 빌드합니다.  
  
2.  **솔루션 탐색기**의 디자이너에서 **Workflow1.xaml**을 엽니다.  
  
3.  도구 상자의 **MyForEach** 활동을 디자이너 화면으로 끌어 옵니다.활동은 프로젝트와 같은 이름을 사용하여 도구 상자의 한 섹션에 있게 됩니다.  
  
4.  **MyForEach** 활동의 **항목** 속성을 **new Object\[\] {1, "abc"}**로 설정합니다.  
  
5.  <xref:System.Activities.Statements.WriteLine> 활동을 도구 상자의 **기본 형식** 섹션에서 **MyForEach** 활동의 **Delegate:Body** 섹션으로 끌어 놓습니다.  
  
6.  <xref:System.Activities.Statements.WriteLine> 활동의 **Text** 속성을 **Argument.ToString\(\)**으로 설정합니다.  
  
 워크플로가 실행되면 콘솔에 다음이 표시됩니다.  
  
 **1**   
**abc**