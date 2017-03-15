---
title: "방법: 활동 라이브러리 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
caps.latest.revision: 12
caps.handback.revision: 12
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 방법: 활동 라이브러리 만들기
사용자 지정 활동은 워크플로의 특정 비즈니스 프로세스를 모델링하는 데 사용됩니다.[!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]의 활동 라이브러리 템플릿은 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 사용하여 이러한 사용자 지정 활동을 시각적으로 만들 수 있도록 하기 위한 것입니다.  
  
### 워크플로 활동 라이브러리를 만들려면  
  
1.  [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]을 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트...**를 선택합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  **프로젝트 형식** 창에서 원하는 언어에 따라 **Visual C\#** 프로젝트 또는 **Visual Basic** 그룹의 **워크플로**를 선택합니다.  
  
4.  **템플릿** 창에서 **활동 라이브러리**를 선택합니다.  
  
5.  프로젝트를 식별하기 쉽도록 프로젝트를 설명하는 이름을 **이름** 상자에 입력합니다.  
  
6.  **위치** 상자에 프로젝트를 저장할 디렉터리를 입력하거나 **찾아보기**를 클릭하여 해당 디렉터리를 찾습니다.  
  
7.  **솔루션** 상자에 솔루션의 이름을 입력한 다음 **확인**을 클릭합니다.  
  
    > [!NOTE]
    >  기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가하려면 [!INCLUDE[vs2010](../modeling/includes/vs2010_md.md)]에서 해당 솔루션을 열고 **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭한 다음 **추가**, **새 프로젝트...**를 차례로 선택하여 **새 프로젝트** 대화 상자를 엽니다.그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.  
  
8.  프로젝트 템플릿이 활동 정의를 XAML로 만듭니다.[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]가 열리고 사용자 지정 활동의 캔버스가 표시됩니다.  
  
9. **도구 상자**의 활동을 디자인 화면으로 끌어 사용자 지정 활동 안에 넣습니다.  
  
    > [!CAUTION]
    >  사용자 지정 활동의 본문에 자식 활동을 한 개만 넣을 수 있지만, 자식 활동으로 <xref:System.Activities.Statements.Sequence> 활동 또는 <xref:System.Activities.Statements.Flowchart> 활동과 같은 복합 활동을 사용할 수 있습니다.  
  
## 참고 항목  
 [방법: 활동 만들기](../Topic/How%20to:%20Create%20an%20Activity.md)   
 [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)