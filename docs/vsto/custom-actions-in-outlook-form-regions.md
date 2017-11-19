---
title: "사용자 지정 작업 Outlook에서 양식 영역 | Microsoft Docs"
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
- form regions [Office development in Visual Studio], custom actions
- custom actions [Office development in Visual Studio]
ms.assetid: 583fd5f0-aafa-4858-9c54-38a9fdf3bede
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 74c688d0430b95c54f1f871ad6f82fde6fa781ac
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-actions-in-outlook-form-regions"></a>Outlook 양식 영역의 사용자 지정 작업
  작업은 사용자가 Microsoft Office Outlook 항목에 응답할 수 있도록 하는 단추를 표시 합니다. 예를 들어 메일 항목에 응답, 사용자가 클릭는 **회신**, **전체 회신**, 또는 **앞으로** 실행 단추입니다. 이러한 각 작업을 새 메일 항목을 만들고 원본 항목의 정보를 사용 하 여 항목의 필드를 채웁니다.  
  
 사용자 지정 작업 모든 종류의 Outlook 항목을 만들 수 있습니다. 예를 들어 사용자 지정 작업 새 약속 또는 작업 항목을 추가할 수 있습니다. 사용자 지정 작업의 속성을 설정 하거나 사용자 지정 코드를 사용 하 여 새 항목의 필드를 채웁니다. 사용자 지정 작업에 표시 된 **사용자 지정 작업** 드롭 다운 Outlook 검사기 창에 열려 있는 항목의 합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="adding-custom-actions-to-a-form-region"></a>양식 영역에 사용자 지정 작업 추가  
 양식 영역에 사용자 지정 작업을 추가 하려면 사용 된 **사용자 지정 작업** 대화 상자. 열 수는 **사용자 지정 작업** 대화 상자에서 **솔루션 탐색기** 를 확장 하 여는 **매니페스트** 노드를 선택 하는 **CustomActions**속성과 줄임표 단추를 클릭 한 다음 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표")).  
  
 사용할 수는 **사용자 지정 작업** 지정 하려면 대화 상자는 *양식의 대상*합니다. 대상 형식은 사용자 지정 작업을 실행할 때 표시 되는 양식입니다.  
  
 사용할 수도 있습니다는 **사용자 지정 작업** 원래 대상 폼에 표시할 항목의 정보를 지정 하려면 대화 상자.  
  
 다음 표에서에서 사용할 수 있는 속성 설명의 **사용자 지정 작업** 대화 상자.  
  
|속성|설명|  
|--------------|-----------------|  
|**AddressLike**|대상 양식이 처리 되는 방법을 지정 합니다.|  
|**본문**|원래 항목의 본문 대상 폼에 추가 되는 방법을 지정 합니다.|  
|**사용**|사용자 지정 작업을 사용할 수 있는지 여부를 나타냅니다. 이 속성은로 설정 하는 경우 **false**, 사용자 지정 작업을 사용할 수 없습니다.|  
|**메서드**|사용자 지정 작업을 실행할 때 사용할 수 있는 응답 형식을 지정 합니다. 사용자 지정 작업 양식을 보낼 수, 양식을 열려면 또는 보내거나 양식을 열 하 든 사용자에 게 확인 합니다.|  
|**Name**|코드에서이 사용자 지정 작업을 참조 하는 데 사용할 수 있는 내부 이름을 지정 합니다.|  
|**ShowOnRibbon**|원래 항목의 리본에 사용자 지정 작업을 표시할지 여부를 나타냅니다.|  
|**SubjectPrefix**|대상 폼의 제목 줄의 시작 부분에 삽입 되는 텍스트를 지정 합니다.|  
|**TargetForm**|대상 폼의 메시지 클래스 이름을 지정합니다. 예를 들어 입력 **IPM 합니다. 작업** 태스크 폼을 엽니다.|  
|**제목**|사용자 지정 작업 단추의 레이블을 지정합니다.|  
  
## <a name="customizing-a-custom-action-at-run-time"></a>런타임 시 사용자 지정 작업을 사용자 지정  
 또한 코드를 사용 하 여 사용자 지정 작업으로 동작을 추가할 수 있습니다. 예를 들어 전자 메일 받는 사람 이름을 사용 하 고 새 약속 항목에 있는 참석자도 이러한 이름을 추가 하는 코드를 추가할 수 있습니다. 이 작업을 수행 하려면 처리는 [사용자 지정](http://msdn.microsoft.com/library/office/ff862186.aspx) 의 이벤트는 [MailItem 개체](http://msdn.microsoft.com/library/office/ff861332.aspx)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook 메시지 클래스에 양식 영역 연결](../vsto/associating-a-form-region-with-an-outlook-message-class.md)  
  
  