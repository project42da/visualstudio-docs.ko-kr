---
title: "&lt;dependency&gt; 요소(ClickOnce 배포) | Microsoft Docs"
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
  - "<dependency> 요소[ClickOnce 배포 매니페스트]"
ms.assetid: 9b4d2082-0347-4922-ac70-85f11b913039
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;dependency&gt; 요소(ClickOnce 배포)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

설치할 응용 프로그램의 버전과 응용 프로그램 매니페스트의 위치를 식별합니다.  
  
## 구문  
  
```  
  
      <dependency>   
   <dependentAssembly  
      preRequisite  
      visible  
      dependencyType  
      codeBase  
      size  
   >   
      <assemblyIdentity   
         name   
         version   
         publicKeyToken   
         processorArchitecture   
         language  
         type  
      />   
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
  
   </dependentAssembly>   
</dependency>  
```  
  
## 요소 및 특성  
 `dependency` 요소는 필수 항목입니다.  특성이 없습니다.  배포 매니페스트에는 `dependency` 요소가 여러 개 있을 수 있습니다.  
  
 `dependency` 요소는 일반적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 포함된 어셈블리에 대한 주 응용 프로그램의 종속성을 표현합니다.  Main.exe 응용 프로그램에서 DotNetAssembly.dll이라는 어셈블리를 사용하는 경우 이 어셈블리는 종속성 섹션에 표시되어 있어야 합니다.  그러나 특정 버전의 공용 언어 런타임, GAC\(전역 어셈블리 캐시\)의 어셈블리 또는 COM 개체에 대한 종속성 같이 다른 형식의 종속성을 표현할 수도 있습니다.  이는 자동\(no\-touch\) 배포 기술이므로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 이러한 형식의 종속 항목에 대한 다운로드 및 설치를 시작할 수 없지만 하나 이상의 지정된 종속 항목이 없는 경우 응용 프로그램이 실행되지 않도록 막을 수는 있습니다.  
  
## dependentAssembly  
 필수 요소.  이 요소에는 `assemblyIdentity` 요소가 포함되어 있습니다.  다음 표에서는 `dependentAssembly`가 지원하는 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|`preRequisite`|선택적 요소.  GAC에 이 어셈블리가 미리 있어야 하는지 지정합니다.  유효한 값으로는 `true`나 `false`를 사용할 수 있습니다.  `true`이고 GAC에 지정된 어셈블리가 없으면 응용 프로그램이 실행되지 않습니다.|  
|`visible`|선택적 요소.  해당 종속성을 포함하여 최상위 응용 프로그램 ID를 식별합니다.  응용 프로그램 저장소와 활성화를 관리하기 위해 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 내부적으로 사용합니다.|  
|`dependencyType`|필수 요소.  종속성과 응용 프로그램 사이의 관계입니다.  올바른 값은 다음과 같습니다.<br /><br /> -   `install`.  구성 요소가 현재 응용 프로그램과 별도의 설치를 나타냅니다.<br />-   `preRequisite`.  구성 요소를 현재 응용 프로그램에서 요구합니다.|  
|`codebase`|선택적 요소.  응용 프로그램 매니페스트의 전체 경로입니다.|  
|`size`|선택적 요소.  응용 프로그램 매니페스트의 바이트 단위 크기입니다.|  
  
## assemblyIdentity  
 필수 요소.  이 요소는 `dependentAssembly` 요소의 자식입니다.  `assemblyIdentity`의 내용은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트에서 설명하는 것과 동일해야 합니다.  다음 표에는 `assemblyIdentity` 요소의 특성이 나와 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 요소.  응용 프로그램의 이름을 식별합니다.|  
