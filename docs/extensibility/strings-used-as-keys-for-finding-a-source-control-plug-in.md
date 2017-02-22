---
title: "소스 제어 플러그 인을 찾기 위한 키로 사용 되는 문자열 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인을 쉽게 찾기 위해 사용 되는 문자열"
ms.assetid: c1e31f76-42a1-4c3d-afb2-664044ef12fd
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 소스 제어 플러그 인을 찾기 위한 키로 사용 되는 문자열
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 문자열은 정보를 찾기 위해 소스 제어 플러그 인 레지스트리를 액세스 하기 위한 키입니다.  
  
 `STR_SCC_PROVIDER_REG_LOCATION`, `STR_PROVIDERREGKEY`, `STR_SCCPROVIDERPATH`, 및 `STR_SCCPROVIDERNAME` 은 레지스트리 키 또는 값이 Visual Studio에 대 한 소스 제어 플러그 인으로 DLL을 등록 하는 데 사용 합니다.  
  
 `SCC_PROJECTNAME_KEY`, `SCC_PROJECTAUX_KEY`, `SCC_KEY, SCC_FILE_SIGNATURE`, 및 `SCC_STATUS_FILE` 는 MSSCCPRJ의 서식을 설명 하는 데 사용 됩니다. SCC 파일입니다.  
  
## 문자열 키 및 값  
  
|키|값|  
|-------|-------|  
|`STR_SCC_PROVIDER_REG_LOCATION`|Software\\SourceCodeControlProvider|  
|`STR_PROVIDERREGKEY`|ProviderRegKey|  
|`STR_SCCPROVIDERPATH`|SCCServerPath|  
|`STR_SCCPROVIDERNAME`|SCCServerName|  
|`STR_SCC_INI_SECTION`|소스 코드 제어|  
|`STR_SCC_INI_KEY`|SourceCodeControlProvider|  
|`SCC_PROJECTNAME_KEY`|SCC\_Project\_Name|  
|`SCC_PROJECTAUX_KEY`|SCC\_Aux\_Path|  
|`SCC_STATUS_FILE`|MSSCCPRJ 합니다. 소스 코드 제어|  
|`SCC_KEY`|소스 코드 제어|  
|`SCC_FILE_SIGNATURE`|소스 코드 제어 파일|  
|`SCC_NSE`|네임 스페이스 확장|  
|`SCC_NSE_PREFIX`|프로토콜 접두사|  
|`SCC_NSE_DisableOpenSCC`|DisableOpenFromSourceControl|  
|`STR_SCCHELPCOLLECTION`|Helpcollection의|  
|`STR_UI_LANGUAGE`|UILanguage|  
|`STR_SRCSAFE_ROOT_KEY`|Software\\Microsoft\\SourceSafe|  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [방법: 소스 제어 플러그 인 설치](../extensibility/internals/how-to-install-a-source-control-plug-in.md)   
 [MSSCCPRJ 합니다. SCC 파일](../extensibility/mssccprj-scc-file.md)