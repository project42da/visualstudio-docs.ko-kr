---
title: "ClickOnce 캐시 개요 | Microsoft Docs"
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
  - "ClickOnce 응용 프로그램, 캐시"
  - "ClickOnce 배포, 캐시"
  - "Windows 응용 프로그램, ClickOnce 배포"
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 캐시 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 로컬로 설치되는지 온라인으로 호스팅되는지 여부와 상관없이 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]응용 프로그램 *캐시*의 클라이언트 컴퓨터에 저장됩니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 캐시는 현재 사용자의 Documents and Settings 폴더에서 Local Settings 디렉터리 아래의 숨겨진 디렉터리 집합입니다.  이 캐시에는 어셈블리, 구성 파일, 응용 프로그램 및 사용자 설정, 데이터 디렉터리 같은 응용 프로그램의 모든 파일이 보관됩니다.  이 캐시는 응용 프로그램의 데이터 디렉터리를 최신 버전으로 마이그레이션하는 데 사용되기도 합니다.  데이터 마이그레이션에 대한 자세한 내용은 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)를 참조하십시오.  
  
 응용 프로그램 저장소에 단일 장소를 제공함으로써 응용 프로그램의 실제 설치를 관리하는 작업을 사용자 대신 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 담당할 수 있습니다.  또한 이 캐시를 사용하면 모든 응용 프로그램과 개별 버전에 대한 어셈블리와 데이터 파일을 각각 분리하여 유지할 수 있으므로 응용 프로그램을 서로 격리하는 데 도움이 됩니다.  예를 들어 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 업그레이드하면 해당 버전 및 데이터 리소스가 캐시의 고유 디렉터리와 함께 제공됩니다.  
  
## 캐시 저장소 할당량  
 온라인으로 호스팅된 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에서 차지할 수 있는 공간의 크기는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 캐시의 크기를 제한하는 할당량으로 제한됩니다.  캐시 크기는 사용자의 모든 온라인 응용 프로그램에 적용됩니다. 부분적으로 신뢰할 수 있는 단일 온라인 응용 프로그램은 할당 공간의 반만 사용하도록 제한됩니다.  설치된 응용 프로그램은 캐시 크기에 의해 제한되지 않으며 캐시 제한 계산에 포함되지 않습니다.  모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 경우 캐시에는 현재 버전과 이전에 설치한 버전만 보존됩니다.  
  
 기본적으로 클라이언트 컴퓨터에는 온라인 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 저장소로 250MB가 할당됩니다.  데이터 파일은 이 제한 계산에 포함되지 않습니다.  시스템 관리자는 캐시 크기를 킬로바이트 단위로 표현하는 DWORD 값인 레지스트리 키 HKEY\_CURRENT\_USER\\Software\\Classes\\Software\\Microsoft\\Windows\\CurrentVersion\\Deployment\\OnlineAppQuotaInKB를 변경하여 특정 클라이언트 컴퓨터에서 이 할당량을 늘리거나 줄일 수 있습니다.  예를 들어 캐시 크기를 50MB로 줄이려면 이 값을 51200으로 변경합니다.  
  
## 참고 항목  
 [ClickOnce 응용 프로그램의 로컬 및 원격 데이터 액세스](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)