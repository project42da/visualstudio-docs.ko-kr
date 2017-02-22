---
title: "&lt;PackageFiles&gt; 요소(부트스트래퍼) | Microsoft Docs"
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
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<PackageFiles> 요소[부트스트래퍼]"
ms.assetid: 3ea252d7-18a3-47d8-af83-47feebcfe82b
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;PackageFiles&gt; 요소(부트스트래퍼)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`PackageFiles` 요소에는 `Command` 요소의 결과로 실행되는 설치 패키지를 정의하는 `PackageFile` 요소가 들어 있습니다.  
  
## 구문  
  
```  
<PackageFiles  
    CopyAllPackageFiles  
>  
    <PackageFile   
        Name  
        HomeSite  
        CopyOnBuild  
        PublicKey  
        Hash  
    />  
</PackageFiles>  
```  
  
## 요소 및 특성  
 `PackageFiles` 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`CopyAllPackageFiles`|선택적 요소.  `false`로 설정되면 설치 관리자는 `Command` 요소에서 참조된 파일만 다운로드하고  `true`로 설정되면 모든 파일을 다운로드합니다.<br /><br /> `IfNotHomesite`로 설정되면 설치 관리자는 `ComponentsLocation`이 `HomeSite`로 설정된 경우 `False`인 것처럼 작동하고 그렇지 않은 경우 `True`인 것처럼 작동합니다.  HomeSite 시나리오에서 고유한 동작을 실행하기 위한 부트스트래퍼인 패키지를 허용하는 데 이 설정이 유용할 수 있습니다.<br /><br /> 기본값은 `true`입니다.|  
  
## PackageFile  
 `PackageFile` 요소는 `PackageFiles` 요소의 자식입니다.  `PackageFiles` 요소에는 `PackageFile` 요소가 적어도 한 개 있어야 합니다.  
  
 `PackageFile`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Name`|필수 요소.  패키지 파일의 이름입니다.  이 이름은 패키지를 설치할 조건을 정의할 때 `Command` 요소에서 참조하는 이름입니다.  이 값은 `Strings` 테이블에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 같은 도구로 패키지를 설명하는 데 사용할 지역화된 이름을 검색하기 위한 키로도 사용됩니다.|  
|`HomeSite`|선택적 요소.  패키지가 설치 관리자에 포함되지 않은 경우 원격 서버에 있는 패키지의 위치입니다.|  
|`CopyOnBuild`|선택적 요소.  빌드할 때 부트스트래퍼가 패키지 파일을 디스크에 복사할지 여부를 지정합니다.  기본값은 true입니다.|  
|`PublicKey`|패키지 인증서 서명자의 암호화된 공개 키입니다.  `HomeSite`를 사용하는 경우 필수적 요소이고, 그렇지 않으면 선택적 요소입니다.|  
|`Hash`|선택적 요소.  패키지 파일의 SHA1 해시입니다.  이 특성은 설치 시 파일의 무결성을 확인하는 데 사용됩니다.  패키지 파일에서 동일한 해시를 계산할 수 없으면 패키지가 설치되지 않습니다.|  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 재배포 가능 패키지와 Windows Installer 같은 종속 항목에 대한 패키지를 정의합니다.  
  
```  
<PackageFiles>  
    <PackageFile Name="instmsia.exe" HomeSite="InstMsiAExe" PublicKey="3082010A0282010100AA99BD39A81827F42B3D0B4C3F7C772EA7CBB5D18C0DC23A74D793B5E0A04B3F595ECE454F9A7929F149CC1A47EE55C2083E1220F855F2EE5FD3E0CA96BC30DEFE58C82732D08554E8F09110BBF32BBE19E5039B0B861DF3B0398CB8FD0B1D3C7326AC572BCA29A215908215E277A34052038B9DC270BA1FE934F6F335924E5583F8DA30B620DE5706B55A4206DE59CBF2DFA6BD154771192523D2CB6F9B1979DF6A5BF176057929FCC356CA8F440885558ACBC80F464B55CB8C96774A87E8A94106C7FF0DE968576372C36957B443CF323A30DC1BE9D543262A79FE95DB226724C92FD034E3E6FB514986B83CD0255FD6EC9E036187A96840C7F8E203E6CF050203010001"/>  
    <PackageFile Name="WindowsInstaller-KB884016-v2-x86.exe" HomeSite="Msi30Exe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetfx.exe" HomeSite="DotNetFXExe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetchk.exe"/>  
</PackageFiles>  
```  
  
## 참고 항목  
 [\<Product\> 요소](../deployment/product-element-bootstrapper.md)   
 [\<Package\> 요소](../deployment/package-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)