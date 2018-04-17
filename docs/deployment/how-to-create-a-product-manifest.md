---
title: '방법: 제품 매니페스트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- product files [ClickOnce]
- product files [Windows Installer]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper package
ms.assetid: 2d316aaa-8bc0-4ce5-90ab-23b3eac0b5dd
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 116a54bae39738f95503ae9ca6e6cbac45c2db47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-product-manifest"></a>방법: 제품 매니페스트 만들기
응용 프로그램에 대 한 필수 구성 요소를 배포 하려면 부트스트래퍼 패키지를 만들 수 있습니다. 부트스트래퍼 패키지는 각 로캘에 대 한 패키지 매니페스트를 제외한 단일 제품 매니페스트 파일을 포함합니다. 패키지 매니페스트의 패키지의 지역화 관련 항목이 포함 되어 있습니다. 문자열, 최종 사용자 사용권 계약 및 언어 팩이 포함 됩니다.  
  
 제품 매니페스트에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 패키지 매니페스트 만들기](../deployment/how-to-create-a-package-manifest.md)합니다.  
  
## <a name="creating-the-product-manifest"></a>제품 매니페스트 만들기  
  
#### <a name="to-create-the-product-manifest"></a>제품 매니페스트를 만들려면  
  
1.  부트스트래퍼 패키지에 대 한 디렉터리를 만듭니다. 이 예제에서는 C:\package를 사용 합니다.  
  
2.  Visual Studio에서 라는 새 XML 파일을 만듭니다 `product.xml`, C:\package 폴더에 저장 합니다.  
  
3.  패키지에 대 한 XML 네임 스페이스 및 제품 코드를 설명 하는 다음 XML을 추가 합니다. 패키지에 대 한 고유 식별자가 있는 제품 코드를 바꿉니다.  
  
    ```  
    <Product  
    xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"   
    ProductCode="Custom.Bootstrapper.Package">  
    ```  
  
4.  패키지에 종속 되어 있는지를 지정 하는 XML을 추가 합니다. 이 예제에서는 Microsoft Windows Installer 3.1에 종속성을 사용 합니다.  
  
    ```  
    <RelatedProducts>  
        <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
      </RelatedProducts>  
    ```  
  
5.  부트스트래퍼 패키지에 있는 모든 파일을 나열 하는 XML을 추가 합니다. 이 예제에서는 CorePackage.msi 패키지 파일 이름을 사용 합니다.  
  
    ```  
    <PackageFiles>  
        <PackageFile Name="CorePackage.msi"/>  
    </PackageFiles>  
    ```  
  
6.  복사 하거나 CorePackage.msi 파일을 C:\package 폴더로 이동 합니다.  
  
7.  부트스트래퍼 명령을 사용 하 여 패키지를 설치 하는 XML을 추가 합니다. 부트스트래퍼가 자동으로 추가 **/qn** 자동으로 설치 하는.msi 파일을 플래그 합니다. 파일 확장명이.exe 인 경우 부트스트래퍼 셸을 사용 하 여.exe 파일을 실행 합니다. 다음 XML CorePackage.msi를 인수 없이 보여주지만 인수 특성에 명령줄 인수를 삽입할 수 있습니다.  
  
    ```  
    <Commands>  
        <Command PackageFile="CorePackage.msi" Arguments="">  
    ```  
  
8.  부트스트래퍼 패키지가 설치 되어 있는지 확인 하려면 다음 XML을 추가 합니다. 재배포 가능 구성 요소에 대 한 GUID를 가진 제품 코드를 바꿉니다.  
  
    ```  
    <InstallChecks>  
        <MsiProductCheck   
            Property="IsMsiInstalled"   
            Product="{XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
    </InstallChecks>  
    ```  
  
9. 부트스트래퍼 구성 요소를 이미 설치한 경우에 따라 부트스트래퍼 동작을 변경 하는 XML을 추가 합니다. 요소를 설치 하면 부트스트래퍼 패키지가 실행 되지 않습니다. 다음 XML이 구성이 요소 관리자 권한이 필요 하므로 현재 사용자가 관리자 인지 확인 합니다.  
  
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
  
10. 성공적으로 설치 하 고 다시 시작이 필요한 경우 종료 코드를 설정 하는 XML을 추가 합니다. 다음 XML 실패 하 고 FailReboot 부트스트래퍼 패키지 설치 계속 되지 것입니다 나타냅니다는 코드를 종료 하는 방법을 보여 줍니다.  
  
    ```  
    <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
    </ExitCodes>  
    ```  
  
11. 부트스트래퍼 명령에 대 한 섹션을 종료 하려면 다음 XML을 추가 합니다.  
  
    ```  
        </Command>  
    </Commands>  
    ```  
  
12. Visual Studio 부트스트래퍼 디렉터리로 C:\package 폴더를 이동 합니다. Visual Studio 2010 files\microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages 디렉터리입니다.  
  
## <a name="example"></a>예제  
 제품 매니페스트는 사용자 지정 필수 구성 요소에 대 한 설치 지침을 포함합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)