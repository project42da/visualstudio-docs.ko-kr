---
title: '&lt;assemblyIdentity&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce deployment manifest]
ms.assetid: f4a3bb83-c800-47d0-9905-9a5ae2486838
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 79ce08b434e5f26085b4f3f2285f7ae34bfb2d11
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ltassemblyidentitygt-element-clickonce-deployment"></a>&lt;assemblyIdentity&gt; 요소 (ClickOnce 배포)
주 어셈블리를 식별 하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      <assemblyIdentity    
   name   
   version  
   publicKeyToken  
   processorArchitecture  
    type  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `assemblyIdentity` 요소는 필수입니다. 자식 요소가 없는 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 요소. 정보 제공 목적으로 배포의 이해 하기 쉬운 이름을 식별합니다.<br /><br /> 경우 `name` 특수 문자가 포함 된 작은따옴표 또는 큰따옴표와 같은 응용 프로그램 활성화에 실패할 수 있습니다.|  
|`version`|필수 요소. 다음과 같은 형식의 어셈블리의 버전 번호를 지정: `major.minor.build.revision`합니다.<br /><br /> 응용 프로그램 업데이트에 업데이트 된 매니페스트에서이 값을 증가 해야 합니다.|  
|`publicKeyToken`|필수 요소. 배포 매니페스트 서명에 사용 된 공개 키의 sha-1 해시 값의 마지막 8 바이트를 나타내는 16 자리의 16 진수 문자열을 지정 합니다. 서명에 사용 되는 공개 키에 2048 비트 이어야 합니다. 큰 합니다.<br /><br /> 어셈블리 서명 하는 것이 좋지만 선택 사항,이 특성은 필요 합니다. 어셈블리 서명 되지 않은 경우에 자체 서명 된 어셈블리에서 값을 복사 하거나 "dummy" 모두 0 값을 사용 해야 합니다.|  
|`processorArchitecture`|필수 요소. 프로세서를 지정합니다. 유효한 값은 `msil` 모든 프로세서에 대해 `x86` 32 비트 Windows에 대 한 `IA64` 64 비트 Windows에 대 한 및 `Itanium` Intel 64 비트 Itanium 프로세서에 대 한 합니다.|  
|`type`|필수 요소. Windows-나란히 설치 기술을 비교 합니다. 허용 되는 유일한 값은 `win32`합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 코드 예제는 `assemblyIdentity` 요소에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트 합니다. 이 코드 예제는에 대해 제공 된 큰 예제의 일부는 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 항목입니다.  
  
```  
<!-- Identify the deployment. -->  
<assemblyIdentity   
  name="My Application Deployment.app"  
  version="1.0.0.0"  
  publicKeyToken="43cb1e8e7a352766"  
  language="neutral"  
  processorArchitecture="x86"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [\<assemblyIdentity > 요소](../deployment/assemblyidentity-element-clickonce-application.md)