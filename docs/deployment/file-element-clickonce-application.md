---
title: "&lt;file&gt; 요소(ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://www.w3.org/2000/09/xmldsig#Transform"
  - "urn:schemas-microsoft-com:asm.v2#file"
  - "http://www.w3.org/2000/09/xmldsig#DigestValue"
  - "http://www.w3.org/2000/09/xmldsig#DigestMethod"
  - "http://www.w3.org/2000/09/xmldsig#Transforms"
  - "urn:schemas-microsoft-com:asm.v2#hash"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<file> 요소[ClickOnce 응용 프로그램 매니페스트]"
  - "매니페스트[ClickOnce], file 요소"
ms.assetid: 56e3490c-eed5-4841-b1bf-eefe778b6ac9
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;file&gt; 요소(ClickOnce 응용 프로그램)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램에서 다운로드하여 사용하는 어셈블리 이외의 모든 파일을 식별합니다.  
  
## 구문  
  
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
  
## 요소 및 특성  
 `file` 요소는 선택적 항목입니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 요소.  파일의 이름을 식별합니다.|  
|`size`|필수 요소.  파일의 크기를 바이트 단위로 지정합니다.|  
|`group`|`optional` 특성이 지정되지 않았거나 `false`로 설정되었으면 선택적 요소이고, `optional`이 `true`로 설정되었으면 필수 요소입니다.  이 특성은 이 파일이 속한 그룹의 이름을 나타냅니다.  이 이름은 개발자가 선택한 임의의 유니코드 문자열 값이 될 수 있고 <xref:System.Deployment.Application.ApplicationDeployment> 클래스를 사용하여 요청 시 파일을 다운로드하는 데 사용됩니다.|  
|`optional`|선택적 요소.  응용 프로그램을 처음 실행할 때 파일을 다운로드할지 응용 프로그램에서 요청하기 전까지는 파일을 서버에 보관할지 여부를 지정합니다.  `false`이거나 정의되어 있지 않으면 응용 프로그램을 처음 실행하거나 설치할 때 파일이 다운로드됩니다.  `true`인 경우 응용 프로그램 매니페스트가 유효하려면 `group`를 지정해야 합니다.  `optional`은 `writeableType`이 값 `applicationData`로 지정된 경우 true가 될 수 없습니다.|  
|`writeableType`|선택적 요소.  이 파일이 데이터 파일임을 지정합니다.  현재 유일하게 유효한 값은 `applicationData`입니다.|  
  
## typelib  
 `typelib` 요소는 파일 요소의 선택적 자식 요소입니다.  이 요소는 COM 구성 요소에 속하는 형식 라이브러리를 설명합니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`tlbid`|필수 요소.  형식 라이브러리에 할당된 GUID입니다.|  
|`version`|필수 요소.  형식 라이브러리의 버전 번호입니다.|  
|`helpdir`|필수 요소.  구성 요소의 도움말 파일을 포함하는 디렉터리이며  길이가 0일 수 있습니다.|  
|`resourceid`|선택적 요소.  로캘 ID\(LCID\)의 16진수 문자열 표현입니다.  0x 접두사가 없고 0으로 시작하지 않는 1~4자리 16진수입니다.  LCID에는 중립 보조 언어 식별자가 있을 수 있습니다.|  
|`flags`|선택적 요소.  이 형식 라이브러리에 대한 형식 라이브러리 플래그의 문자열 표현입니다.  "RESTRICTED", "CONTROL", "HIDDEN", "HASDISKIMAGE" 중 하나여야 합니다.|  
  
## comClass  
 `comClass` 요소는 `file` 요소의 선택적 자식 요소이지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 등록이 필요 없는 COM을 사용하여 배포하려는 COM 구성 요소가 포함되어 있는 경우에는 필수 요소입니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`clsid`|필수 요소.  GUID로 표현된 COM 구성 요소의 클래스 ID입니다.|  
