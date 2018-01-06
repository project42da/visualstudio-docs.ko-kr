---
title: "&lt;assemblyIdentity&gt; 요소 (ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <assemblyIdentity> element [ClickOnce application manifest]
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
caps.latest.revision: "20"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: b731522897512300459a32f8e01c4d54277eaa5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;assemblyIdentity&gt; 요소 (ClickOnce 응용 프로그램)
에 배포 된 응용 프로그램을 식별 한 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      <assemblyIdentity   
   name  
   version  
   publicKeyToken  
   processorArchitecture  
   language  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `assemblyIdentity` 요소는 필수입니다. 자식 요소가 없는 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Name`|필수. 응용 프로그램의 이름을 식별합니다.<br /><br /> 경우 `Name` 특수 문자가 포함 된 작은따옴표 또는 큰따옴표와 같은 응용 프로그램 활성화에 실패할 수 있습니다.|  
|`Version`|필수. 다음 형식으로 응용 프로그램의 버전 번호를 지정합니다.`major.minor.build.revision`|  
|`publicKeyToken`|선택 사항입니다. 마지막 8 바이트를 나타내는 16 자 16 진수 문자열을 지정 된 `SHA-1` 응용 프로그램이 나 어셈블리 서명에 사용 된 공개 키의 해시 값입니다. 카탈로그에 서명 하는 데 사용 되는 공개 키에 2048 비트 이어야 합니다. 큰 합니다.<br /><br /> 어셈블리 서명 하는 것이 좋지만 선택 사항,이 특성은 필요 합니다. 어셈블리 서명 되지 않은 경우에 자체 서명 된 어셈블리에서 값을 복사 하거나 "dummy" 모두 0 값을 사용 해야 합니다.|  
|`processorArchitecture`|필수. 프로세서를 지정합니다. 유효한 값은 `msil` 모든 프로세서에 대해 `x86` 32 비트 Windows에 대 한 `IA64` 64 비트 Windows에 대 한 및 `Itanium` Intel 64 비트 Itanium 프로세서에 대 한 합니다.|  
|`language`|필수. 두 부분 언어 코드를 식별 합니다. (예를 들어 `en-US`)의 어셈블리. 이 요소는는 `asmv2` 네임 스페이스입니다. 기본값은 지정 하지 않으면 `neutral`합니다.|  
  
## <a name="examples"></a>예제  
  
### <a name="description"></a>설명  
 다음 코드 예제는 `assemblyIdentity` 요소에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 매니페스트 합니다. 이 코드 예제는에 제공 된 큰 예제의 일부 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)합니다.  
  
### <a name="code"></a>코드  
  
```  
<asmv1:assemblyIdentity   
  name="My Application Deployment.exe"   
  version="1.0.0.0"   
  publicKeyToken="43cb1e8e7a352766"   
  language="neutral"   
  processorArchitecture="x86"   
  type="win32" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)   
 [\<assemblyIdentity > 요소](../deployment/assemblyidentity-element-clickonce-deployment.md)