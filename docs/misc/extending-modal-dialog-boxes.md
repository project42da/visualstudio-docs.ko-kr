---
title: "모달 대화 상자 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio 확장의 모달 대화 상자"
  - "Visual Studio 확장, 모달 대화 상자"
ms.assetid: 478743dc-9fd9-46d7-9739-859fb8841a4f
caps.latest.revision: 11
caps.handback.revision: 11
manager: "douge"
---
# 모달 대화 상자 확장
Visual Studio와 기능 및 시각적 호환성을 보장하려면 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName> 개체에서 대화 상자 창을 파생시켜 Visual Studio 확장에 대한 모달 대화 상자를 만듭니다. 이런 방식으로 파생된 대화 상자는 추가 기능을 제공할 수도 있습니다. 예를 들어 F1 도움말 대상을 설정하고 창에서 최소화 및 최대화를 사용하도록 설정할 수 있습니다.  
  
## 모달 대화 상자 만들기  
  
1.  프로젝트에서 System.XAML에 대한 참조를 추가합니다.  
  
2.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭한 다음 **창**을 클릭합니다.  
  
3.  창 이름을 지정하고 **추가**를 클릭합니다.  
  
     디자이너에 빈 XAML 창이 나타납니다.  
  
4.  다음 예제와 같이 최상위 `Window` 요소에서 <xref:Microsoft.VisualStudio.PlatformUI>에 대한 네임스페이스 선언을 추가하고 `Window` 요소를 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow?displayProperty=fullName> 요소로 변경합니다.  
  
     [!code-xml[VSModalDialog#02](../misc/codesnippet/Xaml/extending-modal-dialog-boxes_1.xaml)]  
  
5.  **도구 상자**에서 단추, 레이블 및 기타 컨트롤을 추가하고 텍스트 레이블을 입력한 다음 대화 상자의 모양을 조정합니다.  
  
6.  코드 뷰로 전환합니다.  
  
7.  클래스 정의에서 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow>에서 상속받을 클래스를 설정합니다. 기본적으로 클래스는 <xref:System.Windows.Window?displayProperty=fullName> 클래스에서 상속합니다.  
  
8.  단추 및 기타 컨트롤에 대한 이벤트 처리기를 추가합니다.  
  
#### 모달 대화 상자에 F1 도움말을 추가하려면  
  
1.  다음 예제와 같이 인수로 문자열을 사용하는 매개 변수를 생성자에 추가하고 동일한 매개 변수를 사용하여 기본 생성자에서 상속받을 생성자를 설정합니다.  
  
     [!code-cs[VSModalDialog#12](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_2.cs)]  
  
     이 생성자는 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasHelpButton%2A> 속성을 `true`로 설정하고, 사용자가 F1 키를 누르거나 **도움말** 단추를 클릭할 때 받은 문자열을 키워드로 사용할 수 있게 합니다.  
  
#### 모달 대화 상자에 최소화 및 최대화 단추를 추가하려면  
  
1.  다음 예제와 같이 생성자 함수에서 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.hasMinimizeButton%2A> 및 <xref:Microsoft.VisualStudio.PlatformUI.DialogWindow.hasHMaximizeButton%2A> 속성을 `true`로 설정합니다.  
  
     [!code-cs[VSModalDialog#13](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_3.cs)]  
  
    > [!WARNING]
    >  <xref:Microsoft.VisualStudio.PlatformUI.DialogWindowBase.HasHelpButton%2A> 속성이 `true`로 설정된 경우에도 **최소화** 및 **최대화** 단추가 표시되면 **도움말** 단추는 숨겨집니다.  
  
## 예제  
 다음 예제에서는 두 개의 생성자가 있는 모달 대화 상자를 보여 줍니다. 첫 번째 생성자는 F1 키워드를 인수로 사용하고 **도움말** 단추를 표시합니다. 두 번째 생성자는 인수를 사용하지 않지만 **최소화** 및 **최대화** 단추를 표시합니다.**예** 단추를 클릭하면 대화 상자의 두 번째 인스턴스가 호출되고 도움말을 사용할 수 있습니다.  
  
 [!code-xml[VSModalDialog#01](../misc/codesnippet/Xaml/extending-modal-dialog-boxes_4.xaml)]  
  
 [!code-cs[VSModalDialog#11](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_5.cs)]  
  
 다음 코드에서는 이벤트 처리기에서 대화 상자를 호출합니다.  
  
 [!code-cs[VSModalDialog#21](../misc/codesnippet/CSharp/extending-modal-dialog-boxes_6.cs)]  
  
## 참고 항목  
 [만들기 및 관리 모달 대화 상자](../extensibility/creating-and-managing-modal-dialog-boxes.md)