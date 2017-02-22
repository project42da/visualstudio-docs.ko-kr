---
title: "ClickOnce 관리되지 않는 API 참조 | Microsoft Docs"
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
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "CleanOnlineAppCache[ClickOnce 관리되지 않는]"
  - "CleanOnlineAppCacheW 인터페이스[ClickOnce 관리되지 않는]"
  - "ClickOnce, 관리되지 않는 API"
  - "GetDeploymentDataFromManifest[ClickOnce 관리되지 않는]"
  - "LaunchApplication[ClickOnce 관리되지 않는]"
ms.assetid: ec002138-4054-456d-bcc1-79ac2f4a4fd7
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 관리되지 않는 API 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

dfshim.dll의 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 관리되지 않는 공용 API입니다.  
  
## CleanOnlineAppCache  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 캐시에서 모든 온라인 응용 프로그램을 정리하거나 제거합니다.  
  
### 반환 값  
 성공하면 S\_OK가 반환되고, 그렇지 않으면 실패를 나타내는 HRESULT가 반환됩니다.  관리되는 예외가 발생하면 0x80020009\(DISP\_E\_EXCEPTION\)가 반환됩니다.  
  
### 설명  
 CleanOnlineAppCache를 호출하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 서비스가 아직 실행되고 있지 않을 경우 이 서비스가 시작됩니다.  
  
## GetDeploymentDataFromManifest  
 매니페스트 및 활성화 URL에서 배포 정보를 검색합니다.  
  
### 매개 변수  
  
|Parameter|설명|형식|  
|---------------|--------|--------|  
|`pcwzActivationUrl`|`ActivationURL`에 대한 포인터입니다.|LPCWSTR|  
|`pcwzPathToDeploymentManifest`|`PathToDeploymentManifest`에 대한 포인터입니다.|LPCWSTR|  
|`pwzApplicationIdentity`|반환된 전체 응용 프로그램 ID를 지정하는 null로 끝나는 문자열을 받을 버퍼에 대한 포인터입니다.|LPWSTR|  
|`pdwIdentityBufferLength`|WCHAR에 있는 `pwzApplicationIdentity` 버퍼의 길이인 DWORD에 대한 포인터입니다.  여기에는 null로 끝나는 문자열을 위한 공간이 포함됩니다.|LPDWORD|  
|`pwzProcessorArchitecture`|매니페스트에서 응용 프로그램 배포의 프로세서 아키텍처를 지정하는 null로 끝나는 문자열을 받을 버퍼에 대한 포인터입니다.|LPWSTR|  
|`pdwArchitectureBufferLength`|WCHAR에 있는 `pwzProcessorArchitecture` 버퍼의 길이인 DWORD에 대한 포인터입니다.|LPDWORD|  
|`pwzApplicationManifestCodebase`|매니페스트에서 응용 프로그램 매니페스트의 코드베이스를 지정하는 null로 끝나는 문자열을 받을 버퍼에 대한 포인터입니다.|LPWSTR|  
|`pdwCodebaseBufferLength`|WCHAR에 있는 `pwzApplicationManifestCodebase` 버퍼의 길이인 DWORD에 대한 포인터입니다.|LPDWORD|  
|`pwzDeploymentProvider`|배포 공급자가 있을 경우 매니페스트에서 이를 지정하는 null로 끝나는 문자열을 받을 버퍼에 대한 포인터입니다.  그렇지 않으면 빈 문자열이 반환됩니다.|LPWSTR|  
|`pdwProviderBufferLength`|`pwzProviderBufferLength`의 길이인 DWORD에 대한 포인터입니다.|LPDWORD|  
  
### 반환 값  
 성공하면 S\_OK가 반환되고, 그렇지 않으면 실패를 나타내는 HRESULT가 반환됩니다.  버퍼가 너무 작을 경우 HRESULTFROMWIN32\(ERROR\_INSUFFICIENT\_BUFFER\)가 반환됩니다.  
  
### 설명  
 포인터는 null이 아니어야 합니다.  즉, `pcwzActivationUrl` 및 `pcwzPathToDeploymentManifest`는 비어 있지 않아야 합니다.  
  
 호출자는 활성화 URL을 정리해야 합니다.  예를 들어, 필요한 위치에 이스케이프 문자를 추가하거나 쿼리 문자열을 제거합니다.  
  
 호출자는 입력 길이를 제한해야 합니다.  예를 들어, 최대 URL 길이는 2KB입니다.  
  
## LaunchApplication  
 배포 URL을 사용하여 응용 프로그램을 시작하거나 설치합니다.  
  
### 매개 변수  
  
|Parameter|설명|형식|  
|---------------|--------|--------|  
|`deploymentUrl`|배포 매니페스트의 URL이 포함된 null로 끝나는 문자열에 대한 포인터입니다.|LPCWSTR|  
|`data`|다음에 사용하도록 예약됩니다.  null이어야 합니다.|LPVOID|  
|`flags`|다음에 사용하도록 예약됩니다.  0이어야 합니다.|DWORD|  
  
### 반환 값  
 성공하면 S\_OK가 반환되고, 그렇지 않으면 실패를 나타내는 HRESULT가 반환됩니다.  관리되는 예외가 발생하면 0x80020009\(DISP\_E\_EXCEPTION\)가 반환됩니다.  
  
## 참고 항목  
 <xref:System.Deployment.Application.DeploymentServiceCom.CleanOnlineAppCache%2A>