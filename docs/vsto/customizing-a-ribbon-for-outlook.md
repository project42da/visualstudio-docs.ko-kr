---
title: Outlook에 대 한 리본을 사용자 지정
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Inspectors [Office development in Visual Studio]
- Outlook [Office development in Visual Studio], Ribbon
- customizing the Ribbon, about customizing the Ribbon
- custom Ribbon, about customizing the Ribbon
- Ribbon [Office development in Visual Studio], Outlook
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ef1c72d5c24c70a539b909e8d338a235ceb52a49
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="customize-a-ribbon-for-outlook"></a>Outlook에 대 한 리본을 사용자 지정
  Microsoft Office Outlook에서 리본을 사용자 지정할 경우 응용 프로그램에서 사용자 지정 리본이 나타나는 위치를 고려해야 합니다. Outlook에서 리본은 사용자가 메일 메시지 만들기 등의 특정 작업을 수행할 때 열리는 창과 기본 응용 프로그램 UI(사용자 인터페이스)에 표시됩니다. 이러한 응용 프로그램 창의 이름을 검사기라고 합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [사용 할까요?: Outlook에서 리본을 사용자 지정 리본 디자이너 작업 방법?](http://go.microsoft.com/fwlink/?LinkID=130312)합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="add-a-custom-ribbon-to-the-main-application-ui"></a>기본 응용 프로그램 UI 사용자 지정 리본 메뉴 추가  
 Outlook의 기본 응용 프로그램 UI를 탐색기라고 합니다. 사용 하는 경우는 **리본 (비주얼 디자이너)** 클릭 하 여 탐색기에 리본 메뉴를 추가할 수는 항목,는 **RibbonType** 에서 리본 메뉴의 속성은 **속성** 창 다음을 선택 하 고 **Microsoft.Outlook.Explorer**합니다.  
  
## <a name="assign-a-ribbon-to-an-inspector"></a>검사기에 리본 할당  
 검사기에 대한 메시지 클래스에 해당하는 리본 형식을 지정하여 사용자 지정하려는 검사기를 식별합니다.  
  
 사용 하는 경우는 **리본 (비주얼 디자이너)** 항목을 클릭는 **RibbonType** 에서 리본 메뉴의 속성은 **속성** 창, 선택 하나 이상의 리본 Id를 값의 목록입니다.  
  
 프로젝트에 리본을 두 개 이상 추가할 수 있습니다. 두 개 이상의 리본이 리본 ID를 공유하는 경우 프로젝트의 `ThisAddin` 클래스에서 `CreateRibbonExtensibilityObject` 메서드를 재정의하여 런타임에 표시할 리본을 지정합니다. 자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다. 각 리본 형식에 대 한 자세한 내용은 기술 문서를 참조 하십시오. [Outlook 2007에서 리본을 사용자 지정](http://msdn.microsoft.com/en-us/946e97ea-f556-4e84-8fac-01cd9214e170)합니다.  
  
## <a name="specify-the-ribbon-type-by-using-ribbon-xml"></a>리본 XML을 사용 하 여 리본 형식 지정  
 사용 하는 경우는 **리본 (XML)** 항목의 값을 확인는 *ribbonID* 에서 매개 변수는 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드와 적절 한 리본을 반환 합니다.  
  
 <xref:Microsoft.Office.Core.IRibbonExtensibility.GetCustomUI%2A> 메서드는 Visual Studio를 통해 리본 코드 파일에서 자동으로 생성됩니다. *ribbonID* 매개 변수는 탐색기 또는 특정 형식의 검사기를 식별 하는 문자열입니다. 가능한 값의 전체 목록은 *ribbonID* 매개 변수를 기술 문서를 참조 하십시오. [Outlook 2007에서 리본을 사용자 지정](http://msdn.microsoft.com/en-us/946e97ea-f556-4e84-8fac-01cd9214e170)합니다.  
  
 다음 코드 예제에서는 `Microsoft.Outlook.Mail.Compose` 검사기에만 사용자 지정 리본을 표시하는 방법을 보여 줍니다. 사용자가 새 메일 메시지를 만들 때 열리는 검사기입니다. 표시할 리본에 지정 된는 `GetResourceText()` 에 생성 된 메서드는 **리본** 클래스입니다. 에 대 한 자세한 내용은 **리본** 클래스를 참조 하십시오. [리본 XML](../vsto/ribbon-xml.md)합니다.  
  
 [!code-csharp[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/CSharp/Trin_RibbonOutlookBasic/Ribbon1.cs#1)]
 [!code-vb[Trin_RibbonOutlookBasic#1](../vsto/codesnippet/VisualBasic/Trin_RibbonOutlookBasic/Ribbon1.vb#1)]  
  
## <a name="see-also"></a>참고자료  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)  
  
  