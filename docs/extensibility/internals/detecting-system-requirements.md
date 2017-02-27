---
title: "시스템 요구 사항 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "설치, VSPackage"
  - "시작 조건"
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
caps.latest.revision: 50
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 50
---
# 시스템 요구 사항 검색
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio가 설치 되어 있지 않으면 VSPackage 작동할 수 없습니다. Microsoft Windows Installer를 사용 하 여 VSPackage의 설치를 관리 하는 경우에 Visual Studio가 설치 되어 있는지 여부를 검색 하는 설치 관리자를 구성할 수 있습니다. 예를 들어 다른 요구 사항에 대 한 시스템을 확인 하 여, 특정 버전의 Windows 또는 특정 양의 RAM 구성할 수도 있습니다.  
  
## Visual Studio 버전 검색  
 버전의 Visual Studio가 설치 되어 있는지를 확인 하려면 설치 레지스트리 키의 값 \(REG\_DWORD\) 해당 폴더에는 1 인지는 다음 표에 나열 된 대로 확인 합니다. Visual Studio 버전의 계층 구조 않음을 유의 하십시오.  
  
1.  엔터프라이즈  
  
2.  2차원 형식  
  
3.  커뮤니티  
  
 "상위" 버전을 설치할 때 "lower" 버전의 경우와 해당 버전에 대 한 레지스트리 키 추가 됩니다. 즉, Enterprise edition이 설치 되어 있는 경우 설치 키 전문가 및 커뮤니티 버전 뿐만 아니라 엔터프라이즈에 대 한 1로 설정 됩니다. 따라서 필요한 "최고" 버전에 대해서만 확인 해야 합니다.  
  
> [!NOTE]
>  레지스트리 편집기의 64 비트 버전에서는 32 비트 키 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\ 아래에 표시 됩니다. Visual Studio 키는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\DevDiv\\vs\\Servicing\\ 아래입니다.  
  
|제품|Key|  
|--------|---------|  
|Visual Studio Enterprise 2015|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\DevDiv\\vs\\Servicing\\14.0\\enterprise|  
|Visual Studio Professional 2015|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\DevDiv\\vs\\Servicing\\14.0\\professional|  
|Visual Studio Community 2015|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\DevDiv\\vs\\Servicing\\14.0\\community|  
|Visual Studio 2015 Shell \(통합 및 격리\)|HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\DevDiv\\vs\\Servicing\\14.0\\isoshell|  
  
## Visual Studio가 실행 되는 경우를 검색 합니다.  
 VSPackage를 설치 하면 Visual Studio가 실행 되는 경우 VSPackage는 올바르게 등록할 수 없습니다. 설치 관리자는 Visual Studio가 실행 되는 시기를 검색 하 고 프로그램을 설치 하려면 다음을 거부 해야 합니다. Windows Installer 테이블 항목을 사용 하 여 이러한 검색 사용을 허용 하지 않습니다. 사용자 지정 작업을 다음과 같이 만듭니다 해야 하는 대신,: 사용 된 `EnumProcesses` Visual Studio를 닫을 수 있는 대화 상자를 표시 하는 devenv.exe 프로세스를 검색 하 고 다음 중 하나는 시작 조건을 또는 조건에 따라 사용 되는 설치 관리자 속성을 설정 하는 함수입니다.  
  
## 참고 항목  
 [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)