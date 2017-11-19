---
title: "방법: 리본에 개발자 탭 표시 | Microsoft Docs"
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
- Ribbon [Office development in Visual Studio], tabs
- Developer tab [Office development in Visual Studio]
ms.assetid: ce7cb641-44f2-4a40-867e-a7d88f8e98a9
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: cad7fb4fe49df9688a0b9e7b3baa1f1108694136
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-show-the-developer-tab-on-the-ribbon"></a>방법: 리본 메뉴에 개발 도구 탭 표시
  액세스는 **개발자** 탭 Office 응용 프로그램의 리본 메뉴에 기본적으로 표시 되지 않으므로 해당 탭을 표시 하도록 구성 해야 있습니다. 예를 표시 Word의 문서 수준 사용자 지정에 <xref:Microsoft.Office.Tools.Word.GroupContentControl>을 추가하려면 해당 탭을 표시해야 합니다.  
  
> [!NOTE]  
>  이 지침은 Office 2010 또는 이상의 응용 프로그램에만 적용됩니다. 2007 Microsoft Office System에서이 탭이 표시 하려는 경우이 항목의 다음 버전을 참조 [하는 방법: 리본에 개발자 탭 표시](http://msdn.microsoft.com/library/bb608625(v=vs.90).aspx)합니다.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
> [!NOTE]  
>  하지는 **개발자** 탭 합니다.  
  
### <a name="to-show-the-developer-tab"></a>개발자 탭을 표시하려면  
  
1.  이 항목에서 지원하는 Office 응용 프로그램을 시작합니다. 참조는 **에 적용:** 이 항목의 앞부분에 나오는 참고 합니다.  
  
2.  에 **파일** 탭에서 선택 된 **옵션** 단추입니다.  
  
     다음 그림에서는 **파일** 탭 및 **옵션** Office 2010의 단추입니다.  
  
     ![Outlook 2010에서 옵션 파일을 선택](../vsto/media/vsto-office-file-tab.png "Outlook 2010에서 옵션 파일을 선택")  
  
     다음 그림에서는 **파일** Office 2013의 탭 합니다.  
  
     ![Outlook 2013의 파일 탭](../vsto/media/vsto-office2013-filetab.png "Outlook 2013의 파일 탭")  
  
     다음 그림에서는 **옵션** Office 2013에서 단추입니다.  
  
     ![Outlook 2013 Preview의 옵션 단추](../vsto/media/vsto-office2013-optionsbutton.png "Outlook 2013 preview에서의 옵션 단추")  
  
3.  에 *ApplicationName***옵션** 대화 상자에서 선택 하는 **리본 사용자 지정** 단추입니다.  
  
     다음 그림에서는 **옵션** 대화 상자와 **리본 사용자 지정** Excel 2010에서 단추입니다. 이 단추의 위치는 이 항목의 위쪽 “적용 대상" 섹션에 나열된 다른 모든 응용 프로그램에서 유사합니다.  
  
     ![리본 사용자 지정 단추](../vsto/media/vsto-office2010-customizeribbonbutton.png "리본 사용자 지정 단추")  
  
4.  기본 탭 목록에서 선택 된 **개발자** 확인란 합니다.  
  
     다음 그림에서는 **개발자** Word 2010에서 확인란 및 [!INCLUDE[Word_15_short](../vsto/includes/word-15-short-md.md)]합니다. 이 확인란의 위치는 이 항목의 위쪽 “적용 대상" 섹션에 나열된 다른 모든 응용 프로그램에서 유사합니다.  
  
     ![Word 옵션 대화 상자에서 개발자 확인란](../vsto/media/vsto-office2010-developercheckbox.png "Word 옵션 대화 상자에서의 개발자 확인란")  
  
5.  선택 된 **확인** 닫기 단추를는 **옵션** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)  
  
  