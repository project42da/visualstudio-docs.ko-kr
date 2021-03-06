---
title: '방법: Updater 메서드 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], updating data
- BDC [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating data
- Business Data Connectivity service [SharePoint development in Visual Studio], Updater
- Business Data Connectivity service [SharePoint development in Visual Studio], updating entity instances
- BDC [SharePoint development in Visual Studio], updating entity instances
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 808e37b6d172a63288751c28dfdcd1e43d466c08
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767423"
---
# <a name="how-to-add-an-updater-method"></a>방법: Updater 메서드 추가
  사용자가을 만들어서 외부 SharePoint 목록의 비즈니스 데이터를 업데이트할 사용 하도록 설정할 수는 *Updater* 메서드. 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
### <a name="to-create-an-updater-method"></a>Updater 메서드를 만들려면  
  
1.  BDC 디자이너에서 엔터티를 선택 합니다.  
  
2.  메뉴 모음에서 **보기** > **다른 창** > **BDC 메서드 세부 정보**합니다.  
  
     BDC 메서드 세부 정보 창이 열립니다. 이 창에 대 한 자세한 내용은 참조 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)합니다.  
  
3.  에 **메서드 추가** 목록에서 선택 **Updater 메서드 만들기**합니다.  
  
     Visual Studio는 모델에 다음과 같은 요소를 추가합니다. 이러한 요소 BDC 메서드 세부 정보 창에 나타납니다.  
  
    -   라는 메서드 **업데이트**합니다.  
  
    -   메서드에 대 한 입력된 매개 변수입니다.  
  
    -   형식 설명자는 매개 변수입니다. 기본적으로 Visual Studio에서는 Finder 메서드에 대해 정의 된 엔터티 형식 설명자를 사용 (예: 연락처).  
  
    -   메서드에 대 한 메서드 인스턴스입니다.  
  
     자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
    > [!NOTE]  
    >  엔터티 유형의 식별자는 자동으로 생성 되는 데이터베이스 테이블에 있는 필드를 나타내는 경우 설정의 **사전 Updater 필드** 속성을 **True**합니다.  
  
4.  **솔루션 탐색기**, 엔터티에 대해 생성 된 서비스 코드 파일의 바로 가기 메뉴를 열고 선택한 후 **코드 보기**합니다.  
  
     엔터티 서비스 코드 파일이 열립니다는 **코드 편집기**합니다. 해당 파일에 대 한 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
5.  데이터를 업데이트 하면 Update 메서드를 코드를 추가 합니다. 다음 예제에서는 SQL Server에 대 한 AdventureWorks 예제 데이터베이스에 있는 연락처에 대 한 정보를 업데이트합니다.  
  
    > [!NOTE]  
    >  값을 바꿉니다는 `ServerName` 필드와 사용자 서버의 이름입니다.  
  
     [!code-csharp[SP_BDC#5](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#5)]
     [!code-vb[SP_BDC#5](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#5)]  
  
## <a name="see-also"></a>참고자료
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: 특정 Finder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수를 추가 합니다.](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
 