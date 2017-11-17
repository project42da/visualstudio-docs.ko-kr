---
title: "&lt;entryPoint&gt; 요소 (ClickOnce 응용 프로그램) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#commandLine
- urn:schemas-microsoft-com:asm.v2#entryPoint
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <entryPoint> element [ClickOnce application manifest]
- manifests [ClickOnce], entryPoint element
ms.assetid: 10ad3083-10c1-4189-a870-9bba2eab244f
caps.latest.revision: "33"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: eb280684f0c06391bc6c0596093c01f260f685d3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ltentrypointgt-element-clickonce-application"></a>&lt;entryPoint&gt; 요소 (ClickOnce 응용 프로그램)
되어야 하는 어셈블리를 식별 될 때 실행이 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램이 클라이언트 컴퓨터에서 실행 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      <entryPoint  
   name  
>  
   <assemblyIdentity  
      name  
      version  
      processorArchitecture  
      language  
   />  
   <commandLine  
      file  
      parameters  
   />  
   <customHostRequired />  
   <customUX />  
</entryPoint>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `entryPoint` 요소는 필수이며 `urn:schemas-microsoft-com:asm.v2` 네임스페이스에 있습니다. 수 하나 `entryPoint` 응용 프로그램 매니페스트에서 정의 된 요소입니다.  
  
 `entryPoint` 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|선택 사항입니다. 이 값은.NET Framework에서 사용 되지 않습니다.|  
  
 `entryPoint`에 다음 요소가 있습니다.  
  
## <a name="assemblyidentity"></a>assemblyIdentity  
 필수 요소. 역할 `assemblyIdentity` 및 해당 특성에 정의 되었는지 [ \<y y > 요소](../deployment/assemblyidentity-element-clickonce-application.md)합니다.  
  
 `processorArchitecture` 이 요소의 특성 및 `processorArchitecture` 에 정의 된 특성과 `assemblyIdentity` 다른 위치에서 응용 프로그램 매니페스트 일치 해야 합니다.  
  
## <a name="commandline"></a>명령줄  
 필수 요소. 자식 이어야 합니다는 `entryPoint` 요소입니다. 자식 요소가 없는 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`file`|필수 요소. 에 대 한 시작 어셈블리에 대 한 로컬 참조는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. 이 값 앞에 슬래시 (/) 또는 백슬래시를 포함할 수 없습니다 (\\) 경로 구분 기호입니다.|  
|`parameters`|필수 요소. 진입점에서 수행할 동작을 설명 합니다. 유일한 유효 값은 `run`빈 문자열로 제공 되는 경우; `run` 것으로 간주 됩니다.|  
  
## <a name="customhostrequired"></a>customHostRequired  
 선택 사항입니다. 포함 하는 경우이 배포 사용자 지정 호스트 내부에 배포 하는 구성 요소에 포함 되도록 지정 하 고 독립 실행형 응용 프로그램을 되지 않습니다.  
  
 이 요소가 없으면는 `assemblyIdentity` 및 `commandLine` 요소 하지도 있어야 합니다. 인 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 하는 동안 유효성 검사 오류를 발생 시킵니다.  
  
 이 요소에는 특성과 하위 항목이 없습니다.  
  
## <a name="customux"></a>customUX  
 선택 사항입니다. 응용 프로그램 설치는 사용자 지정 설치 관리자에서 유지 관리 및 시작 메뉴 항목, 만드는 바로 가기를 추가 되거나 않는 프로그램 항목을 제거를 지정 합니다.  
  
```  
<customUX xmlns="urn:schemas-microsoft-com:clickonce.v1" />  
```  
  
 CustomUX 요소를 포함 하는 응용 프로그램 사용자 지정 설치 관리자를 사용 하는 제공 해야 합니다는 <xref:System.Deployment.Application.InPlaceHostingManager> 설치 작업을 수행 하는 클래스입니다. 이 요소와 응용 프로그램의 매니페스트 또는 setup.exe 필수 부트스트래퍼를 두 번 클릭 하 여 설치할 수 없습니다. 사용자 지정 설치 관리자 시작 메뉴, 바로 가기 항목과 프로그램 추가 / 제거 항목 만들 수 있습니다. 제공한 구독 id를 저장 해야 사용자 지정 설치 관리자 프로그램 추가 / 제거 항목을 만들지 않는 경우는 <xref:System.Deployment.Application.GetManifestCompletedEventArgs.SubscriptionIdentity%2A> 속성과 호출 하 여 나중에 응용 프로그램을 제거 하려면 사용자가 사용 된 <xref:System.Deployment.Application.InPlaceHostingManager.UninstallCustomUXApplication%2A> 메서드. 자세한 내용은 참조 [연습: ClickOnce 응용 프로그램에 대 한 사용자 지정 설치 관리자 만들기](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md)합니다.  
  
## <a name="remarks"></a>설명  
 이 요소에 대 한 어셈블리 및 진입점 지점을 식별는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다.  
  
 사용할 수 없습니다 `commandLine` 런타임 시 응용 프로그램에 매개 변수를 전달 합니다. 에 대 한 쿼리 문자열 매개 변수를 액세스할 수 있습니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 에서 응용 프로그램의 배포 <xref:System.AppDomain>합니다. 자세한 내용은 참조 [하는 방법: 온라인 ClickOnce 응용 프로그램에서 쿼리 문자열 정보 검색](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 `entryPoint` 요소에 대 한 응용 프로그램 매니페스트에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. 이 코드 예제는에 대해 제공 된 큰 예제의 일부는 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md) 항목입니다.  
  
```  
<!-- Identify the main code entrypoint. -->  
<!-- This code runs the main method in an executable assembly. -->  
  <entryPoint>  
    <assemblyIdentity   
      name="MyApplication"   
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)