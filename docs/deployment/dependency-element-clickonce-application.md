---
title: "&lt;dependency&gt; 요소(ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "urn:schemas-microsoft-com:asm.v2#osVersionInfo"
  - "urn:schemas-microsoft-com:asm.v2#os"
  - "http://www.w3.org/2000/09/xmldsig#Transform"
  - "urn:schemas-microsoft-com:asm.v2#dependency"
  - "http://www.w3.org/2000/09/xmldsig#DigestValue"
  - "urn:schemas-microsoft-com:asm.v2#assemblyIdentity"
  - "http://www.w3.org/2000/09/xmldsig#DigestMethod"
  - "http://www.w3.org/2000/09/xmldsig#Transforms"
  - "urn:schemas-microsoft-com:asm.v2#hash"
  - "urn:schemas-microsoft-com:asm.v2#dependentAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<dependency> 요소[ClickOnce 응용 프로그램 매니페스트]"
  - "매니페스트[ClickOnce], dependency 요소"
ms.assetid: 09d6a1e0-60f8-4fbd-843b-8e49ee3115a3
caps.latest.revision: 34
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 34
---
# &lt;dependency&gt; 요소(ClickOnce 응용 프로그램)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램에 필요한 플랫폼 또는 어셈블리 종속성을 식별합니다.  
  
## 구문  
  
```  
  
      <dependency>  
   <dependentOS  
      supportURL  
      description  
   >  
      <osVersionInfo>  
         <os  
            majorVersion  
            minorVersion  
            buildNumber  
            servicePackMajor  
            servicePackMinor  
            productType  
            suiteType  
         />   
      </osVersionInfo>  
   </dependentOS>  
   <dependentAssembly  
      dependencyType  
      allowDelayedBinding  
      group  
      codeBase  
      size  
   >  
      <assemblyIdentity  
         name  
         version  
         processorArchitecture  
         language  
      >  
         <hash>  
            <dsig:Transforms>  
               <dsig:Transform  
                  Algorithm  
            />  
            </dsig:Transforms>  
            <dsig:DigestMethod />  
            <dsig:DigestValue>  
            </dsig:DigestValue>  
    </hash>  
  
      </assemblyIdentity>  
   </dependentAssembly>  
</dependency>  
```  
  
## 요소 및 특성  
 `dependency` 요소는 필수 항목입니다.  동일한 응용 프로그램 매니페스트에 여러 개의 `dependency` 인스턴스가 있을 수 있습니다.  
  
 `dependency` 요소에는 특성이 없고 다음과 같은 자식 요소가 포함되어 있습니다.  
  
### dependentOS  
 선택적 요소.  `osVersionInfo` 요소를 포함합니다.  `dependentOS` 및 `dependentAssembly` 요소는 함께 사용할 수 없습니다. `dependency` 요소에는 두 요소 중 하나가 반드시 있어야 하지만 두 요소를 함께 사용할 수는 없습니다.  
  
 `dependentOS`는 다음과 같은 특성을 지원합니다.  
  
|특성|설명|  
|--------|--------|  
|`supportUrl`|선택적 요소.  종속 플랫폼의 지원 URL을 지정합니다.  이 URL은 필요한 플랫폼을 찾은 경우 사용자에게 표시됩니다.|  
|`description`|선택적 요소.  `dependentOS` 요소에서 설명하는 운영 체제를 사람이 읽을 수 있는 형식으로 설명합니다.|  
  
### osVersionInfo  
 필수 요소.  이 요소는 `dependentOS` 요소의 자식이고 `os` 요소를 포함합니다.  이 요소에는 특성이 없습니다.  
  
### os  
 필수 요소.  이 요소는 `osVersionInfo` 요소의 자식입니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`majorVersion`|필수 요소.  OS의 주 버전 번호를 지정합니다.|  
|`minorVersion`|필수 요소.  OS의 부 버전 번호를 지정합니다.|  
|`buildNumber`|필수 요소.  OS의 빌드 번호를 지정합니다.|  
|`servicePackMajor`|필수 요소.  OS의 서비스 팩 주 번호를 지정합니다.|  
|`servicePackMinor`|선택적 요소.  OS의 서비스 팩 부 번호를 지정합니다.|  
|`productType`|선택적 요소.  제품 형식 값을 식별합니다.  유효한 값은 `server`, `workstation` 및 `domainController`입니다.  예를 들어, Windows 2000 Professional의 경우 이 특성 값은 `workstation`입니다.|  
|`suiteType`|선택적 요소.  시스템에서 사용할 수 있는 제품군 또는 시스템의 구성 형식을 식별합니다.  유효한 값은 `backoffice`, `blade`, `datacenter`, `enterprise`, `home`, `professional`, `smallbusiness`, `smallbusinessRestricted` 및 `terminal`입니다.  예를 들어, Windows 2000 Professional의 경우 이 특성 값은 `professional`입니다.|  
  
### dependentAssembly  
 선택적 요소.  `assemblyIdentity` 요소를 포함합니다.  `dependentOS` 및 `dependentAssembly` 요소는 함께 사용할 수 없습니다. `dependency` 요소에는 두 요소 중 하나가 반드시 있어야 하지만 두 요소를 함께 사용할 수는 없습니다.  
  
 `dependentAssembly`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`dependencyType`|필수 요소.  종속성 형식을 지정합니다.  유효한 값은 `preprequisite` 및 `install`입니다.  `install` 어셈블리는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 일부로 설치됩니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치하려면 `prerequisite` 어셈블리가 GAC\(전역 어셈블리 캐시\)에 있어야 합니다.|  
