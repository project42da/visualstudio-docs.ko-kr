---
title: "&lt;파일&gt; 요소 (ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#file
- http://www.w3.org/2000/09/xmldsig#DigestValue
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <file> element [ClickOnce application manifest]
- manifests [ClickOnce], file element
ms.assetid: 56e3490c-eed5-4841-b1bf-eefe778b6ac9
caps.latest.revision: "24"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: f448b7455bcbe13b7257a58a0eafbadd1165b197
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ltfilegt-element-clickonce-application"></a>&lt;파일&gt; 요소 (ClickOnce 응용 프로그램)
다운로드 하 고 응용 프로그램에서 사용 하는 어셈블리 이외의 모든 파일을 식별 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<file  
    name  
    size  
    group  
    optional  
    writeableType  
>  
    <typelib  
        tlbid  
        version  
        helpdir  
        resourceid  
        flags  
    />  
    <comClass  
        clsid  
        description  
        threadingModel  
        tlbid  
        progid  
        miscStatus  
        miscStatusIcon  
        miscStatusContent  
        miscStatusDocPrint  
        miscStatusThumbnail  
    />  
    <comInterfaceExternalProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <comInterfaceProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <windowClass  
        versioned  
    />  
</file>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `file` 요소는 선택적입니다. 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 요소. 파일의 이름을 식별합니다.|  
|`size`|필수 요소. 파일의 바이트 단위로 크기를 지정 합니다.|  
|`group`|선택적 이며 if는 `optional` 특성이 지정 되지 않았거나로 설정 `false`; 경우 필수 `optional` 은 `true`합니다. 이 파일이 속한 그룹의 이름입니다. 이름, 즉 개발자가 선택한 모든 유니코드 문자열 값의 수 있으며 파일에서 요청 시 다운로드에 사용 되는 <xref:System.Deployment.Application.ApplicationDeployment> 클래스입니다.|  
|`optional`|선택 사항입니다. 이 파일을 다운로드는 응용 프로그램이 첫 번째 때 실행 또는 응용 프로그램이 필요에 따라 요청 될 때까지 파일 서버에만 상주 하 해야 하는지 여부를 지정 합니다. 경우 `false` 정의 되지 않은 파일이 다운로드 되는 응용 프로그램을 처음 실행 하거나 설치 하는 경우 또는 합니다. 경우 `true`, `group` 유효 하도록 응용 프로그램 매니페스트를 지정 해야 합니다. `optional`true 일 수 없습니다 경우 `writeableType` 값으로 지정 `applicationData`합니다.|  
|`writeableType`|선택 사항입니다. 이 파일에 데이터 파일 임을 지정 합니다. 현재 유일 하 게 유효한 값은 `applicationData`합니다.|  
  
## <a name="typelib"></a>형식 라이브러리  
 `typelib` 파일 요소의 선택적 자식 요소입니다. 요소는 COM 구성 요소에 속하는 형식 라이브러리를 설명 합니다. 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`tlbid`|필수 요소. 형식 라이브러리에 할당 된 GUID입니다.|  
|`version`|필수 요소. 형식 라이브러리의 버전 번호입니다.|  
|`helpdir`|필수 요소. 구성 요소에 대 한 도움말 파일이 포함 된 디렉터리입니다. 길이가 0 일 수 있습니다.|  
|`resourceid`|선택 사항입니다. 로캘 id (LCID) 16 진수 문자열 표현입니다. 0x 접두사 및 앞에 오는 0 없이 16 진수를 1 ~ 4는 LCID 중립 하위 언어 식별자에 있을 수 있습니다.|  
|`flags`|선택 사항입니다. 이 형식 라이브러리에 대 한 형식 라이브러리 플래그의 문자열 표현입니다. 특히, "RESTRICTED", "컨트롤", "HIDDEN" 및 "HASDISKIMAGE" 중 하나 여야 합니다.|  
  
## <a name="comclass"></a>comClass  
 `comClass` 의 선택적 자식 요소입니다는 `file` 요소, 하지만 필요한 경우에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM. 등록이 필요 없는 사용 하 여 배포 하려는 COM 구성 요소를 포함 하는 응용 프로그램 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`clsid`|필수 요소. GUID로 표현 되는 COM 구성 요소의 클래스 ID입니다.|  
