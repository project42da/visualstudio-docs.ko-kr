---
title: "ClickOnce 및 응용 프로그램 설정 | Microsoft Docs"
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
helpviewer_keywords: ClickOnce deployment, application settings
ms.assetid: 891caba6-faef-4a3c-8f71-60e6fadb60eb
caps.latest.revision: "10"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 862f51aa7d124c3dbaa6514b666d74c26334e299
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clickonce-and-application-settings"></a>ClickOnce 및 응용 프로그램 설정
Windows Forms에 대 한 응용 프로그램 설정 하면 쉽게 만들고, 저장 및 사용자 지정 응용 프로그램과 사용자 기본 설정 클라이언트에서 유지 관리할 수 있습니다. 다음 문서에는 응용 프로그램 설정 파일 ClickOnce 응용 프로그램에서 작업 하는 방법 및 사용자는 다음 버전으로 업그레이드 하면 ClickOnce가 설정을 마이그레이션하 하는 방법을 설명 합니다.  
  
 기본 응용 프로그램 설정 공급자에만 적용 됩니다 아래 정보는 <xref:System.Configuration.LocalFileSettingsProvider> 클래스입니다. 사용자 지정 공급자를 제공 하는 경우 해당 공급자 버전 간에 설정 업그레이드 방법 및 해당 데이터 저장 방식을 결정 합니다. 응용 프로그램 설정 공급자에 대 한 자세한 내용은 참조 하십시오. [응용 프로그램 설정 아키텍처](/dotnet/framework/winforms/advanced/application-settings-architecture)합니다.  
  
## <a name="application-settings-files"></a>응용 프로그램 설정 파일  
 두 개의 파일을 사용 하는 응용 프로그램 설정: *앱*. user.config 및 exe.config로 바뀝니다 여기서 *앱* Windows Forms 응용 프로그램의 이름입니다. user.config 응용 프로그램 사용자 범위 설정을 저장 하는 클라이언트에 처음으로 만들어집니다. *응용 프로그램*..exe.config 이며 반면는 존재를 배포 하기 전에 설정에 대 한 기본값을 정의 하는 경우. Visual Studio는이 파일을 포함 자동으로 사용 하는 경우 해당 **게시** 명령입니다. 이 파일은 포함 되어 있는지 확인 해야 Mage.exe 나 MageUI.exe를 사용 하 여 ClickOnce 응용 프로그램을 만드는 경우 응용 프로그램 매니페스트를 채울 때 응용 프로그램의 다른 파일입니다.  
  
 ClickOnce를 사용 하는 응용 프로그램의 배포 되지 Windows Forms 응용 프로그램에서 *앱*..exe.config 파일 user.config 파일은 사용자의에 저장 하는 동안 응용 프로그램 디렉터리에 저장 됩니다 **Documents and Settings**  폴더입니다. ClickOnce 응용 프로그램에서 *앱*. exe.config로 바뀝니다의 ClickOnce 응용 프로그램 캐시 내에서 응용 프로그램 디렉터리의 위치와 해당 응용 프로그램에 대 한 ClickOnce 데이터 디렉터리에서 user.config를 유지 합니다.  
  
 응용 프로그램을 배포 하는 방법에 관계 없이 응용 프로그램 설정에 대 한 안전 읽기를 보장 *앱*..exe.config 이며 및 user.config에 대 한 안전 읽기/쓰기 액세스입니다.  
  
 ClickOnce 응용 프로그램에서는 응용 프로그램 설정에서 사용 하는 구성 파일의 크기는 ClickOnce 캐시의 크기에 따라 제한 됩니다. 자세한 내용은 참조 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)합니다.  
  
## <a name="version-upgrades"></a>버전 업그레이드  
 ClickOnce 응용 프로그램의 각 버전을 다른 모든 버전에서 격리와 마찬가지로 ClickOnce 응용 프로그램에 대 한 응용 프로그램 설정도 다른 버전에 대 한 설정을 격리 됩니다. 사용자와 응용 프로그램의 최신 버전으로 업그레이드 하는 경우 응용 프로그램 설정 업데이트 된 버전 및 설정 파일의 새로운 집합의 설정 병합와 함께 제공 된 설정에 대 한 최신 (가장 높은 번호) 버전의 설정을 비교 합니다.  
  
 다음 표에서 응용 프로그램 설정을 복사 하는 설정을 결정 하는 방법에 대해 설명 합니다.  
  
|변경 형식|업그레이드 동작|  
|--------------------|--------------------|  
|추가 된 설정 *앱*. exe.config로 바뀝니다|새 설정을 현재 버전의 파티션으로 병합 되며 병합 *앱*. exe.config로 바뀝니다|  
|설정에서 제거 *앱*. exe.config로 바뀝니다|현재 버전에서 이전 설정이 제거 될 *앱*. exe.config로 바뀝니다|  
|설정의 기본값이 변경 되었습니다. 로컬 설정 user.config에서 원래 기본으로 계속 설정|설정 값으로 새 기본과 최신 버전은 user.config에 병합 됩니다.|  
|설정의 기본값이 변경 되었습니다. 기본이 아닌에서 user.config 설정합니다.|설정 보존 기본이 아닌 값으로 최신 버전은 user.config에 병합 됩니다.|  
  
 사용자 고유의 응용 프로그램 설정 래퍼 클래스를 만든 하 고 업데이트 논리를 사용자 지정할 경우 재정의할 수 있습니다는 <xref:System.Configuration.ApplicationSettingsBase.Upgrade%2A> 메서드.  
  
## <a name="clickonce-and-roaming-settings"></a>ClickOnce 및 로밍 설정  
 ClickOnce 작동 하지 않습니다 로밍 설정을 사용 하 여 설정 파일을 네트워크의 컴퓨터 간에 따르도록 수 있도록 해줍니다. 로밍 설정을 해야 할 경우 네트워크를 통해 설정을 저장 하는 응용 프로그램 설정 공급자를 구현 하거나 원격 컴퓨터에서 설정을 저장 하기 위한 사용자 고유의 사용자 지정 설정 클래스를 개발 하 합니다. 설정 공급자에 대 한 자세한 내용은 참조 하십시오. [응용 프로그램 설정 아키텍처](/dotnet/framework/winforms/advanced/application-settings-architecture)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [응용 프로그램 설정 개요](/dotnet/framework/winforms/advanced/application-settings-overview)   
 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)   
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)