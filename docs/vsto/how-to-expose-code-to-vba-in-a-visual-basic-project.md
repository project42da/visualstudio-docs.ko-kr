---
title: "방법: Visual Basic 프로젝트에서 VBA로 코드 노출"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 코드 노출"
  - "VBA에 코드 노출"
  - "호스트 항목[Visual Studio에서 Office 개발], VBA에 코드 노출"
  - "VBA[Visual Studio에서 Office 개발], 문서 수준 사용자 지정의 코드 노출"
  - "Visual Basic[Visual Studio에서 Office 개발], VBA에 코드 노출"
ms.assetid: dc74f3ea-3f78-47f8-8a82-a67896144dd9
caps.latest.revision: 47
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 방법: Visual Basic 프로젝트에서 VBA로 코드 노출
  VBA\(Visual Basic for Applications\) 코드와 Visual Basic 코드가 서로 상호 작용하도록 VBA 코드에 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 프로젝트의 코드를 노출할 수 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Visual Basic 프로세스는 Visual C\# 프로세스와 다릅니다.  자세한 내용은 [방법: Visual C&#35; 프로젝트에서 VBA로 코드 노출](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)을 참조하십시오.  
  
 호스트 항목 클래스에 있는 코드를 노출하는 프로세스는 다른 클래스에 있는 코드를 노출하는 프로세스와는 다릅니다.  
  
