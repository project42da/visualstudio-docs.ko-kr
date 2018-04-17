---
title: ClickOnce 관리 되지 않는 API 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- LaunchApplication [ClickOnce unmanaged]
- ClickOnce, unmanaged APIs
- CleanOnlineAppCache [ClickOnce unmanaged]
- CleanOnlineAppCacheW interface [ClickOnce unmanaged]
- GetDeploymentDataFromManifest [ClickOnce unmanaged]
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- cplusplus
ms.openlocfilehash: 8463976825d38c5ff5e8cb910df153737da9eeee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="clickonce-unmanaged-api-reference"></a>ClickOnce 관리되지 않는 API 참조
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dfshim.dll에서 관리 되지 않는 공용 Api를 지원 합니다.  
  
## <a name="cleanonlineappcache"></a>CleanOnlineAppCache  
 정리 하거나 모든 온라인 응용 프로그램에서 제거 된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 캐시 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않으면 실패를 나타내는 HRESULT를 반환 합니다. 관리 되는 예외를 발생 하는 경우 0x80020009 (DISP_E_EXCEPTION)를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 CleanOnlineAppCache 호출가 시작 되는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 서비스 아직 실행 하지 않은 경우.  
  
## <a name="getdeploymentdatafrommanifest"></a>GetDeploymentDataFromManifest  
 매니페스트 및 활성화 URL에서 배포 정보를 검색합니다.  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|형식|  
|---------------|-----------------|----------|  
|`pcwzActivationUrl`|에 대 한 포인터는 `ActivationURL`합니다.|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|에 대 한 포인터는 `PathToDeploymentManifest`합니다.|LPCWSTR|  
|`pwzApplicationIdentity`|반환 된 전체 응용 프로그램 id를 지정 하는 NULL로 끝나는 문자열을 받기 위한 버퍼에 대 한 포인터입니다.|LPWSTR|  
|`pdwIdentityBufferLength`|길이가 DWORD에 대 한 포인터는 `pwzApplicationIdentity` WCHARs 버퍼입니다. 여기에 NULL 종결 문자에 대 한 공간이 포함 됩니다.|LPDWORD|  
|`pwzProcessorArchitecture`|응용 프로그램 배포 매니페스트에서 프로세서 아키텍처를 지정 하는 NULL로 끝나는 문자열을 받기 위한 버퍼에 대 한 포인터입니다.|LPWSTR|  
|`pdwArchitectureBufferLength`|길이가 DWORD에 대 한 포인터는 `pwzProcessorArchitecture` WCHARs 버퍼입니다.|LPDWORD|  
|`pwzApplicationManifestCodebase`|응용 프로그램 매니페스트의 매니페스트에서 코드 베이스를 지정 하는 NULL로 끝나는 문자열을 받기 위한 버퍼에 대 한 포인터입니다.|LPWSTR|  
|`pdwCodebaseBufferLength`|길이가 DWORD에 대 한 포인터는 `pwzApplicationManifestCodebase` WCHARs 버퍼입니다.|LPDWORD|  
|`pwzDeploymentProvider`|NULL로 끝나는 문자열을 받기 위한 버퍼에 대 한 포인터 공급자를 지정 하는 배포 매니페스트, 있는 경우. 그렇지 않은 경우 빈 문자열이 반환 됩니다.|LPWSTR|  
|`pdwProviderBufferLength`|길이가 DWORD에 대 한 포인터는 `pwzProviderBufferLength`합니다.|LPDWORD|  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않으면 실패를 나타내는 HRESULT를 반환 합니다. 버퍼가 너무 작은 경우 HRESULTFROMWIN32(ERROR_INSUFFICIENT_BUFFER)를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 포인터를 null 이어야 합니다. `pcwzActivationUrl` 및 `pcwzPathToDeploymentManifest` 비어 있지 않아야 합니다.  
  
 호출자의 정품 인증 URL을 정리 합니다. 예를 들어 이스케이프 문자를 추가 필요한 위치 또는 쿼리 문자열을 제거 합니다.  
  
 호출자의 입력된 길이 제한 해야 합니다. 예를 들어 최대 URL 길이 2KB입니다.  
  
## <a name="launchapplication"></a>LaunchApplication  
 시작 하거나 배포 URL을 사용 하 여 응용 프로그램을 설치 합니다.  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|형식|  
|---------------|-----------------|----------|  
|`deploymentUrl`|배포 매니페스트의 URL이 포함 된 NULL로 끝나는 문자열에 대 한 포인터입니다.|LPCWSTR|  
|`data`|나중에 사용하기 위해 예약되어 있습니다. NULL 이어야 합니다.|LPVOID|  
|`flags`|나중에 사용하기 위해 예약되어 있습니다. 0 이어야 합니다.|DWORD|  
  
### <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않으면 실패를 나타내는 HRESULT를 반환 합니다. 관리 되는 예외를 발생 하는 경우 0x80020009 (DISP_E_EXCEPTION)를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>