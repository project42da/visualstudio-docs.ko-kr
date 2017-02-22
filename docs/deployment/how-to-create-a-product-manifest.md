---
title: "방법: 제품 매니페스트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "종속성, 사용자 지정 부트스트래퍼 패키지"
  - "필수 구성 요소, 사용자 지정 부트스트래퍼 패키지"
  - "제품 파일[ClickOnce]"
  - "제품 파일[Windows Installer]"
ms.assetid: 2d316aaa-8bc0-4ce5-90ab-23b3eac0b5dd
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: 제품 매니페스트 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램의 필수 구성 요소를 배포하기 위해 부트스트래퍼 패키지를 만들 수 있습니다.  부트스트래퍼 패키지에 포함되는 제품 매니페스트 파일은 하나 밖에 없지만 패키지 매니페스트는 각 로캘별로 포함됩니다.  패키지 매니페스트에는 패키지의 지역화 관련 항목이 포함되어 있습니다.  예를 들어 문자열, 최종 사용자 사용권 계약 및 언어 팩 등이 포함됩니다.  
  
 제품 매니페스트에 대한 자세한 내용은 [방법: 패키지 매니페스트 만들기](../deployment/how-to-create-a-package-manifest.md)를 참조하십시오.  
  
## 제품 매니페스트 만들기  
  
#### 제품 매니페스트를 만들려면  
  
1.  부트스트래퍼 패키지용 디렉터리를 만듭니다.  이 예제에서는 C:\\package를 사용합니다.  
  
2.  Visual Studio에서 `product.xml`이라는 새 XML 파일을 만들고 이 파일을 C:\\package 폴더에 저장합니다.  
  
3.  XML 네임스페이스 및 패키지의 제품 코드를 기술하는 다음 XML을 추가합니다.  제품 코드를 패키지의 고유 식별자로 바꿉니다.  
  
    ```  
    <Product  
    xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"   
    ProductCode="Custom.Bootstrapper.Package">  
    ```  
  
4.  패키지에 종속성이 있음을 지정하는 XML을 추가합니다.  이 예제에서는 Microsoft Windows Installer 3.1에 대한 종속성을 사용합니다.  
  
    ```  
    <RelatedProducts>  
        <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
      </RelatedProducts>  
    ```  
  
5.  부트스트래퍼 패키지에 있는 모든 파일을 나열하는 XML을 추가합니다.  이 예제에서는 패키지 파일 이름으로 CorePackage.msi를 사용합니다.  
  
    ```  
    <PackageFiles>  
        <PackageFile Name="CorePackage.msi"/>  
    </PackageFiles>  
    ```  
  
6.  CorePackage.msi 파일을 C:\\package 폴더로 복사 또는 이동합니다.  
  
7.  부트스트래퍼 명령을 사용하여 패키지를 설치하는 XML을 추가합니다.  부트스트래퍼는 자동으로 .msi 파일에 **\/qn** 플래그를 추가하여 이 파일이 자동으로 설치되도록 합니다.  파일의 확장명이 .exe인 경우 부트스트래퍼는 셸을 사용하여 .exe 파일을 실행합니다.  다음 XML에서는 CorePackage.msi에 대한 인수가 없지만 Arguments 특성에 명령줄 인수를 제공할 수는 있습니다.  
  
    ```  
    <Commands>  
        <Command PackageFile="CorePackage.msi" Arguments="">  
    ```  
  
8.  부트스트래퍼 패키지 설치 여부를 확인하는 다음 XML을 추가합니다.  제품 코드를 재배포 구성 요소의 GUID로 바꿉니다.  
  
    ```  
    <InstallChecks>  
        <MsiProductCheck   
            Property="IsMsiInstalled"   
            Product="{XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
    </InstallChecks>  
    ```  
  
9. 부트스트래퍼 구성 요소가 이미 설치되어 있는지 여부에 따라 부트스트래퍼 동작을 변경하는 XML을 추가합니다.  이 구성 요소가 설치되어 있으면 부트스트래퍼 패키지가 실행되지 않습니다.  이 구성 요소 설치에는 관리자 권한이 필요하므로 다음 XML에서는 현재 사용자가 관리자인지 확인합니다.  
  
    ```  
    <InstallConditions>  
        <BypassIf   
           Property="IsMsiInstalled"   
           Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
            Compare="ValueNotEqualTo" Value="True"  
            String="NotAnAdmin"/>  
    </InstallConditions>  
    ```  
  
10. 설치가 성공적이고 재부팅이 필요한 경우에 종료 코드를 설정하는 XML을 추가합니다.  다음 XML에서는 부트스트래퍼가 패키지 설치를 계속하지 않을 것임을 나타내는 Fail 및 FailReboot 종료 코드를 보여 줍니다.  
  
    ```  
    <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
    </ExitCodes>  
    ```  
  
11. 부트스트래퍼 명령 섹션을 종료하는 다음 XML을 추가합니다.  
  
    ```  
        </Command>  
    </Commands>  
    ```  
  
12. C:\\package 폴더를 Visual Studio 부트스트래퍼 디렉터리로 이동합니다.  Visual Studio 2010의 경우 이 디렉터리의 경로는 \\Program Files\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages입니다.  
  
## 예제  
 아래의 제품 매니페스트에는 사용자 지정 필수 구성 요소에 대한 설치 지침이 포함되어 있습니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Product  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  ProductCode="Custom.Bootstrapper.Package">  
  
  <RelatedProducts>  
    <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
  </RelatedProducts>  
  
  <PackageFiles>  
    <PackageFile Name="CorePackage.msi"/>  
  </PackageFiles>  
  
  <InstallChecks>  
    <MsiProductCheck Product="IsMsiInstalled"   
      Property="{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
  </InstallChecks>  
  
  <Commands>  
    <Command PackageFile="CorePackage.msi" Arguments="">  
  
      <InstallConditions>  
        <BypassIf Property="IsMsiInstalled"  
          Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
          Compare="ValueNotEqualTo" Value="True"  
         String="NotAnAdmin"/>  
      </InstallConditions>  
  
      <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
      </ExitCodes>  
    </Command>  
  </Commands>  
</Product>  
```  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)