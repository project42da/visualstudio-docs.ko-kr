---
title: "&lt;compatibleFrameworks&gt; 요소 (ClickOnce 배포) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <compatibleFrameworks> element [ClickOnce deployment manifest]
ms.assetid: f6c3ee55-9e65-403d-8664-3ebde872c7d4
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: bb8c31d37bd37f4e2db8415ef1815caec0ec185a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ltcompatibleframeworksgt-element-clickonce-deployment"></a>&lt;compatibleFrameworks&gt; 요소 (ClickOnce 배포)
이 응용 프로그램이 설치 및 실행할 수 있는 .NET Framework의 버전을 식별합니다.  
  
> [!NOTE]
>  [MageUI.exe](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) 지원 하지 않습니다는 `compatibleFrameworks` 요소 응용 프로그램 매니페스트를 저장할 때 사용 하 여 인증서로 서명 된 이미 [MageUI.exe](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)합니다. 대신, [Mage.exe](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)를 사용해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<compatibleFrameworks  
      SupportUrl>   
   <framework  
      targetVersion  
      profile  
      supportedRuntime  
   />   
</ compatibleFrameworks>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `compatibleFrameworks` 배포 매니페스트에 대상으로 하는 요소는 필수는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 에서 제공 하는 런타임 [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] 이상. `compatibleFrameworks` 요소 하나 이상 포함 `framework` 이 응용 프로그램 실행 될 수 있는.NET Framework 버전을 지정 하는 요소입니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 런타임 첫 번째 응용 프로그램을 실행 합니다 사용 가능한 `framework` 이 목록에 있습니다.  
  
 다음 표에서 특성을 나열 하는 `compatibleFrameworks` 요소는 지원 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`S` `upportUrl`|선택 사항입니다. 호환 되는 기본.NET Framework 버전을 다운로드할 수 있는 URL을 지정 합니다.|  
  
## <a name="framework"></a>프레임워크  
 필수 요소. 다음 표에서 특성을 나열 하는 `framework` 요소를 지원 합니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`targetVersion`|필수 요소. 대상.NET Framework의 버전 번호를 지정합니다.|  
|`profile`|필수 요소. 대상.NET Framework의 프로필을 지정합니다.|  
|`supportedRuntime`|필수 요소. 대상.NET Framework와 관련 된 런타임 버전 번호를 지정 합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 코드 예제는 `compatibleFrameworks` 요소에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트 합니다. 이 배포에서 실행할 수는 [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]합니다. 또한에서 실행할 수는 [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] 의 상위 집합 이므로 [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)]합니다.  
  
```  
<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
  <framework   
      targetVersion="4.0"   
      profile="Client"   
      supportedRuntime="4.0.30319" />  
</compatibleFrameworks>  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)