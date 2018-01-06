---
title: "방법: 특정 Finder 메서드 추가 | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], Specific Finder
- BDC [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], get an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], Specific Finder
- Business Data Connectivity service [SharePoint development in Visual Studio], get an entity
ms.assetid: 7bbc5986-2828-4755-96fa-9f1dc0f8dc75
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6a5dbff1d4a4c739ce8ecab0807e2d74c62f999e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-specific-finder-method"></a>방법: SpecificFinder 메서드 추가
  단일 엔터티 인스턴스를 만들어 반환할 수 있습니다는 *Specificfinder* 메서드. BDC 비즈니스 데이터 연결 () 서비스는 사용자가 비즈니스 데이터 웹 파트 또는 외부 목록에서 엔터티를 선택할 때 특정 Finder 메서드를 실행 합니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
### <a name="to-create-a-specific-finder-method"></a>특정 Finder 메서드를 만들려면  
  
1.  BDC 디자이너에서 엔터티를 선택 합니다.  
  
     Visual Studio에서 BDC 디자이너에 엔터티를 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)합니다.  
  
2.  메뉴 모음에서 **보기**, **다른 창**, **BDC 메서드 세부 정보**합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다. 해당 창에 대 한 자세한 내용은 참조 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)합니다.  
  
3.  에 **메서드 추가** 목록에서 선택 **Specificfinder 메서드 만들기**합니다.  
  
     Visual Studio는 모델에 다음과 같은 요소를 추가합니다. 이러한 요소에 표시 된 **BDC 메서드 세부 정보** 창.  
  
    -   메서드  
  
    -   메서드에 대 한 입력된 매개 변수입니다.  
  
    -   메서드에 대 한 반환 매개 변수입니다.  
  
    -   각 매개 변수에 대해 형식 설명자입니다.  
  
    -   메서드에 대 한 메서드 인스턴스입니다.  
  
     자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
4.  Visual Studio를 열고 **속성** 창.  
  
5.  엔터티 형식 설명자로 반환 매개 변수의 형식 설명자를 구성 합니다. 엔터티 형식 설명자를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)합니다.  
  
    > [!NOTE]  
    >  Finder 메서드는 엔터티를 추가한 경우이 단계를 수행할 필요가 없습니다. Visual Studio에서는 Finder 메서드에 정의 된 형식 설명자를 사용 합니다.  
  
    > [!NOTE]  
    >  엔터티 형식의 식별자 필드 자동으로 생성 되는 데이터베이스 테이블에 있는 필드를 나타내는 경우 설정의 **읽기 전용** 속성 식별자 필드의 **True**합니다.  
  
6.  에 **메서드 세부 정보** 창 메서드의 메서드 인스턴스를 선택 합니다.  
  
7.  에 **속성 창**설정는 **반환 매개 변수 이름** 속성을 반환 매개 변수는 메서드의 이름입니다. 메서드 인스턴스 속성에 대 한 자세한 내용은 참조 [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282)합니다.  
  
8.  **솔루션 탐색기**, 엔터티에 대해 생성 된 서비스 코드 파일의 바로 가기 메뉴를 열고 선택한 후 **코드 보기**합니다.  
  
     엔터티 서비스 코드 파일에는 코드 편집기에서 열립니다. 엔터티 서비스 코드 파일에 대 한 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
9. 특정 Finder 메서드에 코드를 추가 합니다. 이 코드는 다음 작업을 수행합니다.  
  
    -   데이터 원본에서 레코드를 검색합니다.  
  
    -   BDC 서비스에 엔터티를 반환합니다.  
  
     다음 예제에서는 SQL Server에 대 한 AdventureWorks 예제 데이터베이스에서 연락처를 반환합니다.  
  
    > [!NOTE]  
    >  값을 바꿉니다는 `ServerName` 필드와 사용자 서버의 이름입니다.  
  
     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수를 추가 합니다.](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
  