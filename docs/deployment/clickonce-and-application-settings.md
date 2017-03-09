---
title: "ClickOnce 및 응용 프로그램 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "ClickOnce 배포, 응용 프로그램 설정"
ms.assetid: 891caba6-faef-4a3c-8f71-60e6fadb60eb
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 및 응용 프로그램 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Windows Forms의 응용 프로그램 설정을 사용하면 클라이언트에서 사용자 지정 응용 프로그램과 사용자 기본 설정을 쉽게 만들고 저장하고 유지 관리할 수 있습니다.  다음 문서에서는 ClickOnce 응용 프로그램에서 응용 프로그램 설정 파일이 작동하는 방식 및 사용자가 다음 버전으로 업그레이드할 때 ClickOnce가 설정을 마이그레이션하는 방법에 대해 설명합니다.  
  
 다음 정보는 기본 응용 프로그램 설정 공급자 <xref:System.Configuration.LocalFileSettingsProvider> 클래스에만 적용됩니다.  사용자 지정 공급자를 제공하면 해당 공급자가 데이터 저장 방법과 버전 간 설정 업그레이드 방법을 결정합니다.  응용 프로그램 설정 공급자에 대한 자세한 내용은 [응용 프로그램 설정 아키텍처](../Topic/Application%20Settings%20Architecture.md)를 참조하십시오.  
  
## 응용 프로그램 설정 파일  
 응용 프로그램 설정에는 *app*.exe.config와 user.config라는 두 개의 파일이 사용됩니다. 여기서 *app*는 Windows Forms 응용 프로그램의 이름입니다.  user.config는 응용 프로그램에서 사용자 범위 설정을 처음 저장할 때 클라이언트에 만들어집니다.  이와 달리 *app*.exe.config는 설정의 기본값을 정의하는 경우 배포 전에 이미 존재합니다.  Visual Studio는 **게시** 명령을 사용할 때 이 파일을 자동으로 포함합니다.  Mage.exe 또는 MageUI.exe를 사용하여 ClickOnce 응용 프로그램을 만들 경우 응용 프로그램 매니페스트를 채울 때 이 파일이 응용 프로그램의 다른 파일과 함께 포함되어 있는지 확인해야 합니다.  
  
 ClickOnce를 통해 배포되지 않은 Windows Forms 응용 프로그램에서는 응용 프로그램의 *app*.exe.config 파일이 응용 프로그램 디렉터리에 저장되지만 user.config 파일은 사용자의 **Documents and Settings** 폴더에 저장됩니다.  ClickOnce 응용 프로그램에서는 *app*.exe.config가 ClickOnce 응용 프로그램 캐시 내의 응용 프로그램 디렉터리에 있고 user.config는 해당 응용 프로그램의 ClickOnce 데이터 디렉터리에 있습니다.  
  
 응용 프로그램을 배포하는 방법에 관계없이 응용 프로그램 설정은 *app*.exe.config에 대한 안전한 읽기 권한 및 user.config에 대한 안전한 읽기\/쓰기 권한을 보장합니다.  
  
 ClickOnce 응용 프로그램에서 응용 프로그램 설정에 사용되는 구성 파일 크기는 ClickOnce 캐시 크기에 의해 제한됩니다.  자세한 내용은 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)를 참조하십시오.  
  
## 버전 업그레이드  
 ClickOnce 응용 프로그램의 각 버전이 다른 모든 버전에서 격리되는 것과 같이 ClickOnce 응용 프로그램의 응용 프로그램 설정도 다른 버전의 설정에서 격리됩니다.  사용자가 응용 프로그램의 이후 버전으로 업그레이드하면 응용 프로그램 설정은 가장 최근\(번호가 가장 큰\) 버전의 설정과 업데이트된 버전에서 제공된 설정을 비교하고 해당 설정을 새 설정 파일 집합으로 병합합니다.  
  
 다음 표에서는 응용 프로그램 설정에서 복사할 설정을 결정하는 방법에 대해 설명합니다.  
  
|변경 형식|업그레이드 동작|  
|-----------|--------------|  
|*app*.exe.config에 추가된 설정|새 설정은 현재 버전의 *app*.exe.config로 병합됨|  
|*app*.exe.config에서 제거된 설정|이전 설정은 현재 버전의 *app*.exe.config에서 제거됨|  
|설정의 기본값이 변경되며 로컬 설정은 계속 user.config의 원래 기본값으로 설정됨|설정이 새 기본값을 값으로 사용하여 현재 버전의 user.config로 병합됨|  
|설정의 기본값이 변경되며 설정이 user.config에서 기본값이 아닌 값으로 설정됨|설정이 기본값이 아닌 값을 유지하여 현재 버전의 user.config로 병합됨|  
  
 고유의 응용 프로그램 설정 래퍼 클래스를 만들었고 업데이트 논리를 사용자 지정하려면 <xref:System.Configuration.ApplicationSettingsBase.Upgrade%2A> 메서드를 재정의하면 됩니다.  
  
## ClickOnce 및 로밍 설정  
 ClickOnce는 설정 파일이 네트워크에 있는 시스템 전체에서 사용자의 설정 파일을 따르도록 하는 로밍 설정과 함께 작동하지 않습니다.  로밍 설정이 필요한 경우에는 네트워크를 통해 설정을 저장하는 응용 프로그램 설정 공급자를 구현하거나 원격 컴퓨터에 설정을 저장하는 사용자 지정 설정 클래스를 개발해야 합니다.  설정 공급자에 대한 자세한 내용은 [응용 프로그램 설정 아키텍처](../Topic/Application%20Settings%20Architecture.md)를 참조하십시오.  
  
## 참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [응용 프로그램 설정 개요](../Topic/Application%20Settings%20Overview.md)   
 [ClickOnce 캐시 개요](../deployment/clickonce-cache-overview.md)   
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)