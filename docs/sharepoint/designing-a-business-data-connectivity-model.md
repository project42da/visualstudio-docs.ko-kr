---
title: "비즈니스 데이터 연결 모델 디자인"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 모델 디자인"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 모델 디자인"
ms.assetid: 19cad8cf-8a82-4000-84cf-1e5aff54e5af
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# 비즈니스 데이터 연결 모델 디자인
  엔터티와 메서드를 모델 파일에 추가하여 BDC\(비즈니스 데이터 연결\) 서비스의 모델을 개발할 수 있습니다.  엔터티는 데이터 필드의 컬렉션을 설명합니다.  예를 들어 엔터티는 데이터베이스의 테이블을 나타낼 수 있습니다.  메서드는 엔터티가 나타내는 데이터의 추가, 삭제 또는 업데이트와 같은 작업을 수행합니다.  자세한 내용은 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)을 참조하십시오.  
  
## 엔터티 추가  
 Visual Studio **도구 상자** 의 **엔터티** 를 BDC 디자이너로 끌어오거나 복사하여 엔터티를 추가할 수 있습니다.  자세한 내용은 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)을 참조하십시오.  
  
 클래스에 엔터티의 필드를 정의합니다.  예를 들어, `Address`라는 필드를 `Customer` 클래스에 추가할 수 있습니다.  프로젝트에 새 클래스를 추가하거나 O\/R 디자이너\(개체 관계형 디자이너\)와 같은 다른 도구를 사용하여 만든 기존 클래스를 사용할 수 있습니다.  엔터티를 나타내는 클래스의 이름과 엔터티의 이름은 일치하지 않아도 됩니다.  모델에서 메서드를 정의할 때 클래스를 엔터티와 관련시킵니다.  
  
## 메서드 추가  
 BDC 서비스는 사용자가 모델을 기반으로 하는 목록이나 웹 파트의 정보를 보거나, 추가하거나, 업데이트하거나, 삭제할 때 모델에서 메서드를 호출합니다.  사용자가 수행할 수 있는 각 작업에 대한 메서드를 모델에 추가해야 합니다.  **BDC 메서드 세부 정보** 창에서 5가지 기본 메서드 형식 중 하나를 선택하여 메서드를 만듭니다.  다음 표에서는 BDC 모델의 5가지 기본 메서드에 대해 설명합니다.  
  
|메서드|설명|  
|---------|--------|  
|Finder|엔터티 인스턴스의 컬렉션을 반환합니다.  사용자가 목록이나 웹 파트를 열면 호출됩니다.  자세한 내용은 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)을 참조하십시오.|  
|SpecificFinder|특정 엔터티 인스턴스를 반환합니다.  사용자가 목록에서 특정 항목의 세부 정보를 보면 호출됩니다.  자세한 내용은 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)을 참조하십시오.|  
|Creator|엔터티의 데이터 소스에 새 데이터를 추가합니다.  사용자가 모델을 기반으로 하는 목록의 리본에서 **새 항목** 버튼을 선택하면 호출됩니다.  자세한 내용은 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)을 참조하십시오.|  
|Updater|목록에서 데이터를 수정합니다.  사용자가 목록에서 정보를 업데이트하면 호출됩니다.  자세한 내용은 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)을 참조하십시오.|  
|Deleter|데이터를 제거합니다.  사용자가 목록에서 항목을 삭제하면 호출됩니다.  자세한 내용은 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)을 참조하십시오.|  
  
## 메서드 매개 변수 정의  
 메서드를 만들면 Visual Studio에서는 메서드 형식에 적합한 입력 및 출력 매개 변수를 추가합니다.  이러한 매개 변수는 자리 표시자일 뿐입니다.  대부분의 경우 올바른 형식의 데이터를 전달하거나 반환하도록 매개 변수를 수정해야 합니다.  예를 들어, 기본적으로 Finder 메서드는 문자열을 반환합니다.  대부분의 경우 엔터티의 컬렉션을 반환하도록 Finder 메서드의 반환 매개 변수를 수정하려고 합니다.  매개 변수의 형식 설명자를 수정하여 이 작업을 수행할 수 있습니다.  형식 설명자는 매개 변수의 데이터 형식을 설명하는 특성의 컬렉션입니다.  자세한 내용은 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)을 참조하십시오.  
  
 Visual Studio에서는 모델의 매개 변수 간에 형식 설명자를 복사할 수 있습니다.  예를 들어, `GetCustomer` 메서드의 반환 매개 변수에 대해 `CustomerTD`라는 형식 설명자를 정의할 수 있습니다.  **BDC 탐색기**에서 `CustomerTD` 형식 설명자를 복사한 다음 `CreateCustomer` 메서드의 입력 매개 변수에 붙여 넣을 수 있습니다.  이렇게 하면 동일한 형식 설명자를 두 번 이상 정의할 필요가 없습니다.  
  
