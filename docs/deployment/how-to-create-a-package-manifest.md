---
title: "방법: 패키지 매니페스트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "패키지 파일[ClickOnce]"
  - "패키지 파일[Windows Installer]"
  - "필수 구성 요소, 사용자 지정 부트스트래퍼 패키지"
ms.assetid: 5aecc507-2764-42f2-ae6f-c227971cf0af
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 패키지 매니페스트 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램의 필수 구성 요소를 배포하기 위해 부트스트래퍼 패키지를 사용할 수 있습니다.  부트스트래퍼 패키지에 포함되는 제품 매니페스트 파일은 하나 밖에 없지만 패키지 매니페스트는 각 로캘별로 포함됩니다.  따라서 지역화된 여러 버전에서 공유되는 기능은 제품 매니페스트에 포함되어야 합니다.  
  
 패키지 매니페스트에 대한 자세한 내용은 [방법: 제품 매니페스트 만들기](../deployment/how-to-create-a-product-manifest.md)를 참조하십시오.  
  
## 패키지 매니페스트 만들기  
  
#### 패키지 매니페스트를 만들려면  
  
1.  부트스트래퍼 패키지용 디렉터리를 만듭니다.  이 예제에서는 C:\\package를 사용합니다.  
  
2.  이름에 로캘 이름\(예: 영어의 경우 en\)이 포함된 하위 디렉터리를 만듭니다.  
  
3.  Visual Studio에서 `package.xml`이라는 XML 파일을 만들고 이 파일을 C:\\package\\en 폴더에 저장합니다.  
  
4.  부트스트래퍼 패키지 이름, 지역화된 이 패키지 매니페스트의 문화권, 선택적 사용권 계약을 나열하는 XML을 추가합니다.  다음 XML에서는 뒤에 있는 요소에서 정의되는 변수 `DisplayName` 및 `Culture`를 사용합니다.  
  
    ```  
    <Package  
        xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
        Name="DisplayName"  
        Culture="Culture"  
        LicenseAgreement="eula.txt">  
    ```  
  
5.  로캘별 디렉터리에 있는 모든 파일을 나열하는 XML을 추가합니다.  다음 XML에서는 **en** 로캘에 적합한 eula.txt라는 파일을 사용합니다.  
  
    ```  
    <PackageFiles>  
      <PackageFile Name="eula.txt"/>  
    </PackageFiles>  
    ```  
  
6.  부트스트래퍼 패키지에 대해 지역화 가능한 문자열을 정의하는 XML을 추가합니다.  다음 XML에서는 en 로캘에 대한 오류 문자열을 추가합니다.  
  
    ```  
      <Strings>  
        <String Name="DisplayName">Custom Bootstrapper Package</String>  
        <String Name="CultureName">en</String>  
        <String Name="NotAnAdmin">You must be an administrator to install   
    this package.</String>  
        <String Name="GeneralFailure">A general error has occurred while   
    installing this package.</String>  
    </Strings>  
    ```  
  
7.  C:\\package 폴더를 Visual Studio 부트스트래퍼 디렉터리로 복사합니다.  Visual Studio 2010의 경우 이 디렉터리의 경로는 \\Program Files\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages입니다.  
  
## 예제  
 아래의 패키지 매니페스트에는 오류 메시지, 소프트웨어 사용 조건, 언어 팩 같은 로캘별 정보가 포함되어 있습니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Package  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  Name="DisplayName"  
  Culture="Culture"  
  LicenseAgreement="eula.txt">  
  
  <PackageFiles>  
    <PackageFile Name="eula.txt"/>  
  </PackageFiles>  
  
  <Strings>  
    <String Name="DisplayName">Custom Bootstrapper Package</String>  
    <String Name="Culture">en</String>  
    <String Name="NotAnAdmin">You must be an administrator to install this package.</String>  
    <String Name="GeneralFailure">A general error has occurred while   
installing this package.</String>  
  </Strings>  
</Package>  
```  
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)