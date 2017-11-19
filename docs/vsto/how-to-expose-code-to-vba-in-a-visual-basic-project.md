---
title: "방법: Visual Basic 프로젝트에서 VBA로 코드 노출 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], exposing code in document-level customizations
- document-level customizations [Office development in Visual Studio], exposing code
- Visual Basic [Office development in Visual Studio], exposing code to VBA
- exposing code to VBA
- host items [Office development in Visual Studio], exposing code to VBA
ms.assetid: dc74f3ea-3f78-47f8-8a82-a67896144dd9
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 782b42c83f9557b6567849e4d03c7ad9e221da49
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-expose-code-to-vba-in-a-visual-basic-project"></a>How to: Expose Code to VBA in a Visual Basic Project
  코드에 노출할 수 있습니다는 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 두 가지 유형의 서로 상호 작용 하는 코드를 원하는 경우 VBA 코드에 대 한 Visual basic 프로젝트.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Visual Basic 프로세스는 Visual C# 프로세스와에서 다릅니다. 자세한 내용은 참조 [하는 방법: Visual C# 35; 및 답변에서 VBA로 코드 노출 프로젝트](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)합니다.  
  
 프로세스는 다른 클래스에 코드의 경우 코드는 호스트 항목 클래스에 대 한 다릅니다.  
  
-   [호스트 항목 클래스에 코드 노출](#HostItemCode)  
  
-   [호스트 항목 클래스에 없는 코드 노출](#NonHostItem)  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [어떻게 수행 할까요 호출 VSTO 코드 VBA에서?](http://go.microsoft.com/fwlink/?LinkId=136757)합니다.  
  
##  <a name="HostItemCode"></a>호스트 항목 클래스에 코드 노출  
 호스트 항목 클래스에는 Visual Basic 코드를 호출 하는 VBA 코드를 사용 하려면 설정는 **EnableVbaCallers** 호스트 항목의 속성 **True**합니다.  
  
 호스트 항목 클래스의 메서드를 노출 하 고 VBA에서 호출 하는 방법을 보여 주는 연습을 참조 하십시오. [연습: Visual Basic 프로젝트에서 vba의 코드 호출](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)합니다. 호스트 항목에 대한 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)를 참조하세요.  
  
#### <a name="to-expose-code-in-a-host-item-to-vba"></a>VBA에 대 한 호스트 항목의 코드를 노출 하려면  
  
1.  열기 또는 문서 수준 만들기 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] Word 문서, Excel 통합 문서 또는 매크로 지원 하 고 VBA 코드가 이미 들어 있는 Excel 서식 파일을 기반으로 하는 프로젝트입니다.  
  
     매크로 지 원하는 문서 파일 형식에 대 한 자세한 내용은 참조 [결합 VBA 및 문서 수준 사용자 지정](../vsto/combining-vba-and-document-level-customizations.md)합니다.  
  
    > [!NOTE]  
    >  이 기능은 Word 서식 파일 프로젝트에서 사용할 수 없습니다.  
  
2.  문서의 VBA 코드를 매크로 사용 하도록 사용자에 게 확인 하지 않고 실행할 수 있는지 확인 합니다. Word 또는 Excel의 보안 센터 설정에서 신뢰할 수 있는 위치 목록에 Office 프로젝트의 위치를 추가하여 VBA 코드를 실행하도록 신뢰할 수 있습니다.  
  
3.  속성, 메서드 또는 프로젝트에서 호스트 항목 클래스 중 하나를 VBA에 노출 하려는 이벤트를 추가 하 고 새 멤버를 선언 **공용**합니다. 클래스의 이름을 응용 프로그램에 따라 달라 집니다.  
  
    -   프로젝트를 호스트 항목 클래스의 이름이 한마디로 `ThisDocument` 기본적으로 합니다.  
  
    -   Excel 프로젝트에서 호스트 항목 클래스 이름은 `ThisWorkbook`, `Sheet1`, `Sheet2`, 및 `Sheet3` 기본적으로 합니다.  
  
4.  설정의 **EnableVbaCallers** 호스트 항목에 대 한 속성 **True**합니다. 이 속성을 사용할 수는 **속성** 호스트 항목은 디자이너에에서 열려 있는 창입니다.  
  
     이 속성을 설정한 후 Visual Studio 자동으로 설정 하는 **ReferenceAssemblyFromVbaProject** 속성을 **True**합니다.  
  
    > [!NOTE]  
    >  통합 문서 또는 문서 포함 되어 있지 않으면, VBA 코드 하거나 설정 하는 경우는 오류 메시지가 표시 됩니다는 문서의 VBA 코드를 실행 하도록 신뢰할 수 없는 경우는 **EnableVbaCallers** 속성을 **True**합니다. 그 이유는 이러한 경우 Visual Studio에서 문서의 VBA 프로젝트를 수정할 수 없기 때문입니다.  
  
