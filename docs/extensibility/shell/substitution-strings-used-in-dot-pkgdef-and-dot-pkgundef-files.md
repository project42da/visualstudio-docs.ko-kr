---
title: "사용 되는 대체 문자열입니다. Pkgdef 및 합니다. Pkgundef 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode, .pkgdef and .pkgundef files
ms.assetid: b1755d63-d794-4fd7-864b-70a9684881c2
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6144c0200c03776ead9e7dc7f46b5e9e707b6e82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="substitution-strings-used-in-pkgdef-and-pkgundef-files"></a>사용 되는 대체 문자열입니다. Pkgdef 및 합니다. Pkgundef 파일
.pkgdef에서 아래 나열 된 대체 문자열을 사용 하 여.pkgundef 파일에서 Visual Studio에 대해 정의한 격리 셸 응용 프로그램 및입니다.  
  
## <a name="substitution-strings"></a>대체 문자열  
  
|문자열|설명|  
|------------|-----------------|  
|$=*찾아*$|값은 *찾아* 항목입니다. 레지스트리 항목 문자열이 백슬래시 끝나는 경우 (\\), 레지스트리 하위 키의 기본 값이 사용 됩니다. 예를 들어, 대체 문자열 $= HKEY_CURRENT_USER\Environment\TEMP$ 현재 사용자의 임시 폴더에 확장 됩니다.|  
|$AppName $|AppEnv.dll 진입점에 전달 되는 응용 프로그램의 정규화 된 이름입니다. 응용 프로그램 이름, 밑줄 및 프로젝트.pkgdef 파일에 있는 ThisVersionDTECLSID 설정의 값으로도 기록 되는 응용 프로그램 자동화 개체의 클래스 식별자 (CLSID)의 정규화 된 이름은 구성 됩니다.|  
|$AppDataLocalFolder|이 응용 프로그램에 대 한 % LOCALAPPDATA % 아래 하위 폴더입니다.|  
|$BaseInstallDir $|Visual Studio 설치 된 위치의 전체 경로입니다.|  
|$CommonFiles $|값 % CommonProgramFiles % 환경 변수입니다.|  
|$MyDocuments $|현재 사용자의 내 문서 폴더의 전체 경로입니다.|  
|$PackageFolder $|응용 프로그램에 대 한 패키지 어셈블리 파일을 포함 하는 디렉터리의 전체 경로입니다.|  
|$ProgramFiles $|% ProgramFiles % 환경 변수의 값입니다.|  
|$RootFolder $|응용 프로그램의 루트 디렉터리의 전체 경로입니다.|  
|$RootKey $|응용 프로그램에 대 한 루트 레지스트리 키입니다. 기본적으로 루트가 주의 하십시오\\*CompanyName*\\*ProjectName*\\*VersionNumber* (때 응용 프로그램이 실행 중인, _Config이이 키에 추가 됩니다). RegistryRoot 값에 의해 설정 됩니다는 *SolutionName*.pkgdef 파일.<br /><br /> 응용 프로그램 하위 키에서 레지스트리 값을 검색 하려면 $RootKey$ 문자열을 사용할 수 있습니다. 예를 들어 문자열 "$= $RootKey$ \AppIcon$" 응용 프로그램 루트의 하위 키 아래 AppIcon 항목의 값을 반환 합니다.<br /><br /> 파서는은.pkgdef 파일을 순서 대로 처리 하 고 해당 항목이 이전에 정의 된 경우에 응용 프로그램 하위 키 아래에 레지스트리 항목에 액세스할 수 있습니다.|  
|$ShellFolder $|Visual Studio 설치 된 위치의 전체 경로입니다.|  
|$System $|Windows\system32 폴더입니다.|  
|$WINDIR $|Windows 폴더입니다.|  
  
 파서가 대체 문자열을 인식 하지 못합니다 경우 문자열의 해당 부분을 대체를 수행 하지 않는 한 다음 레지스트리 항목 또는 환경 변수 값을 결정할 수 없습니다.