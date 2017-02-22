---
title: "ClickOnce 응용 프로그램 매니페스트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 매니페스트[ClickOnce]"
  - "ClickOnce, 응용 프로그램 매니페스트"
ms.assetid: 29570cec-4e53-4660-a850-abc4fa150243
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 응용 프로그램 매니페스트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램매니페스트를 사용 하 여 배포 된응용 프로그램에 대해 설명 하는XML파일입니다 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램매니페스트에 다음과 같은 요소와 특성이 있습니다.  
  
|요소|설명|특성|  
|--------|--------|--------|  
|[\<assembly\> 요소](../deployment/assembly-element-clickonce-application.md)|필수 요소.  최상위 요소.|`manifestVersion`|  
|[\<assemblyIdentity\> 요소](../deployment/assemblyidentity-element-clickonce-application.md)|필수 요소.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 주 어셈블리를 식별합니다.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[\<trustInfo\> 요소](../deployment/trustinfo-element-clickonce-application.md)|응용 프로그램 보안 요구 사항을 식별합니다.|없음|  
|[\<entryPoint\> 요소](../deployment/entrypoint-element-clickonce-application.md)|필수 요소.  응용 프로그램 코드 진입점을 식별합니다.|`name`|  
|[\<dependency\> 요소](../deployment/dependency-element-clickonce-application.md)|필수 요소.  응용 프로그램 실행에 필요한 각 종속성을 식별합니다.  사전 설치해야 하는 어셈블리를 식별할 수도 있습니다.|없음|  
|[\<file\> 요소](../deployment/file-element-clickonce-application.md)|선택적 요소.  응용 프로그램에 사용되는 어셈블리 이외의 각 파일을 식별합니다.  파일과 관련된 COM\(Component Object Model\) 격리 데이터가 포함될 수 있습니다.|`name`<br /><br /> `size`<br /><br /> `group`<br /><br /> `optional`<br /><br /> `writeableType`|  
|[\<fileAssociation\> 요소](../deployment/fileassociation-element-clickonce-application.md)|선택적 요소.  응용 프로그램과 연결할 파일 확장명을 식별합니다.|`extension`<br /><br /> `description`<br /><br /> `progid`<br /><br /> `defaultIcon`|  
  
## 설명  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램매니페스트파일을 사용 하 여 배포 된응용 프로그램을 식별 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].    [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 대한 자세한 내용은 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)를 참조하십시오.  
  
## 파일 위치  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램매니페스트는 특정 단일버전을배포합니다.    이 때문에 이들은 별도로배포매니페스트와 저장 되어야 합니다.  일반적으로 응용 프로그램 매니페스트는 관련 버전에 따라 이름을 지정한 하위 디렉터리에 저장합니다.  
  
 응용 프로그램 매니페스트는 항상 배포에 앞서 서명해야 합니다.  응용 프로그램 매니페스트를 수동으로 변경하는 경우 mage.exe를 사용하여 응용 프로그램 매니페스트를 다시 서명하고 배포 매니페스트를 업데이트한 다음 배포 매니페스트를 다시 서명해야 합니다.  자세한 내용은 [연습: ClickOnce 응용 프로그램 수동 배포](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)를 참조하십시오.  
  
## 파일 이름 구문  
 이름은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램매니페스트파일에서 식별 된 대로 될 해야 합니다전체 이름및응용 프로그램의확장명`assemblyIdentity`확장명에서 뒤에 요소를.매니페스트.    예를 들어, Example.exe 응용 프로그램을 가리키는 응용 프로그램 매니페스트에는 다음과 같은 파일 이름 구문을 사용해야 합니다.  
  
 `example.exe.manifest`  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 응용 프로그램 매니페스트를 보여 줍니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd" manifestVersion="1.0" xmlns:asmv3="urn:schemas-microsoft-com:asm.v3" xmlns:dsig="http://www.w3.org/2000/09/xmldsig#" xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2" xmlns="urn:schemas-microsoft-com:asm.v2" xmlns:asmv1="urn:schemas-microsoft-com:asm.v1" xmlns:asmv2="urn:schemas-microsoft-com:asm.v2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
  <asmv1:assemblyIdentity name="My Application Deployment.exe" version="1.0.0.0" publicKeyToken="43cb1e8e7a352766" language="neutral" processorArchitecture="x86" type="win32" />  
  <application />  
  <entryPoint>  
    <assemblyIdentity name="MyApplication" version="1.0.0.0" language="neutral" processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
  <trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet Unrestricted="true" ID="Custom" SameSite="site" />  
        <defaultAssemblyRequest permissionSetReference="Custom" />  
      </applicationRequestMinimum>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <!--  
          UAC Manifest Options  
          If you want to change the Windows User Account Control level replace the   
          requestedExecutionLevel node with one of the following.  
  
        <requestedExecutionLevel  level="asInvoker" uiAccess="false" />  
        <requestedExecutionLevel  level="requireAdministrator" uiAccess="false" />  
        <requestedExecutionLevel  level="highestAvailable" uiAccess="false" />  
  
         If you want to utilize File and Registry Virtualization for backward   
         compatibility then delete the requestedExecutionLevel node.  
    -->  
        <requestedExecutionLevel level="asInvoker" uiAccess="false" />  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
  <dependency>  
    <dependentOS>  
      <osVersionInfo>  
        <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
      </osVersionInfo>  
    </dependentOS>  
  </dependency>  
  <dependency>  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
      <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.20506.0" />  
    </dependentAssembly>  
  </dependency>  
  <dependency>  
    <dependentAssembly dependencyType="install" allowDelayedBinding="true" codebase="MyApplication.exe" size="4096">  
      <assemblyIdentity name="MyApplication" version="1.0.0.0" language="neutral" processorArchitecture="x86" />  
      <hash>  
        <dsig:Transforms>  
          <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
        </dsig:Transforms>  
        <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
        <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
      </hash>  
    </dependentAssembly>  
  </dependency>  
<publisherIdentity name="CN=DOMAINCONTROLLER\UserMe" issuerKeyHash="18312a18a21b215ecf4cdb20f5a0e0b0dd263c08" /><Signature Id="StrongNameSignature" xmlns="http://www.w3.org/2000/09/xmldsig#">  
…  
</Signature></r:issuer></r:license></msrel:RelData></KeyInfo></Signature></asmv1:assembly>  
```  
  
## 참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)