|`Version`|필수 요소.  `major.minor.build.revision`의 형식으로 응용 프로그램의 버전 번호를 지정합니다.|  
|`publicKeyToken`|필수 요소.  응용 프로그램이나 어셈블리를 서명하는 데 사용되는 공개 키의 SHA\-1 해시 값에서 마지막 8바이트를 나타내는 16개의 16진수 문자를 지정합니다.  서명하는 데 사용되는 공개 키는 2048비트 이상이어야 합니다.|  
|`processorArchitecture`|필수 요소.  마이크로프로세서를 지정합니다.  유효한 값은 32비트 Windows의 경우 `x86`이고 64비트 Windows의 경우 `IA64`입니다.|  
|`Language`|선택적 요소.  두 부분으로 구성된 어셈블리의 언어 코드를 식별합니다.  예를 들어, EN\-US는 영어\(미국\)를 나타냅니다.  기본값은 `neutral`입니다.  이 요소는 `asmv2` 네임스페이스에 있습니다.|  
|`type`|선택적 요소.  이전 버전의 Windows 병렬 설치 기술과의 호환성을 위한 것입니다.  유일하게 허용되는 값은 `win32`입니다.|  
  
## hash  
 `hash`는 `file` 요소의 선택적 자식 요소입니다.  `hash` 요소에는 특성이 없습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 배포 후에 변경된 파일이 없음을 확인하기 위해 응용 프로그램의 모든 파일에 대한 알고리즘 해시를 보안 검사에 사용합니다.  `hash` 요소가 포함되어 있지 않으면 이 확인이 수행되지 않습니다. 따라서 `hash` 요소를 생략하는 것은 좋지 않습니다.  
  
## dsig:Transforms  
 `dsig:Transforms` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:Transforms` 요소에는 특성이 없습니다.  
  
## dsig:Transform  
 `dsig:Transform` 요소는 `dsig:Transforms` 요소의 필수 자식입니다.  다음 표에서는 `dsig:Transform` 요소의 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|`Algorithm`|이 파일의 다이제스트를 계산하는 데 사용되는 알고리즘입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 현재 사용되는 유일한 값은 `urn:schemas-microsoft-com:HashTransforms.Identity`입니다.|  
  
## dsig:DigestMethod  
 `dsig:DigestMethod` 요소는 `hash` 요소의 필수 자식입니다.  다음 표에서는 `dsig:DigestMethod` 요소의 특성을 보여 줍니다.  
  
|특성|설명|  
|--------|--------|  
|`Algorithm`|이 파일의 다이제스트를 계산하는 데 사용되는 알고리즘입니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 현재 사용되는 유일한 값은 `http://www.w3.org/2000/09/xmldsig#sha1`입니다.|  
  
## dsig:DigestValue  
 `dsig:DigestValue` 요소는 `hash` 요소의 필수 자식입니다.  `dsig:DigestValue` 요소에는 특성이 없습니다.  이 요소의 텍스트 값은 지정된 파일에 대해 계산된 해시입니다.  
  
## 설명  
 배포 매니페스트에는 일반적으로 응용 프로그램 매니페스트의 이름 및 버전을 식별하는 `assemblyIdentity` 요소가 단 한 개 있습니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트의 `dependency` 요소를 보여 줍니다.  
  
```  
<!-- Identify the assembly dependencies -->  
<dependency>  
  <dependentAssembly dependencyType="install" allowDelayedBinding="true" codebase="MyApplication.exe" size="16384">  
    <assemblyIdentity name="MyApplication" version="0.0.0.0" cultural="neutral" processorArchitecture="msil" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
       <dsig:DigestValue>YzXYZJAvj9pgAG3y8jXUjC7AtHg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## 예제  
 다음 코드 예제에서는 GAC에 이미 설치된 어셈블리에 대한 종속성을 지정합니다.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="GACAssembly" version="1.0.0.0" language="neutral" processorArchitecture="msil" />  
  </dependentAssembly>  
</dependency>  
```  
  
## 예제  
 다음 코드 예제에서는 공용 언어 런타임의 특정 버전에 대한 종속성을 지정합니다.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50215.0" />  
  </dependentAssembly>  
</dependency>  
```  
  
## 예제  
 다음 코드 예제에서는 운영 체제 종속성을 지정합니다.  
  
```  
<dependency>  
   <dependentOS supportUrl="http://www.microsoft.com" description="Microsoft Windows Operating System">  
      <osVersionInfo>  
         <os majorVersion="4" minorVersion="10" />  
      </osVersionInfo>  
   </dependentOS>  
</dependency>  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [\<dependency\> 요소](../deployment/dependency-element-clickonce-application.md)