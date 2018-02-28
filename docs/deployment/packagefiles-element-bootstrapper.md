---
title: "&lt;PackageFiles&gt; 요소 (부트스트래퍼) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <PackageFiles> element [bootstrapper]
ms.assetid: 3ea252d7-18a3-47d8-af83-47feebcfe82b
caps.latest.revision: 
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 25ba72b511782c450b882826a3e3af94a14f6e20
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltpackagefilesgt-element-bootstrapper"></a>&lt;PackageFiles&gt; 요소 (부트스트래퍼)
`PackageFiles` 요소에 포함 되어 `PackageFile` 의 결과로 실행 설치 패키지를 정의 하는 요소는 `Command` 요소입니다.  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `PackageFiles` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`CopyAllPackageFiles`|선택 사항입니다. 경우로 설정 `false`, 설치 관리자에서 참조 하는 파일을 다운로드만 `Command` 요소입니다. 경우 설정 `true`, 모든 파일을 다운로드 합니다.<br /><br /> 경우로 설정 `IfNotHomesite`, 설치 관리자가 작동 하는 동일한 처럼 `False` 경우 `ComponentsLocation` 로 설정 된 `HomeSite`, 그렇지 않은 경우는 동일 하 게 작동 하 고 처럼 `True`합니다. 이 설정은 HomeSite 시나리오에서 고유한 동작을 실행 하는 부트스트래퍼 패키지를 허용 하도록 유용할 수 있습니다.<br /><br /> 기본값은 `true`입니다.|  
  
## <a name="packagefile"></a>PackageFile  
 `PackageFile` 의 자식인 요소는 `PackageFiles` 요소입니다. A `PackageFiles` 요소가 하나 이상 있어야 `PackageFile` 요소입니다.  
  
 `PackageFile`다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수. 패키지 파일의 이름입니다. 이 이름은 하는 `Command` 요소는 패키지를 설치 하는 조건을 정의 될 때 참조 합니다. 이 값은 키로 사용은 `Strings` 와 같은 도구는 지역화 된 이름을 검색 하는 테이블 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지를 설명 하기 위해 사용 됩니다.|  
|`HomeSite`|선택 사항입니다. 설치 관리자에 포함 되지 않은 경우 원격 서버에서 패키지의 위치입니다.|  
|`CopyOnBuild`|선택 사항입니다. 부트스트래퍼 빌드 시 디스크에 패키지 파일을 복사 해야 하는지 여부를 지정 합니다. 기본값은 true입니다.|  
|`PublicKey`|패키지의 인증서 서명자의 공개 키 암호화입니다. 필요한 경우 `HomeSite` 사용 그렇지 않으면 선택 사항입니다.|  
|`Hash`|선택 사항입니다. 패키지 파일의 SHA1 해시 합니다. 설치 중에 파일의 무결성을 확인 하는이 사용 됩니다. 패키지 파일에서 동일한 해시를 계산할 수 없으면, 패키지가 설치 되지 않습니다.|  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 패키지에 대 한 정의 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 재배포 가능 패키지 및 해당 종속성 Windows Installer 등입니다.  
  
```  
<PackageFiles>  
    <PackageFile Name="instmsia.exe" HomeSite="InstMsiAExe" PublicKey="3082010A0282010100AA99BD39A81827F42B3D0B4C3F7C772EA7CBB5D18C0DC23A74D793B5E0A04B3F595ECE454F9A7929F149CC1A47EE55C2083E1220F855F2EE5FD3E0CA96BC30DEFE58C82732D08554E8F09110BBF32BBE19E5039B0B861DF3B0398CB8FD0B1D3C7326AC572BCA29A215908215E277A34052038B9DC270BA1FE934F6F335924E5583F8DA30B620DE5706B55A4206DE59CBF2DFA6BD154771192523D2CB6F9B1979DF6A5BF176057929FCC356CA8F440885558ACBC80F464B55CB8C96774A87E8A94106C7FF0DE968576372C36957B443CF323A30DC1BE9D543262A79FE95DB226724C92FD034E3E6FB514986B83CD0255FD6EC9E036187A96840C7F8E203E6CF050203010001"/>  
    <PackageFile Name="WindowsInstaller-KB884016-v2-x86.exe" HomeSite="Msi30Exe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetfx.exe" HomeSite="DotNetFXExe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
    <PackageFile Name="dotnetchk.exe"/>  
</PackageFiles>  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<제품 > 요소](../deployment/product-element-bootstrapper.md)   
 [\<패키지 > 요소](../deployment/package-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)