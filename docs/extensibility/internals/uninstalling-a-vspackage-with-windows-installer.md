---
title: "Windows Installer VSPackage 제거 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- packages, uninstalling
- VSPackages, uninstalling
- uninstalling VSPackages
ms.assetid: c4575ac7-82da-4af8-a375-ea756a101fbf
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9b71c977fcc616c6d9cf30b78c9fd7610f11bcd4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="uninstalling-a-vspackage-with-windows-installer"></a>Windows Installer VSPackage를 제거합니다.
대부분의 경우 Windows Installer를 제거할 수 VSPackage에서 방금 수행한 VSPackage를 설치 하려면 "취소"입니다. 설명 하는 사용자 지정 동작 [명령을 해야 수를 실행 한 후 설치](../../extensibility/internals/commands-that-must-be-run-after-installation.md) 도 제거 후 실행 해야 합니다. Devenv.exe에 대 한 호출 모두 설치 및 제거에 대 한 InstallFinalize 표준 작업 바로 전에 발생 하기 때문에 두 경우 모두 사용자 지정 및 InstallExecuteSequence 테이블 항목에 사용 됩니다.  
  
> [!NOTE]
>  실행 `devenv /setup` MSI 패키지를 제거 합니다.  
  
 일반적으로 Windows Installer 패키지에 사용자 지정 작업을 추가 하는 경우를 처리 해야 해당 작업을 제거 및 롤백 중. 자동 VSPackage를 등록할 사용자 지정 작업을 추가 하는 경우 등록을 취소, 너무 사용자 지정 작업을 추가 해야 예를 들어 합니다.  
  
> [!NOTE]
>  사용자가 VSPackage를 설치 하 고 다음의 버전을 제거 하는 것이 불가능 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 와 통합 됩니다. 종속성을 사용 하 여 코드를 실행 하는 사용자 지정 작업을 제거 하 여 VSPackage의 제거 해당 상황에서 작동 하도록 할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="handling-launch-conditions-at-uninstall-time"></a>처리 시작 조건 제거  
 LaunchConditions 표준 작업 오류를 표시 하도록 시작 조건 테이블의 행을 읽고 조건에 경우 메시지입니다. 시작 조건을 일반적으로 시스템 요구 사항이 충족 되는 조건을 추가 하 여 시작 조건을 제거 하는 동안 일반적으로 건너뛸 수 있습니다, 않도록 하기 위해 사용 되 고 `NOT Installed`, 시작 조건 표의 LaunchConditions 행에 있습니다.  
  
 대신 추가 하는 `OR Installed` 를 제거 하는 동안 중요 하지 않은 조건을 시작 합니다. 하면 조건을 제거 하는 동안 true은 항상 시작 조건 오류 메시지 표시 되지 것입니다.  
  
> [!NOTE]
>  `Installed`VSPackage는 시스템에 이미 설치 되어 있는지를 감지할 때 설정 하는 Windows Installer 속성이입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Installer](http://msdn.microsoft.com/en-us/187d8965-c79d-4ecb-8689-10930fa8b3b5)   
 [시스템 요구 사항 검색](../../extensibility/internals/detecting-system-requirements.md)