|`description`|선택적 요소.  클래스 이름입니다.|  
|`threadingModel`|선택적 요소.  in\-process COM 클래스에서 사용하는 스레딩 모델입니다.  이 속성이 null이면 스레딩 모델이 사용되지 않습니다.  구성 요소는 클라이언트의 주 스레드에서 만들어지며 다른 스레드로부터의 호출은 이 스레드로 마샬링됩니다.  다음 목록에서는 올바른 값을 보여 줍니다.<br /><br /> `Apartment`, `Free`, `Both` 및 `Neutral`|  
|`tlbid`|선택적 요소.  이 COM 구성 요소에 대한 형식 라이브러리의 GUID입니다.|  
|`progid`|선택적 요소.  COM 구성 요소와 연결된 버전별 프로그래밍 ID입니다.  `ProgID`의 형식은 `<vendor>.<component>.<version>`입니다.|  
|`miscStatus`|선택적 요소.  `MiscStatus` 레지스트리 키에서 제공하는 정보를 어셈블리 매니페스트에 복제합니다.  `miscStatusIcon`, `miscStatusContent`, `miscStatusDocprint` 또는 `miscStatusThumbnail` 특성의 값을 찾을 수 없는 경우 `miscStatus`에 나열된 해당 기본값을 특성 값으로 사용합니다.  이 값은 다음 표의 특성 값을 쉼표로 구분한 목록이 될 수 있습니다.  COM 클래스가 `MiscStatus` 레지스트리 키 값이 필요한 OCX 클래스인 경우 이 특성을 사용할 수 있습니다.|  
|`miscStatusIcon`|선택적 요소.  DVASPECT\_ICON에서 제공하는 정보를 어셈블리 매니페스트에 복제합니다.  개체의 아이콘을 제공할 수 있습니다.  이 값은 다음 표의 특성 값을 쉼표로 구분한 목록이 될 수 있습니다.  COM 클래스가 `Miscstatus` 레지스트리 키 값이 필요한 OCX 클래스인 경우 이 특성을 사용할 수 있습니다.|  
|`miscStatusContent`|선택적 요소.  DVASPECT\_CONTENT에서 제공하는 정보를 어셈블리 매니페스트에 복제합니다.  화면 또는 프린터에 대해 표시할 수 있는 복합 문서를 제공할 수 있습니다.  이 값은 다음 표의 특성 값을 쉼표로 구분한 목록이 될 수 있습니다.  COM 클래스가 `MiscStatus` 레지스트리 키 값이 필요한 OCX 클래스인 경우 이 특성을 사용할 수 있습니다.|  
|`miscStatusDocPrint`|선택적 요소.  DVASPECT\_DOCPRINT에서 제공하는 정보를 어셈블리 매니페스트에 복제합니다.  프린터에 인쇄된 것처럼 화면에 표시할 수 있는 개체 표현을 제공할 수 있습니다.  이 값은 다음 표의 특성 값을 쉼표로 구분한 목록이 될 수 있습니다.  COM 클래스가 `MiscStatus` 레지스트리 키 값이 필요한 OCX 클래스인 경우 이 특성을 사용할 수 있습니다.|  
|`miscStatusThumbnail`|선택적 요소.  DVASPECT\_THUMBNAIL에서 제공하는 정보를 어셈블리 매니페스트에 복제합니다.  검색 도구에 표시할 수 있는 개체의 축소판 그림을 제공할 수 있습니다.  이 값은 다음 표의 특성 값을 쉼표로 구분한 목록이 될 수 있습니다.  COM 클래스가 `MiscStatus` 레지스트리 키 값이 필요한 OCX 클래스인 경우 이 특성을 사용할 수 있습니다.|  
  
## comInterfaceExternalProxyStub  
 `comInterfaceExternalProxyStub`은 `file` 요소의 선택적 자식 요소이지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 등록이 필요 없는 COM을 사용하여 배포하려는 COM 구성 요소가 포함되어 있는 경우에는 필수 요소입니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`iid`|필수 요소.  이 프록시에 의해 제공되는 IID\(인터페이스 ID\)입니다.  IID는 중괄호로 묶어야 합니다.|  
|`baseInterface`|선택적 요소.  `iid`에서 참조하는 인터페이스가 파생된 인터페이스의 IID입니다.|  
|`numMethods`|선택적 요소.  인터페이스에서 구현하는 메서드 수입니다.|  
|`name`|선택적 요소.  코드에 나타나는 인터페이스 이름입니다.|  
|`tlbid`|선택적 요소.  `iid` 특성에서 지정하는 인터페이스의 설명을 포함하는 형식 라이브러리입니다.|  
|`proxyStubClass32`|선택적 요소.  IID를 32비트 프록시 DLL에서 CLSID로 매핑합니다.|  
  
## comInterfaceProxyStub  
 `comInterfaceProxyStub`은 `file` 요소의 선택적 자식 요소이지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 등록이 필요 없는 COM을 사용하여 배포하려는 COM 구성 요소가 포함되어 있는 경우에는 필수 요소입니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`iid`|필수 요소.  이 프록시에 의해 제공되는 IID\(인터페이스 ID\)입니다.  IID는 중괄호로 묶어야 합니다.|  
