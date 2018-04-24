---
title: '&lt;종속성&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#osVersionInfo
- urn:schemas-microsoft-com:asm.v2#os
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#dependency
- http://www.w3.org/2000/09/xmldsig#DigestValue
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
- urn:schemas-microsoft-com:asm.v2#dependentAssembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <dependency> element [ClickOnce deployment manifest]
ms.assetid: 9b4d2082-0347-4922-ac70-85f11b913039
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 72e217413a428c8c22712ac3a90836b1ea4fbc35
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ltdependencygt-element-clickonce-deployment"></a>&lt;종속성&gt; 요소 (ClickOnce 배포)
를 설치 하려면 응용 프로그램의 버전 및 응용 프로그램 매니페스트의 위치를 식별 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `dependency` 요소는 필수입니다. 특성이 없습니다. 배포 매니페스트는 여러 개 있을 수 `dependency` 요소입니다.  
  
 `dependency` 요소 내에 포함 된 어셈블리에는 주 응용 프로그램에 대 한 종속성을 표현 합니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. Main.exe 응용 프로그램 DotNetAssembly.dll 이라는 어셈블리를 사용 하는 경우 해당 어셈블리 종속성 섹션에 나열 되어야 합니다. 그러나 종속성에는 전역 어셈블리 캐시 (GAC)에 어셈블리 또는 COM 개체에는 다른 유형의 공용 언어 런타임의 특정 버전에 대 한 종속성 같은 종속성을 표현할 수도 있습니다. 자동 배포 기술 이기 때문에 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 막을 수 없습니다 종속성 하지만 이러한 유형의의 시작 다운로드 및 설치는 실행에서 응용 프로그램에서 지정 된 종속성 중 하나 이상을 존재 하지 않는 경우.  
  
## <a name="dependentassembly"></a>dependentAssembly  
 필수. 이 요소에 포함 된 `assemblyIdentity` 요소입니다. 다음 표에서 특성을 보여 줍니다.는 `dependentAssembly` 지원 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`preRequisite`|선택 사항입니다. 이 어셈블리는 GAC에 이미 존재 해야 지정 합니다. 유효한 값은 `true` 및 `false`입니다. 경우 `true`, 지정된 된 어셈블리는 GAC에 존재 하지 않는 하 고, 응용 프로그램이 실행 되지 않습니다.|  
|`visible`|선택 사항입니다. 종속성을 비롯 한 최상위 응용 프로그램 id를 식별 합니다. 내부적으로 사용 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 저장소 및 정품 인증을 관리할 수 있습니다.|  
|`dependencyType`|필수. 이 종속성 및 응용 프로그램 간의 관계입니다. 올바른 값은 다음과 같습니다.<br /><br /> -   `install`. 구성 요소는 현재 응용 프로그램에서 별도 설치를 나타냅니다.<br />-   `preRequisite`. 현재 응용 프로그램 구성 요소가 필요 합니다.|  
|`codebase`|선택 사항입니다. 응용 프로그램 매니페스트를 전체 경로입니다.|  
|`size`|선택 사항입니다. 응용 프로그램 매니페스트의 바이트 크기입니다.|  
  
## <a name="assemblyidentity"></a>assemblyIdentity  
 필수. 이 요소는 `dependentAssembly` 요소의 자식입니다. 내용을 `assemblyIdentity` 에 설명 된 대로 동일 해야 합니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. 다음 표에의 특성은 `assemblyIdentity` 요소입니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수. 응용 프로그램의 이름을 식별합니다.|  
|`Version`|필수. 다음 형식으로는 응용 프로그램의 버전 번호를 지정합니다. `major.minor.build.revision`|  
|`publicKeyToken`|필수. 응용 프로그램이 나 어셈블리 서명에 사용 된 공개 키의 sha-1 해시의 마지막 8 바이트를 나타내는 16 자리의 16 진수 문자열을 지정 합니다. 서명에 사용 되는 공개 키에 2048 비트 이어야 합니다. 큰 합니다.|  
|`processorArchitecture`|필수. 마이크로프로세서를 지정합니다. 유효한 값은 `x86` 32 비트 Windows에 대 한 및 `IA64` 64 비트 Windows에 대 한 합니다.|  
|`Language`|선택 사항입니다. 어셈블리의 두 부분 언어 코드를 식별합니다. 예를 들어, EN-US, 영어 (미국)를 나타내는입니다. 기본값은 `neutral`입니다. 이 요소는는 `asmv2` 네임 스페이스입니다.|  
|`type`|선택 사항입니다. 이전 버전인 Windows-함께와 호환성 설치 기술 합니다. 허용 되는 유일한 값은 `win32`합니다.|  
  
## <a name="hash"></a>hash  
 `hash` 의 선택적 자식 요소입니다는 `file` 요소입니다. `hash` 요소에는 특성이 없습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 보안 검사 방법으로 응용 프로그램에 있는 모든 파일에 대 한 알고리즘 해시를 사용 하 여 배포 후에 변경 된 파일을 확인 합니다. 경우는 `hash` 요소가 포함 되지 않은,이 검사가 수행 되지 것입니다. 따라서 생략 하는 것은 `hash` 요소 권장 되지 않습니다.  
  
## <a name="dsigtransforms"></a>dsig:Transforms  
 `dsig:Transforms` 의 필수 자식 요소인는 `hash` 요소입니다. `dsig:Transforms` 요소에는 특성이 없습니다.  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` 의 필수 자식 요소인는 `dsig:Transforms` 요소입니다. 다음 표에의 특성은 `dsig:Transform` 요소입니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Algorithm`|이 파일에 대 한 다이제스트를 계산 하는 데 사용 되는 알고리즘입니다. 사용 하는 유일한 값인 현재 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 은 `urn:schemas-microsoft-com:HashTransforms.Identity`합니다.|  
  
## <a name="dsigdigestmethod"></a>dsig:DigestMethod  
 `dsig:DigestMethod` 의 필수 자식 요소인는 `hash` 요소입니다. 다음 표에의 특성은 `dsig:DigestMethod` 요소입니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Algorithm`|이 파일에 대 한 다이제스트를 계산 하는 데 사용 되는 알고리즘입니다. 사용 하는 유일한 값인 현재 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 은 `http://www.w3.org/2000/09/xmldsig#sha1`합니다.|  
  
## <a name="dsigdigestvalue"></a>dsig:DigestValue  
 `dsig:DigestValue` 의 필수 자식 요소인는 `hash` 요소입니다. `dsig:DigestValue` 요소에는 특성이 없습니다. 요소의 텍스트 값은 지정된 된 파일에 대 한 계산 된 해시 합니다.  
  
## <a name="remarks"></a>설명  
 배포 매니페스트는 일반적으로 단일은 `assemblyIdentity` 이름 및 응용 프로그램 매니페스트 버전을 지정 하는 요소입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 `dependency` 요소에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트 합니다.  
  
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
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 GAC에 이미 설치 된 어셈블리에 종속성을 지정 합니다.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="GACAssembly" version="1.0.0.0" language="neutral" processorArchitecture="msil" />  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 공용 언어 런타임의 특정 버전에 종속성을 지정 합니다.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50215.0" />  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>예제  
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
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [\<종속성 > 요소](../deployment/dependency-element-clickonce-application.md)