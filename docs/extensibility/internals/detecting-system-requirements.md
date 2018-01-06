---
title: "시스템 요구 사항 검색 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
caps.latest.revision: "50"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: dc16c51b72ced37072c4ddf6d47bf347cf57c0f8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="detecting-system-requirements"></a>시스템 요구 사항 검색
VSPackage는 Visual Studio를 설치 하지 않으면 작동 하지 않습니다. Microsoft Windows Installer를 사용 하 여 VSPackage의 설치를 관리 하는 경우 Visual Studio 설치 되어 있는지 여부를 검색 하는 설치 관리자를 구성할 수 있습니다. 예를 들어 다른 요구 사항에 대 한 시스템을 확인 하 여, 특정 버전의 Windows 또는 특정 양의 RAM 구성할 수도 있습니다.  
  
## <a name="detecting-visual-studio-editions"></a>Visual Studio 버전을 검색합니다.  
 버전의 Visual Studio가 설치 되어 있는지를 확인 하려면 설치 레지스트리 키의 값 (REG_DWORD) 해당 폴더에는 1 인지는 다음 표에 나열 된 대로 확인 합니다. Visual Studio 버전의 계층 구조 있다는 것을 참고:  
  
1.  엔터프라이즈  
  
2.  2차원 형식  
  
3.  커뮤니티  
  
 "상위" 버전을 설치할 때 "lower" 버전의 경우와 해당 버전에 대 한 레지스트리 키 추가 됩니다. 즉, Enterprise edition이 설치는 설치 키 엔터프라이즈에 대 한 것은 물론 Professional 및 Community 버전 1로 설정 됩니다. 따라서 필요한 "가장 높은" edition에 대해서만 확인 해야 합니다.  
  
> [!NOTE]
>  레지스트리 편집기의 64 비트 버전에서 32 비트 키 아래에 표시 됩니다 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\\합니다. Visual Studio 키는 HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing 아래\\합니다.  
  
|제품|Key|  
|-------------|---------|  
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|  
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|  
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|  
|Visual Studio 2015 Shell (통합 및 격리)|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|  
  
## <a name="detecting-when-visual-studio-is-running"></a>Visual Studio가 실행 되는 경우를 검색 합니다.  
 VSPackage에서 VSPackage를 설치할 때 Visual Studio를 실행 중인 경우 올바르게 등록할 수 없습니다. 설치 관리자는 Visual Studio가 실행 되는 시기를 검색 하 고 프로그램을 설치 하려면 다음을 거부 해야 합니다. Windows Installer 이러한 검색이 사용 하도록 설정 하려면 테이블 항목을 사용할 수 없습니다. 대신 만들어야 사용자 지정 작업을 다음과 같이: 사용 된 `EnumProcesses` 닫기 메시지를 표시 하는 대화 상자를 표시 하는 devenv.exe 프로세스를 감지 하 여 시작 조건 또는 조건에 따라 사용 되는 설치 관리자 속성을 설정 하거나 다음 함수 Visual Studio 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Installer를 사용하여 VSPackage 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)