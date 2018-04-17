---
title: Outlook 메시지 클래스에 양식 영역 연결 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.InvalidMessageClassName
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FormRegionMessageClassAttribute
- form regions [Office development in Visual Studio], message classes
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 27797a6b7ec2a415daa525d8eb90c5bbfbe1f859
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="associating-a-form-region-with-an-outlook-message-class"></a>Associating a Form Region with an Outlook Message Class
  각 항목의 메시지 클래스와 양식 영역을 연결 하 여 양식 영역을 표시 하는 Microsoft Office Outlook 항목을 지정할 수 있습니다. 예를 들어 메일 항목 맨 아래에 양식 영역을 추가 하려는 경우 ipm 양식 영역을 연결할 수 있습니다. Message 클래스를 note 합니다.  
  
 메시지 클래스 이름을 지정 메시지 클래스에 양식 영역을 연결 하려면는 **새 Outlook 양식 영역** 마법사 또는 양식 영역 팩터리 클래스에 특성을 적용 합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="understanding-outlook-message-classes"></a>Outlook 메시지 클래스 이해  
 Outlook 메시지 클래스에는 Outlook 항목의 형식을 식별합니다. 다음 표에서 이러한 8 개 표준 항목 형식 및 해당 메시지 클래스 이름을 나열합니다.  
  
|Outlook 항목 형식|메시지 클래스 이름|  
|-----------------------|------------------------|  
|AppointmentItem|IPM 합니다. 약속|  
|ContactItem|IPM 합니다. 연락처|  
|메일 그룹 항목|IPM 합니다. 삭제|  
|JournalItem|IPM 합니다. 활동|  
|MailItem|IPM 합니다. 참고|  
|PostItem|IPM 합니다. Post 또는 IPM 합니다. Post.RSS|  
|TaskItem|IPM 합니다. 작업|  
  
 또한 사용자 지정 메시지 클래스의 이름을 지정할 수 있습니다. 사용자 지정 메시지 클래스에는 Outlook에서 정의 하는 사용자 지정 양식을 식별 합니다.  
  
> [!NOTE]  
>  대체 및 모두 대체 양식 영역에 대 한 새 사용자 지정 메시지 클래스 이름을 지정할 수 있습니다. 기존 사용자 지정 폼의 메시지 클래스 이름을 사용 하 여 필요가 없습니다. 사용자 지정 메시지 클래스의 이름은 고유 해야 합니다. 이름이 고유한 지 확인 하는 한 가지 방법은 다음과 비슷한 명명 규칙을 사용 하는: \< *StandardMessageClassName*>.\< *회사*>.\< *MessageClassName*> (예: IPM 합니다. Note.Contoso.MyMessageClass)입니다.  
  
## <a name="associating-a-form-region-with-an-outlook-message-class"></a>Associating a Form Region with an Outlook Message Class  
 메시지 클래스에 양식 영역을 연결 하는 방법은 두 가지가 있습니다.  
  
-   사용 하 여 **새 Outlook 양식 영역** 마법사.  
  
-   클래스 특성을 적용 합니다.  
  