-   [호스트 항목 클래스에 있는 코드 노출](#HostItemCode)  
  
-   [호스트 항목 클래스에 있지 않은 코드 노출](#NonHostItem)  
  
 ![비디오에 링크](~/data-tools/media/playvideo.gif "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Call VSTO Code from VBA?](http://go.microsoft.com/fwlink/?LinkId=136757)를 참조하십시오.  
  
##  <a name="HostItemCode"></a> 호스트 항목 클래스에 있는 코드 노출  
 VBA 코드에서 호스트 항목 클래스에 있는 Visual Basic 코드를 호출할 수 있도록 하려면 호스트 항목의 **EnableVbaCallers** 속성을 **True**로 설정합니다.  
  
 호스트 항목 클래스의 메서드를 노출한 다음 이를 VBA에서 호출하는 방법을 보여 주는 연습은 [연습: Visual Basic 프로젝트에서 VBA의 코드 호출](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)을 참조하십시오.  호스트 항목에 대한 자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)를 참조하십시오.  
  
#### 호스트 항목에 있는 코드를 VBA로 노출하려면  
  
1.  매크로를 지원하는 Word 문서, Excel 통합 문서 또는 Excel 서식 파일을 기반으로 하며 VBA 코드가 이미 들어 있는 문서 수준 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 프로젝트를 열거나 만듭니다.  
  
     매크로를 지원하는 문서 파일 형식에 대한 자세한 내용은 [VBA 및 문서 수준 사용자 지정 결합](../vsto/combining-vba-and-document-level-customizations.md)을 참조하십시오.  
  
    > [!NOTE]  
    >  이 기능은 Word 서식 파일 프로젝트에서 사용할 수 없습니다.  
  
2.  매크로를 사용할 수 있도록 설정하라는 메시지 없이 문서의 VBA 코드를 실행할 수 있는지 확인합니다.  Word 또는 Excel의 보안 센터 설정에서 신뢰할 수 있는 위치 목록에 Office 프로젝트의 위치를 추가하여 VBA 코드를 실행할 수 있는 것으로 신뢰할 수 있습니다.  
  
3.  VBA로 노출할 속성, 메서드 또는 이벤트를 프로젝트의 호스트 항목 클래스 중 하나에 추가한 다음 새 멤버를 **Public**으로 선언합니다.  클래스의 이름은 응용 프로그램에 따라 다릅니다.  
  
    -   Word 프로젝트의 경우 호스트 항목 클래스의 이름은 기본적으로 `ThisDocument`로 지정됩니다.  
  
    -   Excel 프로젝트의 경우 호스트 항목 클래스의 이름은 기본적으로 `ThisWorkbook`, `Sheet1`, `Sheet2` 및 `Sheet3`으로 지정됩니다.  
  
4.  호스트 항목의 **EnableVbaCallers** 속성을 **True**로 설정합니다.  이 속성은 호스트 항목이 디자이너에 열려 있을 때 **속성** 창에서 사용할 수 있습니다.  
  
     이 속성을 설정한 후 Visual Studio에서는 자동으로 **ReferenceAssemblyFromVbaProject** 속성을 **True**로 설정합니다.  
  
    > [!NOTE]  
    >  통합 문서 또는 문서에 아직 VBA 코드가 없거나 문서의 VBA 코드가 실행할 수 있는 것으로 신뢰되지 않은 경우 **EnableVbaCallers** 속성을 **True**로 설정하면 오류 메시지가 표시됩니다.  이는 이 경우 Visual Studio에서 문서의 VBA 프로젝트를 수정할 수 없기 때문입니다.  
  
5.  메시지가 표시되면 **확인**을 클릭합니다.  이 메시지는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 프로젝트를 실행할 때 통합 문서나 문서에 VBA 코드를 추가하면 다음에 프로젝트를 빌드할 때 VBA 코드를 잃게 된다는 것을 알려 줍니다.  빌드 출력 폴더의 문서는 프로젝트를 빌드할 때마다 덮어쓰여지기 때문입니다.  
  
     이 시점에서 Visual Studio는 VBA 프로젝트에서 어셈블리를 호출할 수 있도록 프로젝트를 구성합니다.  또한 Visual Studio에서는 VBA 프로젝트의 `ThisDocument`, `ThisWorkbook`, `Sheet1`, `Sheet2` 또는 `Sheet3` 모듈에 `CallVSTOAssembly` 라는 속성도 추가합니다.  이 속성을 사용하여 VBA로 노출한 클래스의 공용 멤버에 액세스할 수 있습니다.  
  
6.  프로젝트를 빌드합니다.  
  
##  <a name="NonHostItem"></a> 호스트 항목 클래스에 있지 않은 코드 노출  
 VBA 코드에서 호스트 항목 클래스에 있지 않은 Visual Basic 코드를 호출할 수 있도록 하려면 해당 코드를 VBA에 표시되도록 수정합니다.  
  
#### 호스트 항목 클래스에 있지 않은 코드를 VBA로 노출하려면  
  
1.  매크로를 지원하는 Word 문서, Excel 통합 문서 또는 Excel 서식 파일을 기반으로 하며 VBA 코드가 이미 들어 있는 문서 수준 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 프로젝트를 열거나 만듭니다.  
  
     매크로를 지원하는 문서 파일 형식에 대한 자세한 내용은 [VBA 및 문서 수준 사용자 지정 결합](../vsto/combining-vba-and-document-level-customizations.md)을 참조하십시오.  
  
    > [!NOTE]  
    >  이 기능은 Word 서식 파일 프로젝트에서 사용할 수 없습니다.  
  
2.  매크로를 사용할 수 있도록 설정하라는 메시지 없이 문서의 VBA 코드를 실행할 수 있는지 확인합니다.  Word 또는 Excel의 보안 센터 설정에서 신뢰할 수 있는 위치 목록에 Office 프로젝트의 위치를 추가하여 VBA 코드를 실행할 수 있는 것으로 신뢰할 수 있습니다.  
  
3.  VBA로 노출하려는 멤버를 프로젝트의 public 클래스에 추가하고 새 멤버를 **public**으로 선언합니다.  
  
4.  VBA로 노출할 클래스에 다음 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 및 <xref:Microsoft.VisualBasic.ComClassAttribute> 특성을 적용합니다.  이러한 특성은 클래스가 VBA에 표시되도록 합니다.  
  
    ```vb  
    <Microsoft.VisualBasic.ComClass()> _  
    <System.Runtime.InteropServices.ComVisibleAttribute(True)> _  
    ```  
  
5.  VBA로 노출할 클래스의 인스턴스를 반환하도록 프로젝트에 포함된 호스트 항목 클래스의 **GetAutomationObject** 메서드를 재정의합니다.  다음 코드에서는 `DocumentUtilities`라는 클래스를 VBA로 노출한다고 가정합니다.  
  
    ```vb  
    Protected Overrides Function GetAutomationObject() As Object  
        Return New DocumentUtilities()  
    End Function  
    ```  
  
6.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]의 디자이너에서 문서\(Word의 경우\) 또는 워크시트\(Excel의 경우\)를 엽니다.  
  
7.  **속성** 창에서 **ReferenceAssemblyFromVbaProject** 속성을 선택하고 값을 **True**로 변경합니다.  
  
    > [!NOTE]  
    >  통합 문서 또는 문서에 아직 VBA 코드가 없거나 문서의 VBA 코드가 실행할 수 있는 것으로 신뢰되지 않은 경우 **ReferenceAssemblyFromVbaProject** 속성을 **True**로 설정하면 오류 메시지가 표시됩니다.  이는 이 경우 Visual Studio에서 문서의 VBA 프로젝트를 수정할 수 없기 때문입니다.  
  
8.  메시지가 표시되면 **확인**을 클릭합니다.  이 메시지는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 프로젝트를 실행할 때 통합 문서나 문서에 VBA 코드를 추가하면 다음에 프로젝트를 빌드할 때 VBA 코드를 잃게 된다는 것을 알려 줍니다.  빌드 출력 폴더의 문서는 프로젝트를 빌드할 때마다 덮어쓰여지기 때문입니다.  
  
     이 시점에서 Visual Studio는 VBA 프로젝트에서 어셈블리를 호출할 수 있도록 프로젝트를 구성합니다.  또한 VBA 프로젝트에 `GetManagedClass`라는 메서드를 추가됩니다.  VBA 프로젝트의 모든 위치에서 이 메서드를 호출하여 VBA로 노출된 클래스에 액세스할 수 있습니다.  
  
9. 프로젝트를 빌드합니다.  
  
## 참고 항목  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [VBA 및 문서 수준 사용자 지정 결합](../vsto/combining-vba-and-document-level-customizations.md)   
 [연습: Visual Basic 프로젝트에서 VBA의 코드 호출](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)   
 [방법: Visual C&#35; 프로젝트에서 VBA로 코드 노출](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)  
  
  