|`description`|선택 사항입니다. 클래스 이름입니다.|  
|`threadingModel`|선택 사항입니다. In-process에 COM 클래스에서 사용 하는 스레딩 모델입니다. 이 속성이 null 인 경우에 스레딩 모델이 사용 됩니다. 다른 스레드에서 호출이 스레드로 마샬링되와 구성 요소는 클라이언트의 주 스레드에서 만들어집니다. 다음은 유효한 값입니다.<br /><br /> `Apartment`, `Free`, `Both` 및 `Neutral`가 있습니다.|  
|`tlbid`|선택 사항입니다. 이 COM 구성 요소에 대 한 형식 라이브러리에 대 한 GUID입니다.|  
|`progid`|선택 사항입니다. COM 구성 요소와 연결 된 버전 종속 프로그래밍 id입니다. 형식은 `ProgID` 은 `<vendor>.<component>.<version>`합니다.|  
|`miscStatus`|선택 사항입니다. 어셈블리에 중복 요소 매니페스트 제공 하는 정보는 `MiscStatus` 레지스트리 키입니다. 경우에 대 한 값은 `miscStatusIcon`, `miscStatusContent`, `miscStatusDocprint`, 또는 `miscStatusThumbnail` 특성을 찾을 수 없는, 해당 기본값에 나열 된 `miscStatus` 누락 된 특성에 사용 됩니다. 값은 다음 표에서 특성 값의 쉼표로 구분 된 목록이 수 있습니다. COM 클래스는 OCX 클래스에 필요한 경우에이 특성을 사용할 수 있습니다 `MiscStatus` 레지스트리 키 값입니다.|  
|`miscStatusIcon`|선택 사항입니다. 어셈블리에 중복 요소 매니페스트 DVASPECT_ICON 제공 하는 정보입니다. 개체의 아이콘을 제공할 수 있습니다. 값은 다음 표에서 특성 값의 쉼표로 구분 된 목록이 수 있습니다. COM 클래스는 OCX 클래스에 필요한 경우에이 특성을 사용할 수 있습니다 `Miscstatus` 레지스트리 키 값입니다.|  
|`miscStatusContent`|선택 사항입니다. 어셈블리에 중복 요소 매니페스트 DVASPECT_CONTENT 제공 하는 정보입니다. 화면 또는 프린터에 대해 표시할 수 있는 복합 문서를 제공할 수 있습니다. 값은 다음 표에서 특성 값의 쉼표로 구분 된 목록이 수 있습니다. COM 클래스는 OCX 클래스에 필요한 경우에이 특성을 사용할 수 있습니다 `MiscStatus` 레지스트리 키 값입니다.|  
|`miscStatusDocPrint`|선택 사항입니다. 어셈블리에 중복 요소 매니페스트 DVASPECT_DOCPRINT 제공 하는 정보입니다. 프린터에 인쇄 하는 경우 화면에 표시할 수 있는 개체로 표현을 제공할 수 있습니다. 값은 다음 표에서 특성 값의 쉼표로 구분 된 목록이 수 있습니다. COM 클래스는 OCX 클래스에 필요한 경우에이 특성을 사용할 수 있습니다 `MiscStatus` 레지스트리 키 값입니다.|  
|`miscStatusThumbnail`|선택 사항입니다. 어셈블리에 중복 매니페스트 DVASPECT_THUMBNAIL 제공 하는 정보입니다. 검색 도구에 표시할 수 있는 개체의 미리 보기를 제공할 수 있습니다. 값은 다음 표에서 특성 값의 쉼표로 구분 된 목록이 수 있습니다. COM 클래스는 OCX 클래스에 필요한 경우에이 특성을 사용할 수 있습니다 `MiscStatus` 레지스트리 키 값입니다.|  
  
## <a name="cominterfaceexternalproxystub"></a>comInterfaceExternalProxyStub  
 `comInterfaceExternalProxyStub` 의 선택적 자식 요소입니다는 `file` 요소인 경우 필요할 수 있습니다 하지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM. 등록이 필요 없는 사용 하 여 배포 하려는 COM 구성 요소를 포함 하는 응용 프로그램 요소는 다음과 같은 특성을 포함 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`iid`|필수 요소. ID (IID)이이 프록시에 의해 제공 되는 인터페이스입니다. IID 중괄호로 있어야 합니다.|  
|`baseInterface`|선택 사항입니다. 출처인 인터페이스에서 참조 하는 인터페이스의 IID `iid` 파생 됩니다.|  
|`numMethods`|선택 사항입니다. 인터페이스에서 구현 메서드 수입니다.|  
|`name`|선택 사항입니다. 인터페이스의 이름 코드에 표시 됩니다.|  
|`tlbid`|선택 사항입니다. 으로 지정한 인터페이스에 대 한 설명을 포함 하는 형식 라이브러리는 `iid` 특성입니다.|  
|`proxyStubClass32`|선택 사항입니다. 32 비트 프록시 Dll의에서 CLSID를 IID를 매핑합니다.|  
  
## <a name="cominterfaceproxystub"></a>comInterfaceProxyStub  
 `comInterfaceProxyStub` 의 선택적 자식 요소입니다는 `file` 요소인 경우 필요할 수 있습니다 하지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM. 등록이 필요 없는 사용 하 여 배포 하려는 COM 구성 요소를 포함 하는 응용 프로그램 요소는 다음과 같은 특성을 포함 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`iid`|필수 요소. ID (IID)이이 프록시에 의해 제공 되는 인터페이스입니다. IID 중괄호로 있어야 합니다.|  
