---
title: 비즈니스 데이터 연결 모델 디자인 | Microsoft Docs
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
- BDC [SharePoint development in Visual Studio], designing a model
- Business Data Connectivity service [SharePoint development in Visual Studio], designing a model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 6f34a754562674aacf989c294ff2662ca4f8f28f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="designing-a-business-data-connectivity-model"></a>비즈니스 데이터 연결 모델 디자인
  모델 파일에 엔터티 및 메서드를 추가 하 여 BDC 비즈니스 데이터 연결 () 서비스에 대 한 모델을 개발할 수 있습니다. 엔터티는 데이터 필드의 컬렉션을 설명 합니다. 예를 들어 엔터티는 데이터베이스의 테이블을 나타낼 수 있습니다. 메서드 추가, 삭제 또는 엔터티를 나타내는 데이터를 업데이트 하는 등의 작업을 수행 합니다. 자세한 내용은 참조 [를 SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)합니다.  
  
## <a name="adding-entities"></a>엔터티 추가  
 끌거나 복사 하 여 엔터티를 추가할 수는 **엔터티** Visual Studio에서 **도구 상자** BDC 디자이너에 있습니다. 자세한 내용은 참조 [하는 방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)합니다.  
  
 클래스에서 엔터티의 필드를 정의 합니다. 예를 들어 라는 필드를 추가할 수 있습니다 `Address` 에 `Customer` 클래스입니다. 프로젝트에 새 클래스를 추가 하거나 개체 관계형 디자이너 (O/R 디자이너)와 같은 다른 도구를 사용 하 여 만든 기존 클래스를 사용 합니다. 엔터티의 이름 및 엔터티를 나타내는 클래스의 이름에 맞게 없는 합니다. 모델의 메서드를 정의 하는 경우 엔터티 클래스를 연결 합니다.  
  
## <a name="adding-methods"></a>메서드 추가  
 BDC 서비스에서 사용자가 보기, 추가, 업데이트 또는 목록이 나 모델을 기반으로 하는 웹 파트에 정보를 삭제 하는 경우 모델의 메서드를 호출 합니다. 사용자가 수행할 수 있는 각 작업에 대 한 모델에 메서드를 추가 해야 합니다. 5 가지 기본 메서드 형식 중 하나를 선택 하 여 메서드를 만들기는 **BDC 메서드 세부 정보** 창. 다음 표에서 BDC 모델의 다섯 가지 기본적인 방법을 설명합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|찾기|엔터티 인스턴스의 컬렉션을 반환합니다. 목록이 나 웹 파트는 사용자가 열 때 호출 됩니다. 자세한 내용은 참조 [하는 방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)합니다.|  
|SpecificFinder|특정 엔터티 인스턴스를 반환합니다. 사용자 목록에 있는 특정 항목의 세부 정보를 볼 때 호출 됩니다. 자세한 내용은 참조 [하는 방법: 특정 Finder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)합니다.|  
|Creator|엔터티 데이터 원본에 새 데이터를 추가합니다. 사용자가 선택할 때 호출 된 **새 항목** 모델을 기반으로 하는 목록의 리본에 단추입니다. 자세한 내용은 참조 [하는 방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)합니다.|  
|Updater|목록에서 데이터를 수정합니다. 사용자가 목록에 대 한 정보를 업데이트할 때 호출 됩니다. 자세한 내용은 참조 [하는 방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)합니다.|  
|Deleter|데이터를 제거합니다. 사용자가 목록에서 항목을 삭제할 때 호출 됩니다. 자세한 내용은 참조 [하는 방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)합니다.|  
  
## <a name="defining-method-parameters"></a>메서드 매개 변수 정의  
 메서드를 만들 때 Visual Studio 메서드 형식에 대 한 적합 한 입력 및 출력 매개 변수를 추가 합니다. 이러한 매개 변수는 자리 표시자 일 뿐입니다. 대부분의 경우 전달 하거나 올바른 형식의 데이터를 반환할 수 있도록 매개 변수를 수정 해야 합니다. 예를 들어 기본적으로 찾기 메서드는 문자열을 반환합니다. 대부분의 경우에서 엔터티 컬렉션 반환 되도록 Finder 메서드의 반환 매개 변수를 수정 하려고 합니다. 매개 변수의 형식 설명자를 수정 하 여 수행할 수 있습니다. 형식 설명자는 매개 변수의 데이터 형식을 설명 하는 특성의 컬렉션입니다. 자세한 내용은 참조 [하는 방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)합니다.  
  
 Visual Studio를 사용 하면 모델에 대 한 매개 변수 간의 형식 설명자를 복사할 수 있습니다. 예를 들어 명명 된 형식 설명자를 정의할 수 있습니다 `CustomerTD` 의 반환 매개 변수는 `GetCustomer` 메서드. 복사할 수 있습니다는 `CustomerTD` 형식 설명자에는 **BDC 탐색기**, 복사한 후 해당 형식 설명자의 입력 매개 변수는 `CreateCustomer` 메서드. 이렇게 하면 동일한 형식 설명자를 두 번 이상 정의할 필요가 없습니다.  
  