|`baseInterface`|선택적 요소.  `iid`에서 참조하는 인터페이스가 파생된 인터페이스의 IID입니다.|  
|`numMethods`|선택적 요소.  인터페이스에서 구현하는 메서드 수입니다.|  
|`Name`|선택적 요소.  코드에 나타나는 인터페이스 이름입니다.|  
|`Tlbid`|선택적 요소.  `iid` 특성에서 지정하는 인터페이스의 설명을 포함하는 형식 라이브러리입니다.|  
|`proxyStubClass32`|선택적 요소.  IID를 32비트 프록시 DLL에서 CLSID로 매핑합니다.|  
|`threadingModel`|선택적 요소.  선택적 요소.  in\-process COM 클래스에서 사용하는 스레딩 모델입니다.  이 속성이 null이면 스레딩 모델이 사용되지 않습니다.  구성 요소는 클라이언트의 주 스레드에서 만들어지며 다른 스레드로부터의 호출은 이 스레드로 마샬링됩니다.  다음 목록에서는 올바른 값을 보여 줍니다.<br /><br /> `Apartment`, `Free`, `Both` 및 `Neutral`|  
  
## windowClass  
 `windowClass`은 `file` 요소의 선택적 자식 요소이지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 등록이 필요 없는 COM을 사용하여 배포하려는 COM 구성 요소가 포함되어 있는 경우에는 필수 요소입니다.  이 요소는 적용된 버전이 있어야 하는 COM 구성 요소에서 정의하는 창 클래스를 참조합니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`versioned`|선택적 요소.  등록에 사용되는 내부 창 클래스 이름에 창 클래스를 포함하는 어셈블리 버전을 포함할지 여부를 제어합니다.  이 특성의 값은 `yes` 또는 `no`입니다.  기본값은 `yes`입니다.  `no` 값은 동일한 창 클래스가 side\-by\-side 구성 요소 및 동일한 비 side\-by\-side 구성 요소에 의해 정의되었고 이를 동일한 창 클래스로 처리하려는 경우에만 사용해야 합니다.  적용된 버전이 없으므로 일반 창 클래스 등록 규칙이 적용되어 창 클래스를 등록하는 첫 번째 구성 요소만 등록할 수 있습니다.|  
  
## hash  
 `hash`는 `file` 요소의 선택적 자식 요소입니다.  `hash` 요소에는 특성이 없습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 배포 후에 변경된 파일이 없음을 확인하기 위해 응용 프로그램의 모든 파일에 대한 알고리즘 해시를 보안 검사에 사용합니다.  `hash` 요소가 포함되어 있지 않으면 이 확인이 수행되지 않습니다. 따라서 `hash` 요소를 생략하는 것은 좋지 않습니다.  
  
 매니페스트에 해시되지 않은 파일이 들어 있으면 사용자가 해시되지 않은 파일의 내용을 확인할 수 없으므로 해당 매니페스트에 디지털 서명할 수 없습니다.  
  
## dsig:Transforms  
 `dsig:Transforms` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:Transforms` 요소에는 특성이 없습니다.  
  
## dsig:Transform  
 `dsig:Transform` 요소는 `dsig:Transforms` 요소의 필수 자식입니다.  `dsig:Transform` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Algorithm`|이 파일의 다이제스트를 계산하는 데 사용되는 알고리즘입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 현재 사용되는 유일한 값은 `urn:schemas-microsoft-com:HashTransforms.Identity`입니다.|  
  
## dsig:DigestMethod  
 `dsig:DigestMethod` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:DigestMethod` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Algorithm`|이 파일의 다이제스트를 계산하는 데 사용되는 알고리즘입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 현재 사용되는 유일한 값은 `http://www.w3.org/2000/09/xmldsig#sha1`입니다.|  
  
## dsig:DigestValue  
 `dsig:DigestValue` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:DigestValue` 요소에는 특성이 없습니다.  이 요소의 텍스트 값은 지정된 파일에 대해 계산된 해시입니다.  
  
## 설명  
 이 요소는 응용 프로그램을 구성하는 어셈블리 이외의 모든 파일을 식별하고 특히 파일 확인을 위한 해시 값을 식별합니다.  이 요소에는 파일과 관련된 COM\(구성 요소 개체 모델\) 격리 데이터가 포함될 수도 있습니다.  파일이 변경되면 변경 내용을 반영하도록 응용 프로그램 매니페스트 파일도 업데이트해야 합니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하여 배포되는 응용 프로그램에 대한 응용 프로그램 매니페스트의 `file` 요소를 보여 줍니다.  
  
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
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)