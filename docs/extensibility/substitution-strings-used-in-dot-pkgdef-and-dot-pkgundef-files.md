---
title: "사용 되는 대체 문자열입니다. Pkgdef 하 고 있습니다. Pkgundef 파일 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode, .pkgdef and .pkgundef files
ms.assetid: b1755d63-d794-4fd7-864b-70a9684881c2
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 9044821c2bfee0dba8ffa91f3d91afd565b8d957
ms.openlocfilehash: c64a760b821663ba488f6f9dab415bad13d6047d
ms.lasthandoff: 02/22/2017

---
# <a name="substitution-strings-used-in-pkgdef-and-pkgundef-files"></a>사용 되는 대체 문자열입니다. Pkgdef 하 고 있습니다. Pkgundef 파일
.pkgdef에 아래 나열 된 대체 문자열을 사용할 수 및 Visual Studio에 대해 정의한.pkgundef 파일 셸 응용 프로그램을 격리 합니다.  
  
## <a name="substitution-strings"></a>대체 문자열  
  
|문자열|설명|  
|------------|-----------------|  
|$=*찾아*$|값은 *찾아* 항목입니다. 레지스트리 항목 문자열은 백슬래시로 끝나는 경우 (\\), 레지스트리 하위 키의 기본 값이 사용 됩니다. 예를 들어, 대체 문자열 $= HKEY_CURRENT_USER\Environment\TEMP$ 현재 사용자의 임시 폴더에 확장 됩니다.|  
|$AppName $|AppEnv.dll 진입점에 전달 되는 응용 프로그램의 정규화 된 이름입니다. 정규화 된 이름은 응용 프로그램 이름, 밑줄 및 프로젝트.pkgdef 파일에서 ThisVersionDTECLSID 설정의 값으로도 기록 하 여 응용 프로그램 자동화 개체의 클래스 식별자 (CLSID) 구성 됩니다.|  
|$AppDataLocalFolder|이 응용 프로그램에 대 한 % LOCALAPPDATA % 아래 하위 폴더입니다.|  
|$BaseInstallDir $|전체 경로 Visual Studio가 설치 된 위치입니다.|  
|$CommonFiles $|값 % CommonProgramFiles % 환경 변수입니다.|  
|$MyDocuments $|현재 사용자의 내 문서 폴더의 전체 경로입니다.|  
|$PackageFolder $|응용 프로그램에 대 한 패키지 어셈블리 파일을 포함 하는 디렉터리의 전체 경로입니다.|  
|$ProgramFiles $|% ProgramFiles % 환경 변수의 값입니다.|  
|$RootFolder $|응용 프로그램의 루트 디렉터리의 전체 경로입니다.|  
|$RootKey $|응용 프로그램에 대 한 루트 레지스트리 키입니다. 기본적으로 루트 주의 하십시오에 있으며\\*CompanyName*\\*ProjectName*\\*VersionNumber* (응용 프로그램이 실행 중인 _Config에 추가 됩니다이 키). RegistryRoot 값에 의해 설정 되는 *SolutionName*.pkgdef 파일.<br /><br /> 응용 프로그램 하위 키 아래에 레지스트리 값을 검색 하는 $RootKey$ 문자열을 사용할 수 있습니다. 예를 들어, 문자열 "$$RootKey$ \AppIcon$ =" 응용 프로그램 루트 하위 키 아래에 있는 AppIcon 항목의 값을 반환 합니다.<br /><br /> 파서는은.pkgdef 파일을 순서 대로 처리 하 고 해당 항목이 이전에 정의 된 경우에 응용 프로그램 하위 키 아래에 레지스트리 항목에 액세스할 수 있습니다.|  
|$ShellFolder $|전체 경로 Visual Studio가 설치 된 위치입니다.|  
|$System $|Windows\system32 폴더입니다.|  
|$WINDIR $|Windows 폴더입니다.|  
  
 파서는 대체 문자열을 인식 하지 못합니다 또는 대체 문자열의 해당 부분에서 수행 되지 않는 한 다음 레지스트리 항목 또는 환경 변수 값을 결정할 수 없습니다.
