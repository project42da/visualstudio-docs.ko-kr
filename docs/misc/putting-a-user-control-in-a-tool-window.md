---
title: "도구 창에 사용자 정의 컨트롤 배치 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 창, 사용자 지정 컨트롤 추가"
  - "사용자 정의 컨트롤[Visual Studio SDK], 도구 창에 추가"
  - "사용자 정의 컨트롤[Visual Studio SDK]"
ms.assetid: 869f3195-e152-4e61-802c-51d6b7ba3e36
caps.latest.revision: 29
caps.handback.revision: 29
manager: "douge"
---
# 도구 창에 사용자 정의 컨트롤 배치
이 연습에는 도구 창에 사용자 정의 컨트롤을 추가하는 방법을 보여 줍니다.  
  
 사용자 정의 컨트롤은 한 컨트롤에 함께 바인딩된 Windows 컨트롤의 모음입니다. 도구 창에 사용자 정의 컨트롤을 추가하려면 사용자 정의 컨트롤이 **도구 상자**에 표시되어야 합니다. 이 연습에서 사용되는 사용자 정의 컨트롤은 [연습: Visual C\#에서 합성 컨트롤 제작](../Topic/Walkthrough:%20Authoring%20a%20Composite%20Control%20with%20Visual%20C%23.md)에서 개발된 시계 컨트롤입니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## 사용자 정의 컨트롤 만들기  
  
1.  [연습: Visual C\#에서 합성 컨트롤 제작](../Topic/Walkthrough:%20Authoring%20a%20Composite%20Control%20with%20Visual%20C%23.md)의 단계에 따라 시계 컨트롤을 만듭니다. 알람 시계 컨트롤을 만들지 마세요.  
  
> [!NOTE]
>  다음 단계에서는 시계 컨트롤의 이름이 `ctlClock`이라고 가정합니다.  
  
## 도구 창 확장 만들기  
  
1.  `MyToolWindow`라는 도구 창이 있는 `MyToolWindowPackageUC`라는 VSIX 프로젝트를 만듭니다. 이 작업에 대한 도움이 필요한 경우 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)를 참조하세요.  
  
## 사용자 정의 컨트롤 추가  
  
1.  **솔루션 탐색기**에서 솔루션 **MyToolWindowPackageUC**를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **기존 프로젝트**를 클릭합니다.  
  
2.  **기존 프로젝트 추가** 대화 상자에서 ctlClockLib 프로젝트를 열고 ctlClock.lib.csproj 프로젝트 파일을 선택합니다.**확인**을 클릭합니다. 이렇게 하면 디자이너에서 사용자 정의 컨트롤을 사용할 수 있게 됩니다.  
  
3.  **솔루션 탐색기**에서 MyToolWindowControl.cs를 마우스 오른쪽 단추로 클릭하고 **뷰 디자이너**를 선택합니다. 도구 창에 대해 생성된 컨트롤을 보여 주는 폼 디자이너가 열립니다.  
  
4.  **도구 상자**를 열고 레이블이 **ctlClockLib Components**인 섹션을 찾아 해당 섹션에서 **ctlClock** 컨트롤을 두 번 클릭하여 컨트롤을 폼에 추가합니다.**도구 상자**를 숨기자마자 도구 창 폼에 시간이 표시되는 것을 볼 수 있습니다.  
  
5.  디자이너에서 방금 추가된 시계 컨트롤을 선택하고 **Anchor** 속성을 **Top**으로 변경합니다.  
  
6.  **솔루션 탐색기**에서 ctlClockLib 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
7.  **서명** 탭에서 **어셈블리 서명**을 선택합니다.**강력한 이름 키 파일 선택** 상자에서 **\<찾아보기\>**를 클릭하고 **MyToolWindowPackageUC** 프로젝트 폴더의 key.snk 파일로 이동합니다.  
  
8.  프로그램을 컴파일하고 오류가 없는지 확인합니다. 이 단계는 Visual Studio를 사용하여 VSPackage 및 해당 도구 창을 등록합니다.  
  
9. F5 키를 눌러 실험적 하이브에서 Visual Studio 인스턴스를 엽니다.  
  
10. 실험적 Visual Studio의 **보기** 메뉴에서 **다른 창**을 가리키고 **MyToolWindow**를 클릭합니다. 실행 시간이 표시되는 도구 창이 나타납니다.  
  
## 참고 항목  
 [연습: Visual C\#에서 합성 컨트롤 제작](../Topic/Walkthrough:%20Authoring%20a%20Composite%20Control%20with%20Visual%20C%23.md)