|`baseInterface`|선택 사항입니다. 출처인 인터페이스에서 참조 하는 인터페이스의 IID `iid` 파생 됩니다.|  
|`numMethods`|선택 사항입니다. 인터페이스에서 구현 메서드 수입니다.|  
|`Name`|선택 사항입니다. 인터페이스의 이름 코드에 표시 됩니다.|  
|`Tlbid`|선택 사항입니다. 으로 지정한 인터페이스에 대 한 설명을 포함 하는 형식 라이브러리는 `iid` 특성입니다.|  
|`proxyStubClass32`|선택 사항입니다. 32 비트 프록시 Dll의에서 CLSID를 IID를 매핑합니다.|  
|`threadingModel`|선택 사항입니다. 선택 사항입니다. In-process에 COM 클래스에서 사용 하는 스레딩 모델입니다. 이 속성이 null 인 경우에 스레딩 모델이 사용 됩니다. 다른 스레드에서 호출이 스레드로 마샬링되와 구성 요소는 클라이언트의 주 스레드에서 만들어집니다. 다음은 유효한 값입니다.<br /><br /> `Apartment`, `Free`, `Both` 및 `Neutral`가 있습니다.|  
  
## <a name="windowclass"></a>windowClass  
 `windowClass` 의 선택적 자식 요소입니다는 `file` 요소인 경우 필요할 수 있습니다 하지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM. 등록이 필요 없는 사용 하 여 배포 하려는 COM 구성 요소를 포함 하는 응용 프로그램 요소에 적용 된 버전이 있어야 하는 COM 구성 요소에 정의 된 창 클래스를 가리킵니다. 요소는 다음과 같은 특성을 포함 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`versioned`|선택 사항입니다. 창 클래스를 포함 하는 어셈블리의 버전이 포함 된 내부 창 클래스 등록에 사용 하는 이름을 여부를 제어 합니다. 이 특성의 값으로 가능 `yes` 또는 `no`합니다. 기본값은 `yes`입니다. 값 `no` 동일한 창 클래스는 해당 하는 비---side-by-side 구성 요소와 함께-구성 요소가 정의 되어 있고 동일한 창 클래스 동일 하 게 취급 하려는 경우에 사용 해야 합니다. 창 클래스 등록에 대 한 일반적인 규칙이 적용 —만 적용 되는 버전에 없기 때문에 창 클래스를 등록 하는 첫 번째 구성 요소를 등록할 수 수 있습니다.|  
  
## <a name="hash"></a>hash  
 `hash` 의 선택적 자식 요소입니다는 `file` 요소입니다. `hash` 요소에는 특성이 없습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]보안 검사 응용 프로그램에 있는 모든 파일에 대 한 알고리즘 해시를 사용 하 여 배포 후에 변경 된 파일을 확인 합니다. 경우는 `hash` 요소가 포함 되지 않은,이 검사가 수행 되지 것입니다. 따라서 생략 하는 것은 `hash` 요소 권장 되지 않습니다.  
  
 해당 매니페스트가 디지털 수 없는 매니페스트 해시 하지 않은 파일이 포함 된 경우 서명 됨, 사용자가 있는 해시 되지 않은 파일의 내용을 확인할 수 없으므로 합니다.  
  
## <a name="dsigtransforms"></a>dsig:Transforms  
 `dsig:Transforms` 의 필수 자식 요소인는 `hash` 요소입니다. `dsig:Transforms` 요소에는 특성이 없습니다.  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` 의 필수 자식 요소인는 `dsig:Transforms` 요소입니다. `dsig:Transform` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Algorithm`|이 파일에 대 한 다이제스트를 계산 하는 데 사용 되는 알고리즘입니다. 사용 하는 유일한 값인 현재 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 은 `urn:schemas-microsoft-com:HashTransforms.Identity`합니다.|  
  
## <a name="dsigdigestmethod"></a>dsig:DigestMethod  
 `dsig:DigestMethod` 의 필수 자식 요소인는 `hash` 요소입니다. `dsig:DigestMethod` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Algorithm`|이 파일에 대 한 다이제스트를 계산 하는 데 사용 되는 알고리즘입니다. 사용 하는 유일한 값인 현재 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 은 `http://www.w3.org/2000/09/xmldsig#sha1`합니다.|  
  
## <a name="dsigdigestvalue"></a>dsig:DigestValue  
 `dsig:DigestValue` 의 필수 자식 요소인는 `hash` 요소입니다. `dsig:DigestValue` 요소에는 특성이 없습니다. 요소의 텍스트 값은 지정된 된 파일에 대 한 계산 된 해시 합니다.  
  
## <a name="remarks"></a>설명  
 이 요소는 응용 프로그램을 구성 하는 모든 어셈블리 이외의 파일을 식별 하 고 특히, 확인 파일에 대 한 해시 값입니다. 이 요소는 파일에 연결 된 구성 요소 개체 모델 (COM) 격리 데이터를 포함할 수도 있습니다. 사용자가 파일이 변경 되 면 응용 프로그램 매니페스트 파일은 또한 변경 내용을 반영 하도록 업데이트 되어야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `file` 응용 프로그램의 요소를 사용 하 여 배포 된 응용 프로그램에 대 한 매니페스트 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]합니다.  
  
```  
<file name="Icon.ico" size="9216">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>lVoj+Rh6RQ/HPNLOdayQah5McrI=</dsig:DigestValue>  
  </hash>  
</file>  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)