### <a name="using-the-new-outlook-form-region-wizard"></a>새 Outlook 양식 영역 마법사를 사용 하 여  
 마지막 페이지에는 **새 Outlook 양식 영역** 마법사에서는 표준 메시지 클래스를 선택 하 고 양식 영역이 있는 연결할 사용자 지정 메시지 클래스의 이름을 입력 합니다.  
  
 표준 메시지 클래스는 양식 영역 전체 양식 또는 양식의 기본 페이지를 교체 하도록 디자인 된 경우에 사용할 수 없습니다. 폼에 새 페이지를 추가 하는 수정 하거나 양식의 맨 아래에 추가 된 양식에 대 한 표준 메시지 클래스 이름을 지정할 수 있습니다. 자세한 내용은 참조 [하는 방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.  
  
 하나 이상의 사용자 지정 메시지 클래스를 포함 하려면 입력에 해당 이름을 **이 양식 영역을 표시할 사용자 지정 메시지 클래스?** 상자입니다.  
  
 이름을 입력 하는 다음 지침을 준수 해야 합니다.  
  
-   정규화 된 메시지 클래스 이름 (예: "IPM 합니다. Note.Contoso ")입니다.  
  
-   세미콜론을 사용 하 여 여러 메시지 클래스 이름을 구분 합니다.  
  
-   "IPM 같은 표준 Outlook 메시지 클래스를 포함 하지 마십시오. 참고"또는"IPM 합니다. Contact "입니다. "IPM 등의 사용자 지정 메시지 클래스를 포함 합니다. Note.Contoso "입니다.  
  
-   단독으로 기본 메시지 클래스를 지정 하지 않으면 (예: "IPM").  
  
-   각 메시지 클래스 이름에 대해 256 자를 초과 하지 않는 합니다.  
  
 **새 Outlook 양식 영역** 마법사를 클릭할 때 사용자 입력의 형식만 유효성을 검사 **마침**합니다.  
  
> [!NOTE]  
>  **새 Outlook 양식 영역** 마법사에 제공 하는 메시지 클래스 이름 올 바르 거 나 유효한 지 확인 하지 않습니다.  
  
 마법사를 완료 하는 경우는 **새 Outlook 양식 영역** 마법사는 지정 된 메시지 클래스 이름을 포함 하는 양식 영역 클래스에 특성을 적용 합니다. 또한 이러한 특성을 수동으로 적용할 수 있습니다.  
  
### <a name="applying-class-attributes"></a>클래스 특성 적용  
 완료 한 후 Outlook 메시지 클래스에 양식 영역을 연결할 수는 **새 Outlook 양식 영역** 마법사. 이 작업을 수행 하려면 양식 영역 팩터리 클래스에 특성을 적용 합니다.  
  
 다음 예제에서는 두 개의 <xref:Microsoft.Office.Tools.Outlook.FormRegionMessageClassAttribute> 라는 양식 영역 팩터리 클래스에 적용 된 특성 `myFormRegion`합니다. 첫 번째 특성 메일 메시지 형식에 대 한 표준 메시지 클래스에 양식 영역을 연결합니다. 두 번째 특성 라는 사용자 지정 메시지 클래스에 양식 영역 연결 `IPM.Task.Contoso`합니다.  
  
 [!code-vb[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Attributes/FormRegion1.vb#1)]
 [!code-csharp[Trin_Outlook_FR_Attributes#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Attributes/FormRegion1.cs#1)]  
  
 특성 다음 지침을 준수 해야 합니다.  
  
-   사용자 지정 메시지 클래스에 대 한 정규화 된 메시지 클래스 이름을 사용 하 여 (예: "IPM 합니다. Note.Contoso ")입니다.  
  
-   단독으로 기본 메시지 클래스를 지정 하지 않으면 (예: "IPM").  
  
-   각 메시지 클래스 이름에 대해 256 자를 초과 하지 않는 합니다.  
  
-   전체 양식 또는 양식의 기본 페이지에서 양식 영역을 대체 하는 경우에 표준 메시지 클래스의 이름을 포함 하지 마십시오. 폼에 새 페이지를 추가 하는 수정 하거나 양식의 맨 아래에 추가 된 양식에 대 한 표준 메시지 클래스 이름을 지정할 수 있습니다. 자세한 내용은 참조 [하는 방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.  
  
 Visual Studio 프로젝트를 빌드할 때의 메시지 클래스 이름 형식을 확인 합니다.  
  
> [!NOTE]  
>  Visual Studio에서 제공 하는 메시지 클래스 이름 올 바르 거 나 유효한 지 확인 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Outlook 양식 영역 만들기 지침](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [형식 이름 및 메시지 클래스 개요](http://msdn.microsoft.com/library/office/ff867629.aspx)   
 [Outlook 양식 항목과 함께 작동](http://msdn.microsoft.com/library/office/ff869706.aspx)  
  
  