---
title: "/ResetSettings(devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/ResetSettings 스위치"
  - "Devenv, /ResetSettings 스위치"
  - "ResetSettings 스위치"
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /ResetSettings(devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기본 설정을 복원하고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE를 자동으로 시작합니다.  지정된 .vssettings 파일에 대한 설정을 선택적으로 다시 설정할 수 있습니다.  
  
 기본 설정은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가 처음 실행되었을 때 선택한 프로필에 의해 결정됩니다.  
  
## 구문  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## 인수  
 `SettingsFile`  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 적용할 .vssettings 파일의 전체 경로와 이름입니다.  
  
 일반 개발 설정 프로필을 복원하려면 `General`을 사용합니다.  
  
## 설명  
 `SettingsFile`가 지정되지 않은 경우 다음에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작하면 설정의 기본 컬렉션을 선택하라는 메시지가 나타납니다.  
  
## 예제  
 다음 명령줄은 `MySettings.vssettings` 파일에 저장된 설정을 적용합니다.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## 참고 항목  
 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)