##  <a name="MethodInstances"></a> 메서드 인스턴스  
 메서드를 만들면 Visual Studio에서는 기본 메서드 인스턴스를 추가합니다.  메서드 인스턴스는 메서드에 대한 참조와 매개 변수의 기본값으로 구성됩니다.  한 메서드에는 여러 메서드 인스턴스가 있을 수 있습니다.  각 인스턴스는 메서드 서명과 기본값 집합의 조합입니다.  자세한 내용은 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)을 참조하십시오.  
  
 프로젝트를 실행하면 메서드 인스턴스가 SharePoint 목록 위의 드롭다운 목록에 표시됩니다.  사용자는 메서드 인스턴스를 선택하여 데이터를 볼 수 있습니다.  
  
 메서드 인스턴스에 기본값을 추가하려면 모델의 XML을 직접 수정해야 합니다.  자세한 내용은  을 참조하십시오.  
  
## 필터 설명자 추가  
 모델의 소비자가 일부 조건과 일치하는 엔터티의 인스턴스를 검색하려고 할 수 있습니다.  이 기능을 사용하도록 설정하기 위해 필터 설명자를 메서드에 추가할 수 있습니다.  필터 설명자를 사용하면 모델 소비자가 메서드가 실행되기 전에 메서드에 값을 전달하여 메서드 결과 집합을 필터링할 수 있습니다.  자세한 내용은 [외부 시스템에서 인스턴스를 제한하기 위한 작업에 필터 매개 변수를 추가하는 방법](http://go.microsoft.com/fwlink/?LinkID=169267).  
  
 SharePoint에서는 사용자가 필터 값을 제공할 수 있도록 하는 몇 가지 기능을 제공합니다.  예를 들어, 비즈니스 데이터 웹 파트는 필터 텍스트 상자를 제공합니다.  사용자는 텍스트 상자에 값을 입력하여 목록에서 데이터를 제한할 수 있습니다.  메서드에 필터 설명자를 추가하는 방법에 대한 자세한 내용은 [방법: Finder 메서드에 필터 설명자 추가](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)를 참조하십시오.  
  
### 필터 설명자 속성  
 필터 설명자의 **연결된 TypeDescriptor**, **이름** 및 **형식** 속성 값을 설정해야 합니다.  다른 모든 속성은 선택적 요소입니다.  
  
 **연결된 TypeDescriptor** 속성은 필터 설명자를 입력 매개 변수와 관련시킵니다.  사용자가 필터 값을 제공하면 BDC 서비스는 입력 매개 변수를 사용하여 메서드에 해당 값을 전달합니다.  
  
 **형식** 속성은 사용할 필터링 패턴을 설명합니다.  SharePoint에서 선택하는 필터링 패턴은 UI\(사용자 인터페이스\)에 나타나는 텍스트에 영향을 미칩니다.  예를 들어, 비교 연산자 필터링 패턴의 경우 **\=** 텍스트가 비즈니스 데이터 웹 파트 위에 컨트롤로 나타납니다.  각 필터링 패턴에 대한 자세한 내용은 [BDC에 의해 지원되는 필터의 유형](http://go.microsoft.com/fwlink/?LinkId=169287) 을 참조하십시오.  
  
 필터 설명자의 속성에 대한 자세한 내용은 [FilterDescriptor](http://go.microsoft.com/fwlink/?LinkID=169280) 을 참조하십시오.  
  
### 기본값 제공  
 사용자가 필터 값을 제공하지 않는 경우도 있습니다.  메서드 인스턴스에 기본값을 추가하거나 메서드 코드에서 기본값을 설정하여 기본값을 제공할 수 있습니다.  메서드 인스턴스에 기본값을 추가 하는 방법에 대한 자세한 내용은 [메서드 인스턴스](http://go.microsoft.com/fwlink/?LinkID=169282) 를 참조하십시오.  메서드 코드에서 입력 매개 변수의 기본값을 설정하는 방법에 대한 예제는 [방법: Finder 메서드에 필터 설명자 추가](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)를 참조하십시오.  
  
## 모델 유효성 검사  
 개발하는 동안 모델의 유효성을 검사할 수 있습니다.  Visual Studio에서는 모델이 예상대로 동작하지 못하게 할 수 있는 문제를 식별합니다.  이러한 문제는 Visual Studio **오류 목록**에 나타납니다.  
  
 BDC 디자이너에 대한 바로 가기 메뉴를 열고 **유효성 검사**를 선택하여 모델의 유효성 검사를 할 수 있습니다..  모델에 모든 오류가 포함 된 경우, **오류 목록** 에 표시됩니다.  목록에서 오류를 두 번 클릭하여 오류가 있는 코드로 빠르게 커서를 이동할 수 있습니다.  대신, 목록의 에러에서 F8 키 또는 Shift\+F8 키를 반복적으로 눌러 앞으로 가기 또는 뒤로 가기를 실행할 수 있습니다.  
  
 유효성 검사 오류는 모델의 규칙이 위반되었을 때 발생할 수 있습니다.  예를 들어, 형식 설명자의 **IsCollection** 속성이 **true**로 설정되었지만 자식 형식 설명자가 없는 경우 유효성 검사 오류가 나타납니다.  Visual Studio **오류 목록**에 나타나는 일부 오류를 이해하려면 BDC 모델의 규칙을 참조해야 할 수 있습니다.  BDC 모델의 규칙에 대한 자세한 내용은 [BDCMetadata 스키마](http://go.microsoft.com/fwlink/?LinkID=169275) 를 참조하십시오.  
  
## 모델을 포함하는 솔루션 디버깅  
 Visual Studio에서 코드를 디버깅하듯이 사용자 코드를 디버깅할 수 있습니다.  코드를 디버깅하려면 코드에서 원하는 위치에 중단점을 설정한 다음 디버거를 시작합니다.  Visual Studio에서는 SharePoint 사이트를 엽니다.  SharePoint에서 비즈니스 데이터를 사용하는 웹 파트나 목록을 만듭니다.  그런 다음 단계별로 코드를 실행할 수 있습니다.  SharePoint 프로젝트 디버깅에 대한 자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)을 참조하십시오.  
  
 또한 프로젝트에 추가한 사용자 지정 어셈블리의 코드를 디버깅할 수 있습니다.  그러나 사용자 지정 어셈블리의 코드를 디버깅하려면 해당 어셈블리를 솔루션 패키지에 추가해야 합니다.  자세한 내용은 [방법: 추가 어셈블리 추가 및 제거](../sharepoint/how-to-add-and-remove-additional-assemblies.md)을 참조하십시오.  
  
 프로젝트에 사용자 지정 어셈블리를 추가하는 방법에 대한 내용은 [방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)을 참조하십시오.  
  
### BDC 보안 구성  
 솔루션을 디버깅하려면 먼저 SharePoint에서 보안 설정을 수정해야 할 수도 있습니다.  이러한 설정을 수정하려면 SharePoint 2010 중앙 관리 웹 사이트에서 비즈니스 데이터 연결 서비스 응용 프로그램을 엽니다.  **메타데이터 저장소 사용 권한 설정** 대화 상자에서 사용자 계정을 추가하고 다음 옵션 중 하나를 선택합니다.  
  
|Task|옵션|  
|----------|--------|  
|BDC 서비스에 모델을 배포하려면|Edit|  
|모델에서 외부 콘텐츠 형식\(엔터티\)을 사용하여 목록과 웹 파트를 만들려면|클라이언트에서 선택 가능|  
|엔터티 데이터를 만들고, 읽고, 업데이트하고, 삭제하려면|Execute|  
  
 이러한 설정에 대한 자세한 내용은 [비즈니스 데이터 연결 서비스 관리](http://go.microsoft.com/fwlink/?LinkID=178883) 를 참조하십시오.  
  
 개별 모델이나 외부 콘텐츠 형식의 보안 권한도 설정할 수 있습니다.  모델의 보안 사용 권한을 설정하는 방법에 대한 자세한 내용은 [BDC 모델 관리](http://go.microsoft.com/fwlink/?LinkID=178884) 를 참조하십시오.  외부 콘텐츠 형식의 보안 권한을 설정하는 방법에 대한 자세한 내용은 [외부 콘텐츠 형식 관리](http://go.microsoft.com/fwlink/?LinkID=178885) 을 참조하십시오.  
  
> [!NOTE]  
>  로컬 SharePoint 서버에서 솔루션을 디버깅하려면 이러한 설정을 사용하십시오.  프로덕션 SharePoint 서버에서 BDC 관련 보안 설정을 구성하는 방법에 대한 자세한 내용은 [비지니스 데이터 연결 서비스 보안 개요](http://go.microsoft.com/fwlink/?LinkID=178886) 를 참조하십시오.  
  
### 손상된 모델 취소  
 디버거를 처음 시작하면 Visual Studio에서는 전체 모델을 SharePoint에 배포합니다.  이후에 디버거를 시작할 때마다 Visual Studio에서는 배포 간에 변경하는 내용으로 SharePoint의 모델을 업데이트합니다.  
  
 경우에 따라 Visual Studio에서 SharePoint의 모델을 완전히 취소하도록 할 수 있습니다.  예를 들어, 모델이 손상되었을 수 있습니다.  SharePoint에 모델을 다시 배포하려면 모델의 **증분 업데이트** 속성을 **False**로 설정한 다음 디버거를 시작합니다.  **BDC 탐색기**에서 모델을 나타내는 노드를 선택하면 **증분 업데이트** 속성이 **속성** 창에 표시됩니다.  기본적으로 모델의 이름은 **BdcModel1**입니다.  
  
### 모델에서 엔터티의 식별자 이름 변경  
 모델 배포 이후에 식별자 이름을 변경하면 배포 오류가 발생할 수 있습니다.  이 오류는 모델의 **증분 업데이트** 속성을 **False**로 설정하여 해결할 수 없습니다.  이 경우에는 모델을 수동으로 제거한 다음 솔루션을 다시 배포해야 합니다.  자세한 내용은 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)을 참조하십시오.  이 오류는 모델을 처음 배포하기 전에 **증분 업데이트** 속성을 **False**로 설정하여 방지할 수 있습니다.  
  
## BDC 모델 요소에 대한 설명서 찾기  
 Visual Studio에서는 사용자가 만드는 각 엔터티, 메서드 또는 기타 항목에 대한 XML 요소를 모델에 추가합니다.  요소 특성은 **속성** 창에 속성으로 표시됩니다.  모델을 디자인할 때 Visual Studio에서 생성하는 요소와 특성에 대한 자세한 내용은 [BDCMetadata Schema](http://go.microsoft.com/fwlink/?LinkID=169275) 를 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)|BDC의 모델을 시각적으로 디자인하는 데 사용할 수 있는 도구에 대해 설명합니다.|  
|[방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)|외부 콘텐츠 형식\(엔터티\)을 모델에 추가하는 방법을 보여 줍니다.|  
|[방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)|사용자가 목록이나 웹 파트의 엔터티 목록을 볼 수 있도록 하는 메서드를 추가하는 방법을 보여 줍니다.|  
|[방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)|사용자가 특정 엔터티의 세부 정보를 볼 수 있도록 하는 메서드를 추가하는 방법을 보여 줍니다.|  
|[방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)|사용자가 목록이나 웹 파트에서 직접 데이터 소스에 레코드를 추가할 수 있도록 하는 메서드를 추가하는 방법을 보여 줍니다.|  
|[방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)|사용자가 목록이나 웹 파트의 UI\(사용자 인터페이스\)에서 옵션을 사용하여 데이터 소스에서 데이터를 제거할 수 있도록 하는 메서드를 추가하는 방법을 보여 줍니다.|  
|[방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)|사용자가 목록이나 웹 파트에서 직접 데이터 소스의 데이터 레코드를 변경할 수 있도록 하는 메서드를 추가하는 방법을 보여 줍니다.|  
|[방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)|Visual Studio에서 메서드 세부 정보 창을 사용하여 입력 및 반환 매개 변수를 메서드에 추가하는 방법을 보여 줍니다.|  
|[How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)|모델에서 매개 변수 데이터 형식을 정의하는 방법을 보여 줍니다.|  
|[방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)|BDC가 실행하는 메서드의 인스턴스를 만드는 방법을 보여 줍니다.|  
|[방법: Finder 메서드에 필터 설명자 추가](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)|사용자가 Finder 메서드에서 반환하는 인스턴스의 수를 제한할 수 있도록 하는 방법을 보여 줍니다.|  
|[엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)|모델의 엔터티 간에 관계를 정의하는 방법에 대해 설명합니다.  비즈니스 데이터 웹 파트, 외부 목록 및 사용자 지정 응용 프로그램은 이러한 데이터 관계를 UI\(사용자 인터페이스\)에 표시할 수 있습니다.|  
|[방법: 엔터티 간 연결 만들기](../sharepoint/how-to-create-an-association-between-entities.md)|모델의 엔터티 간에 관계를 정의하는 방법을 보여 줍니다.|  
|[연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)|SharePoint 외부 목록의 연락처를 표시하는 모델을 만들고 테스트하는 방법을 보여 주는 단계별 지침을 제공합니다.|  
|[SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)|BDC 서비스의 모델을 만들고 디자인하는 방법에 대해 간략하게 설명합니다.|  
  
  