|`allowDelayedBinding`|필수 요소.  런타임에 프로그래밍 방식으로 어셈블리를 로드할 수 있는지 여부를 지정합니다.|  
|`group`|선택적 요소.  `dependencyType` 특성이 `install`로 설정되어 있는 경우 요청 시에만 설치되는 어셈블리의 명명된 그룹을 지정합니다.  자세한 내용은 [연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 어셈블리 다운로드](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md)를 참조하십시오.<br /><br /> `framework`로 설정되어 있고 `dependencyType` 특성이 `prerequisite`로 설정되어 있는 경우 어셈블리를 .NET Framework의 일부로 지정합니다.  [!INCLUDE[net_v40_short](../debugger/includes/net_v40_short_md.md)] 이상 버전에 설치하는 경우에는 이 어셈블리에 대해 GAC\(전역 어셈블리 캐시\)가 검사되지 않습니다.|  
|`codeBase`|`dependencyType` 특성이 `install`로 설정된 경우 필요합니다.  종속 어셈블리의 경로입니다.  절대 경로이거나 매니페스트의 코드베이스를 기준으로 한 상대 경로일 수 있습니다.  이 경로가 유효한 URI여야 어셈블리 매니페스트가 유효합니다.|  
|`size`|`dependencyType` 특성이 `install`로 설정된 경우 필요합니다.  종속 어셈블리의 바이트 단위 크기입니다.|  
  
### assemblyIdentity  
 필수 요소.  이 요소는 `dependentAssembly` 요소의 자식이고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`name`|필수 요소.  응용 프로그램의 이름을 식별합니다.|  
|`version`|필수 요소.  `major.minor.build.revision` 같은 형식으로 응용 프로그램의 버전 번호를 지정합니다.|  
|`publicKeyToken`|선택적 요소.  응용 프로그램이나 어셈블리에 서명하는 데 사용되는 공개 키의 `SHA-1` 해시 값에서 마지막 8바이트를 나타내는 16개의 16진수 문자를 지정합니다.  카탈로그에 서명하는 데 사용되는 공개 키는 2048비트 이상이어야 합니다.|  
|`processorArchitecture`|선택적 요소.  프로세서를 지정합니다.  유효한 값은 32비트 Windows의 경우 `x86`이고 64비트 Windows의 경우 `I64`입니다.|  
|`language`|선택적 요소.  EN\-US 같이 두 부분으로 구성된 어셈블리의 언어 코드를 식별합니다.|  
  
### hash  
 `hash`는 `assemblyIdentity` 요소의 선택적 자식 요소입니다.  `hash` 요소에는 특성이 없습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 배포 후에 변경된 파일이 없음을 확인하기 위해 응용 프로그램의 모든 파일에 대한 알고리즘 해시를 보안 검사에 사용합니다.  `hash` 요소가 포함되어 있지 않으면 이 확인이 수행되지 않습니다. 따라서 `hash` 요소를 생략하는 것은 좋지 않습니다.  
  
### dsig:Transforms  
 `dsig:Transforms` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:Transforms` 요소에는 특성이 없습니다.  
  
### dsig:Transform  
 `dsig:Transform` 요소는 `dsig:Transforms` 요소의 필수 자식입니다.  `dsig:Transform` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Algorithm`|이 파일의 다이제스트를 계산하는 데 사용되는 알고리즘입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 현재 사용되는 유일한 값은 `urn:schemas-microsoft-com:HashTransforms.Identity`입니다.|  
  
### dsig:DigestMethod  
 `dsig:DigestMethod` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:DigestMethod` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Algorithm`|이 파일의 다이제스트를 계산하는 데 사용되는 알고리즘입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 현재 사용되는 유일한 값은 `http://www.w3.org/2000/09/xmldsig#sha1`입니다.|  
  
### dsig:DigestValue  
 `dsig:DigestValue` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:DigestValue` 요소에는 특성이 없습니다.  이 요소의 텍스트 값은 지정된 파일에 대해 계산된 해시입니다.  
  
## 설명  
 응용 프로그램에 사용되는 모든 어셈블리에는 상응하는 `dependency` 요소가 있어야 합니다.  전역 어셈블리 캐시에 플랫폼 어셈블리로 사전 설치해야 하는 어셈블리는 종속 어셈블리에 포함되지 않습니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트의 `dependency` 요소를 보여 줍니다.  이 코드 예제는 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md) 항목에 대해 제공되는 더 큰 예제의 일부입니다.  
  
```  
<dependency>  
  <dependentOS>  
    <osVersionInfo>  
      <os   
        majorVersion="4"   
        minorVersion="10"   
        buildNumber="0"   
        servicePackMajor="0" />  
    </osVersionInfo>  
  </dependentOS>  
</dependency>  
<dependency>  
  <dependentAssembly  
    dependencyType="preRequisite"  
    allowDelayedBinding="true">  
    <assemblyIdentity  
      name="Microsoft.Windows.CommonLanguageRuntime"  
      version="4.0.20506.0" />  
  </dependentAssembly>  
</dependency>  
  
<dependency>  
  <dependentAssembly  
    dependencyType="install"  
    allowDelayedBinding="true"  
    codebase="MyApplication.exe"  
    size="4096">  
    <assemblyIdentity  
      name="MyApplication"  
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [\<dependency\> 요소](../deployment/dependency-element-clickonce-deployment.md)