##  <a name="MethodInstances"></a> 메서드 인스턴스  
 메서드를 만들 때 Visual Studio 기본 메서드 인스턴스를 추가 합니다. 메서드 인스턴스는 메서드, 및 매개 변수에 대해 기본 값에 대 한 참조입니다. 단일 메서드는 여러 메서드 인스턴스가 있을 수 있습니다. 각 인스턴스 메서드 시그니처 조합과 기본값 집합이 됩니다. 자세한 내용은 참조 [하는 방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)합니다.  
  
 프로젝트를 실행 하면 메서드 인스턴스는 SharePoint 목록 위의 드롭다운 목록에 나타납니다. 사용자는 메서드 인스턴스를 선택하여 데이터를 볼 수 있습니다.  
  
 메서드 인스턴스의 기본값에 추가 하려면 모델의 XML을 직접 수정 해야 합니다. 자세한 내용은 참조 [DefaultValue](http://go.microsoft.com/fwlink/?LinkID=169279)합니다.  
  
## <a name="adding-filter-descriptors"></a>필터 설명자 추가  
 모델의 소비자는 몇 가지 조건과 일치 하는 엔터티의 인스턴스를 검색 원할 수 있습니다. 이 기능을 활성화 하려면 메서드에 필터 설명자를 추가할 수 있습니다. 필터 설명자 실행 되기 전에 값을 메서드에 전달 하 여 메서드 결과 집합을 필터링 할 모델 소비자를 사용 합니다. 자세한 내용은 참조 [하는 방법: 제한 인스턴스를 외부 시스템에서 작업 필터 매개 변수 추가](http://go.microsoft.com/fwlink/?LinkID=169267)합니다.  
  
 SharePoint은 사용자가 필터 값을 제공할 수 있도록 여러 기능을 제공 합니다. 예를 들어 비즈니스 데이터 웹 파트를 필터 입력란을 제공합니다. 사용자는 텍스트 상자에 값을 입력하여 목록에서 데이터를 제한할 수 있습니다. 메서드에 필터 설명자 추가 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: Finder 메서드에 필터 설명자 추가](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)합니다.  
  
### <a name="filter-descriptor-properties"></a>필터 설명자 속성  
 값을 설정 해야 합니다는 **관련 형식 설명자**, **이름**, 및 **형식** 필터 설명자의 속성입니다. 다른 모든 속성은 선택 사항입니다.  
  
 **관련 형식 설명자** 속성과 입력된 매개 변수 필터 설명자 관련이 있습니다. 필터 값을 제공 하는 사용자, BDC 서비스는 해당 값 입력된 매개 변수를 사용 하 여 메서드에 전달 합니다.  
  
 **형식** 속성 필터링에 사용 하려는 패턴에 설명 합니다. SharePoint, 선택한 필터링 패턴 사용자 인터페이스 (UI)에 표시 되는 텍스트를 영향을 줍니다. 비교 연산자 필터링 패턴 텍스트에 대 한 예를 들어 **같으면** 컨트롤로 비즈니스 데이터 웹 파트 위에 나타납니다. 필터링 각 패턴에 대 한 자세한 내용은 참조 [종류의 필터에서 지 원하는 BDC](http://go.microsoft.com/fwlink/?LinkId=169287)합니다.  
  
 필터 설명자의 속성에 대 한 자세한 내용은 참조 [FilterDescriptor](http://go.microsoft.com/fwlink/?LinkID=169280)합니다.  
  
### <a name="providing-default-values"></a>기본값을 제공  
 경우에 따라 사용자는 필터 값을 제공 하지 수도 있습니다. 메서드 인스턴스의 기본값을 추가 하거나 메서드 코드에서 기본값을 설정 하 여 기본값을 제공할 수 있습니다. 메서드 인스턴스에 기본 값을 추가 하는 방법에 대 한 자세한 내용은 참조 [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282)합니다. 메서드 코드에서의 입력된 매개 변수 기본값을 설정 하는 방법의 예제를 보려면 [하는 방법: Finder 메서드에 필터 설명자 추가](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)합니다.  
  
## <a name="validating-the-model"></a>모델 유효성 검사  
 개발 하는 동안 모델을 확인할 수 있습니다. Visual Studio에서 예상 대로 작동 모델을 방해할 수 있는 문제를 식별 합니다. 이러한 문제는 Visual Studio에 나타나는 **오류 목록**합니다.  
  
 BDC 디자이너에 대 한 바로 가기 메뉴를 열고 선택 하 여 모델을 확인할 수 있습니다 **유효성 검사**합니다. 모델 오류를 포함 하는 경우에 표시 됩니다는 **오류 목록**합니다. 목록에서 오류를 두 번 클릭하여 오류가 포함된 코드로 빠르게 커서를 이동할 수 있습니다. 또는 F8 키 또는 Shift+F8 키를 반복적으로 선택하여 목록의 오류에서 앞뒤로 이동할 수 있습니다.  
  
 어떤 방식으로든에서 모델의 규칙을 위반 하는 유효성 검사 오류가 발생할 수 있습니다. 예를 들어 경우는 **IsCollection** 형식 설명자의 속성이로 설정 되어 **true**, 하지만 없는 자식 형식 설명자, 유효성 검사 오류가 나타납니다. Visual Studio에 표시 되는 몇 가지 오류를 이해 하는 BDC 모델의 규칙을 참조 해야 할 수 있습니다 **오류 목록**합니다. BDC 모델의 규칙에 대 한 자세한 내용은 참조 [BDCMetadata 스키마](http://go.microsoft.com/fwlink/?LinkID=169275)합니다.  
  
## <a name="debugging-the-solution-that-contains-the-model"></a>모델을 포함 하는 솔루션 디버깅  
 Visual Studio의 모든 코드를 디버깅할 때 코드를 디버깅할 수 있습니다. 코드를 디버깅 하려면 코드에서 임의의 위치에 중단점을 설정 하 고 디버거를 시작 합니다. Visual Studio는 SharePoint 사이트를 엽니다. SharePoint 목록 또는 비즈니스 데이터를 사용 하는 웹 파트를 만듭니다. 그런 다음 코드를 단계별로 실행할 수 있습니다. SharePoint 프로젝트를 디버깅 하는 방법에 대 한 자세한 내용은 참조 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)합니다.  
  
 프로젝트에 추가 하는 사용자 지정 어셈블리에서 코드를 디버깅할 수 있습니다. 그러나 사용자 지정 어셈블리에 코드를 디버깅 하려면 솔루션 패키지에 어셈블리를 추가 해야 있습니다. 자세한 내용은 참조 [하는 방법: 추가 어셈블리 추가 및 제거](../sharepoint/how-to-add-and-remove-additional-assemblies.md)합니다.  
  
 사용자 지정 어셈블리 프로젝트를 추가 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: BDC 기능에 사용자 지정 어셈블리 포함](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)합니다.  
  
### <a name="configuring-bdc-security"></a>BDC 보안 구성  
 솔루션을 디버그할 수 있으려면 SharePoint의 보안 설정을 수정 해야 합니다. 이러한 설정을 수정 하려면 비즈니스 데이터 연결 서비스 응용 프로그램을 SharePoint 2010 중앙 관리 웹 사이트에서 엽니다. 에 **메타 데이터 저장소 사용 권한 설정** 대화 상자에서 사용자 계정을 추가 하 고 다음 옵션 중 하나를 선택 합니다.  
  
|작업|옵션|  
|----------|------------|  
|BDC 서비스에 모델을 배포 합니다.|편집|  
|만들려면 목록 및 사용 하 여 웹 파트를 외부 콘텐츠 형식 모델에 (엔터티)입니다.|클라이언트에서 선택 가능|  
|만들기, 읽기, 업데이트 및 엔터티 데이터를 삭제 하려면|실행|  
  
 이러한 설정에 대 한 자세한 내용은 참조 [비즈니스 데이터 연결 서비스 관리](http://go.microsoft.com/fwlink/?LinkID=178883)합니다.  
  
 또한 개별 모델 또는 외부 콘텐츠 형식에 대 한 보안 권한을 설정할 수 있습니다. 모델의 보안 권한을 설정 하는 방법에 대 한 자세한 내용은 참조 [BDC 모델 관리](http://go.microsoft.com/fwlink/?LinkID=178884)합니다. 외부 콘텐츠 형식의 보안 권한을 설정 하는 방법에 대 한 자세한 내용은 참조 [외부 콘텐츠 형식 관리](http://go.microsoft.com/fwlink/?LinkID=178885)합니다.  
  
> [!NOTE]  
>  이러한 설정을 사용 하 여 로컬 SharePoint 서버에 솔루션을 디버깅 합니다. 프로덕션 SharePoint 서버에서 BDC 관련 보안 설정을 구성 하는 방법에 대 한 자세한 내용은 참조 [비즈니스 데이터 연결 서비스 보안 개요](http://go.microsoft.com/fwlink/?LinkID=178886)합니다.  
  
### <a name="retracting-models-that-become-corrupt"></a>손상 된 모델 제거  
 디버거를 처음 시작하면 Visual Studio에서 전체 모델을 SharePoint에 배포합니다. 이후 언제 각 지에 대 한 Visual Studio는 배포 간에 변경으로 SharePoint에서 모델을 업데이트 합니다.  
  
 SharePoint에서 모델을 완전히 제거 하려면 Visual Studio 보여 주려는 경우 있을 수 있습니다. 예를 들어 모델을 손상 될 수 있습니다.  SharePoint에 모델을 다시 배포 하려면 설정는 **증분 업데이트** 모델의 속성 **False**, 한 다음 디버거를 시작 합니다. **증분 업데이트** 에 속성이 표시는 **속성** 창에 모델을 나타내는 노드를 선택할 때의 **BDC 탐색기**합니다. 기본적으로 모델의 이름이 **BdcModel1**합니다.  
  
### <a name="changing-identifier-names-of-entities-in-the-model"></a>모델의 엔터티 식별자 이름 변경  
 모델을 배포한 후 식별자의 이름을 변경 하면 배포 오류가 발생할 수 있습니다. 설정 하 여이 오류를 해결할 수 없는 **증분 업데이트** 모델의 속성 **False**합니다. 모델을 수동으로 제거 하 고 솔루션을 다시 배포 해야 합니다. 자세한 내용은 참조 [SharePoint 솔루션 문제 해결](../sharepoint/troubleshooting-sharepoint-solutions.md)합니다. 설정 하 여이 오류를 방지할 수는 **증분 업데이트** 속성을 **False** 모델을 처음 배포 하기 전에.  
  
## <a name="locating-documentation-for-bdc-model-elements"></a>BDC 모델 요소에 대 한 설명서 찾기  
 각 엔터티에 대 한 모델에는 XML 요소를 추가 하는 visual Studio 메서드나를 만들면 다른 항목입니다. 요소 특성에 속성으로 표시 된 **속성** 창. 요소와 모델을 디자인할 때 Visual Studio에서 생성 하는 특성에 대 한 정보를 참조 하십시오. [BDCMetadata 스키마](http://go.microsoft.com/fwlink/?LinkID=169275)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)|BDC에 대 한 모델을 시각적으로 디자인 하는 데 사용할 수 있는 도구에 설명 합니다.|  
|[방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)|외부 콘텐츠 형식 또는 엔터티 모델에 추가 하는 방법을 보여 줍니다.|  
|[방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)|목록이 나 웹 파트의 엔터티 목록을 볼 수 있도록 하는 메서드를 추가 하는 방법을 보여 줍니다.|  
|[방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)|사용자가 특정 엔터티의 세부 정보를 볼 수 있는 메서드를 추가 하는 방법을 보여 줍니다.|  
|[방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)|사용자가 직접 목록이 나 웹 파트에서 데이터 원본에 레코드를 추가할 수 있는 메서드를 추가 하는 방법을 보여 줍니다.|  
|[방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)|사용자가 목록의 사용자 인터페이스 (UI) 또는 웹 파트에서 옵션을 사용 하 여 데이터 원본에서 데이터를 제거할 수 있는 메서드를 추가 하는 방법을 보여 줍니다.|  
|[방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)|목록이 나 웹 파트에서 직접 데이터 원본에서 데이터 레코드를 변경할 수 있도록 하는 메서드를 추가 하는 방법을 보여 줍니다.|  
|[방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)|Visual Studio에서 메서드 세부 정보 창을 사용 하 여 입력 및 반환 매개 변수는 메서드를 추가 하는 방법을 보여 줍니다.|  
|[방법: 매개 변수의 형식 설명자 정의](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)|모델의 매개 변수 데이터 형식을 정의 하는 방법을 보여 줍니다.|  
|[방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)|BDC가 실행 하는 방법의 인스턴스를 만드는 방법을 보여 줍니다.|  
|[방법: Finder 메서드에 필터 설명자 추가](../sharepoint/how-to-add-a-filter-descriptor-to-a-finder-method.md)|사용자가 Finder 메서드에 의해 반환 되는 인스턴스의 수를 제한할 수 있도록 하는 방법을 보여 줍니다.|  
|[엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)|모델의 엔터티 간 관계를 정의 하는 방법을 설명 합니다. 비즈니스 데이터 웹 파트, 외부 목록 및 사용자 지정 응용 프로그램 사용자 인터페이스 (UI)에서 이러한 데이터 관계를 표시할 수 있습니다.|  
|[방법: 엔터티 간 연결 만들기](../sharepoint/how-to-create-an-association-between-entities.md)|모델의 엔터티 간 관계를 정의 하는 방법을 보여 줍니다.|  
|[연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)|만들고 SharePoint 외부 목록에 있는 연락처를 표시 하는 모델을 테스트 하는 방법을 보여 주는 단계별 지침을 제공 합니다.|  
|[SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)|만들기 및 BDC 서비스에 대 한 모델 디자인에 대 한 개요를 제공 합니다.|  
  
  