5.  표시되는 메시지에서 **확인** 을 클릭합니다. 이 메시지 것을 표시 하는 동안 문서나 통합 문서에 VBA 코드를 추가 하면 프로젝트를 실행 중인 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA 코드 손실 됩니다 다음에 프로젝트를 빌드합니다. 즉, 프로젝트를 빌드할 때마다 빌드 출력 폴더의 문서를 덮어씁니다.  
  
     이 시점에서 VBA 프로젝트에서 어셈블리를 호출할 수 있도록 Visual Studio 프로젝트를 구성 합니다. Visual Studio는 또한 라는 속성을 추가 `CallVSTOAssembly` 에 `ThisDocument`, `ThisWorkbook`, `Sheet1`, `Sheet2`, 또는 `Sheet3` VBA 프로젝트의 모듈입니다. VBA에 노출 하는 클래스의 공용 멤버에 액세스 하려면이 속성을 사용할 수 있습니다.  
  
6.  프로젝트를 빌드합니다.  
  
##  <a name="NonHostItem"></a>호스트 항목 클래스에 없는 코드 노출  
 호스트 항목 클래스에 없는 Visual Basic 코드를 호출 하는 VBA 코드를 사용 하려면 VBA에 표시 되므로 코드를 수정 합니다.  
  
#### <a name="to-expose-code-that-is-not-in-a-host-item-class-to-vba"></a>호스트 항목 클래스를 VBA에 있지 않은 코드에 노출 하려면  
  
1.  열기 또는 문서 수준 만들기 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] Word 문서, Excel 통합 문서 또는 매크로 지원 하 고 VBA 코드가 이미 들어 있는 Excel 서식 파일을 기반으로 하는 프로젝트입니다.  
  
     매크로 지 원하는 문서 파일 형식에 대 한 자세한 내용은 참조 [결합 VBA 및 문서 수준 사용자 지정](../vsto/combining-vba-and-document-level-customizations.md)합니다.  
  
    > [!NOTE]  
    >  이 기능은 Word 서식 파일 프로젝트에서 사용할 수 없습니다.  
  
2.  문서의 VBA 코드를 매크로 사용 하도록 사용자에 게 확인 하지 않고 실행할 수 있는지 확인 합니다. Word 또는 Excel의 보안 센터 설정에서 신뢰할 수 있는 위치 목록에 Office 프로젝트의 위치를 추가하여 VBA 코드를 실행하도록 신뢰할 수 있습니다.  
  
3.  프로젝트에서 공용 클래스를 VBA에 노출 하려는 멤버를 추가 하 고 새 멤버를 선언 **공용**합니다.  
  
4.  다음 적용 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 및 <xref:Microsoft.VisualBasic.ComClassAttribute> 특성 VBA에 노출할 클래스에 있습니다. 이러한 특성 확인 클래스를 VBA에 표시 합니다.  
  
    ```vb  
    <Microsoft.VisualBasic.ComClass()> _  
    <System.Runtime.InteropServices.ComVisibleAttribute(True)> _  
    ```  
  
5.  VBA에 노출할 클래스의 인스턴스를 반환하도록 프로젝트에서 호스트 항목 클래스의 **GetAutomationObject** 메서드를 재정의합니다. 다음 코드 예제에서는 라는 클래스를 노출 한다고 가정 `DocumentUtilities` VBA에 있습니다.  
  
    ```vb  
    Protected Overrides Function GetAutomationObject() As Object  
        Return New DocumentUtilities()  
    End Function  
    ```  
  
6.  문서 (Word) 또는 (Excel 용) 워크시트 디자이너를 열고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
7.  **속성** 창에서 **ReferenceAssemblyFromVbaProject** 속성을 선택하고 값을 **True**로 변경합니다.  
  
    > [!NOTE]  
    >  통합 문서 또는 문서 포함 되어 있지 않으면, VBA 코드 하거나 설정 하는 경우는 오류 메시지가 표시 됩니다는 문서의 VBA 코드를 실행 하도록 신뢰할 수 없는 경우는 **ReferenceAssemblyFromVbaProject** 속성을 **True** . 그 이유는 이러한 경우 Visual Studio에서 문서의 VBA 프로젝트를 수정할 수 없기 때문입니다.  
  
8.  표시되는 메시지에서 **확인** 을 클릭합니다. 이 메시지 것을 표시 하는 동안 문서나 통합 문서에 VBA 코드를 추가 하면 프로젝트를 실행 중인 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], VBA 코드 손실 됩니다 다음에 프로젝트를 빌드합니다. 즉, 프로젝트를 빌드할 때마다 빌드 출력 폴더의 문서를 덮어씁니다.  
  
     이 시점에서 VBA 프로젝트에서 어셈블리를 호출할 수 있도록 Visual Studio 프로젝트를 구성 합니다. Visual Studio도 라는 메서드를 추가 `GetManagedClass` VBA 프로젝트에 있습니다. 모든 위치에서이 메서드를 호출할 수에서 VBA 프로젝트를 VBA에 노출 한 클래스에 액세스 합니다.  
  
9. 프로젝트를 빌드합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Combining VBA and Document-Level Customizations](../vsto/combining-vba-and-document-level-customizations.md)   
 [연습: Visual Basic 프로젝트에서 vba의 코드 호출](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)   
 [방법: Visual C# 35; 및 답변에서 VBA로 코드 노출 프로젝트](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)  
  
  