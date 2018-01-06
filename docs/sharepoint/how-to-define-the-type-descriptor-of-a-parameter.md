---
title: "방법: 매개 변수의 형식 설명자 정의 | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], type descriptor
- BDC [SharePoint development in Visual Studio], parameter types
- BDC [SharePoint development in Visual Studio], type descriptor
- Business Data Connectivity service [SharePoint development in Visual Studio], parameter types
ms.assetid: 7494559f-1567-4cbd-bde0-05a2ed288c3a
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 64d741146c0ee2421ab663f78601bfba8c373f86
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-the-type-descriptor-of-a-parameter"></a>방법: 매개 변수의 형식 설명자 정의
  형식 설명자는 매개 변수의 데이터 형식을 설명하는 속성을 포함합니다. 형식 설명자는 필드, 엔터티 또는 엔터티 컬렉션을 정의할 수 있습니다. 자세한 내용은 참조 [TypeDescriptor](http://msdn.microsoft.com/library/ms543392%28v=office.12%29.aspx)합니다.  
  
### <a name="to-define-the-type-descriptor-of-a-parameter"></a>매개 변수의 형식 설명자를 정의하려면  
  
1.  에 **BDC 메서드 세부 정보** 창에서 매개 변수의 형식 설명자를 선택 합니다.  
  
2.  메뉴 모음에서 **보기**, **속성 창**합니다.  
  
3.  에 **속성** 창에서 형식 설명자의 속성을 설정 합니다.  
  
     다음 절차에서는 형식 설명자를 필드, 엔터티 또는 엔터티 컬렉션으로 정의하는 방법을 설명합니다.  
  
### <a name="to-define-a-field"></a>필드를 정의하려면  
  
1.  에 **속성** 창의 설정는 **이름** 엔터티를 나타내는 형식에서 필드의 이름으로 형식 설명자의 속성 (예: **FirstName**).  
  
2.  옆의 목록에는 **TypeName** 속성을 적절 한 데이터 형식을 선택 (예를 들어 **Int32**).  
  
     기타 선택적 매개 변수에 대 한 정보를 참조 하십시오. [TypeDescriptor](http://msdn.microsoft.com/library/ms543392%28v=office.12%29.aspx)합니다.  
  
### <a name="to-define-an-entity"></a>엔터티를 정의하려면  
  
1.  에 **속성** 창의 설정는 **이름** 속성을 엔터티를 설명 하는 이름 (예: **연락처**).  
  
2.  설정의 **TypeName** 속성을 엔터티를 나타내는 형식의 정규화 된 이름입니다. 이 형식은 프로젝트의 클래스, 솔루션에서 참조하는 어셈블리에 정의된 형식 또는 BDC 개체 모델에 정의된 형식일 수 있습니다.  
  
    -   프로젝트의 클래스에 대해 아래쪽 화살표를 옆에 선택 된 **TypeName** 속성을 선택는 **현재 프로젝트** 프로젝트의 클래스를 선택 하 고, 나타나는 대화 상자에서 탭 합니다.  
  
         정규화된 이름에는 클래스의 네임스페이스 및 이름, LOB 시스템의 이름이 차례로 포함됩니다. 값을 설정 하는 다음 예제는 **TypeName** 프로젝트의 클래스에는 속성입니다.  
  
         `MyBDCNamespace.BdcModel1.Contact, BdcModel1`  
  
    -   솔루션의 어셈블리에 있는 형식인 경우 정규화된 이름에는 형식 이름, 어셈블리 이름, 버전 번호, 문화권 및 public 키 토큰이 포함됩니다.  
  
         값을 설정 하는 다음 예제는 **TypeName** 속성 솔루션에서 참조 하는 어셈블리에 정의 된 형식입니다.  
  
         `MyNamespace.Contact, myAssemblyName, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
    -   BDC 개체 모델에 정의된 형식인 경우 정규화된 이름에는 형식의 네임스페이스 및 이름이 포함됩니다.  
  
         값을 설정 하는 다음 예제는 **TypeName** 속성을 BDC 개체 모델의 형식입니다.  
  
         `Microsoft.BusinessData.Runtime.DynamicType`  
  
3.  에 **BDC 메서드 세부 정보** 창에서 형식 설명자에 대해 표시 되는 목록을 열고 한 다음 **편집**합니다.  
  
     **BDC 탐색기** 창이 열립니다.  
  
4.  에 **BDC 탐색기**를 형식 설명자의 바로 가기 메뉴를 열고 다음 선택 **형식 설명자 추가**합니다.  
  
     새 형식 설명자는 엔터티 형식 설명자에 자식으로 추가됩니다. 이 형식 설명자를 필드로 구성합니다.  
  
5.  4단계를 반복하여 엔터티의 각 필드에 대한 자식 형식 설명자를 추가합니다.  
  
### <a name="to-define-a-collection-of-entities"></a>엔터티 컬렉션을 정의하려면  
  
1.  에 **BDC 메서드 세부 정보** 창에서 원하는 매개 변수의 형식 설명자를 선택 합니다.  
  
2.  메뉴 모음에서 **보기**, **속성 창**합니다.  
  
3.  에 **속성** 창의 설정는 **이름** 속성을 엔터티를 설명 하는 이름 (예: **연락처**).  
  
4.  설정의 **IsCollection** 속성을 **True**합니다. 이는 이 형식 설명자가 엔터티 컬렉션임을 나타냅니다.  
  
5.  설정의 **TypeName** 속성에 대 한 참조를 포함 하는 문자열을는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 및 엔터티를 나타내는 형식의 정규화 된 이름입니다. 이 형식은 프로젝트의 클래스, 솔루션에서 참조하는 어셈블리에 정의된 형식 또는 BDC 개체 모델에 정의된 형식일 수 있습니다.  
  
    -   프로젝트의 클래스에 대해 아래쪽 화살표를 옆에 선택 된 **TypeName** 속성을 선택는 **현재 프로젝트** 프로젝트의 클래스를 선택 하 고, 나타나는 대화 상자에서 탭 합니다.  
  
         정규화된 이름에는 클래스의 네임스페이스 및 이름, LOB 시스템의 이름이 차례로 포함됩니다.  
  
         값을 설정 하는 다음 예제는 **TypeName** 속성을 프로젝트에 클래스의 컬렉션입니다.  
  
         `System.Collections.Generic.IEnumerable`1 [MyBDCNamespace.` ` BdcModel1.Contact, BdcModel1]'  
  
    -   솔루션의 어셈블리에 있는 형식인 경우 정규화된 이름에는 형식 이름, 어셈블리 이름, 버전 번호, 문화권 및 public 키 토큰이 포함됩니다.  
  
         값을 설정 하는 다음 예제는 **TypeName** 속성을 솔루션에서 참조 하는 어셈블리에 있는 형식의 컬렉션입니다.  
  
         `System.Collections.Generic.IEnumerable`1 [MyNamespace.Contact, myAssemblyName, 버전 = 4.0.0.0, Culture = neutral, PublicKeyToken = b77a5c561934e089]'  
  
    -   BDC 개체 모델에 정의된 형식인 경우 정규화된 이름에는 형식의 네임스페이스 및 이름만 포함됩니다.  
  
         값을 설정 하는 다음 예제는 **TypeName** 속성을 BDC 개체 모델에 정의 된 형식의 컬렉션입니다.  
  
         `System.Collections.Generic.IEnumerable`1 [Microsoft.BusinessData.Runtime.DynamicType]'  
  
6.  에 **BDC 메서드 세부 정보** 창에서 형식 설명자에 대해 표시 되는 목록을 열고 한 다음 **편집**합니다.  
  
     **BDC 탐색기** 창이 열립니다.  
  
7.  에 **BDC 탐색기**를 형식 설명자의 바로 가기 메뉴를 열고 다음 선택 **형식 설명자 추가**합니다.  
  
     새 형식 설명자는 컬렉션 형식 설명자에 자식으로 추가됩니다. 이 형식 설명자를 엔터티로 구성합니다.  
  
## <a name="see-also"></a>참고 항목  
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [방법: 메서드에 매개 변수를 추가 합니다.](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  