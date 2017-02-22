---
title: "방법: ClickOnce 배포 오류에 대한 사용자 지정 로그 파일 위치 설정 | Microsoft Docs"
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
  - "ClickOnce 배포, 오류 로깅"
  - "ClickOnce 배포, 문제 해결"
  - "ClickOnce 배포 문제 해결"
ms.assetid: 77424414-7f0e-4b99-94bb-ea130de92d09
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: ClickOnce 배포 오류에 대한 사용자 지정 로그 파일 위치 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 모든 배포의 활성화 로그 파일을 유지 관리합니다.  이러한 로그에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포의 설치 및 초기화와 관련된 오류가 기록됩니다.  기본적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 배포가 활성화될 때마다 로그 파일이 하나씩 만들어집니다.  이러한 로그 파일은 임시 인터넷 파일 폴더에 저장됩니다.  활성화 오류가 발생할 때 나타나는 오류 대화 상자에서 **자세히**를 클릭하면 배포에 대한 로그 파일이 표시됩니다.  
  
 레지스트리 편집기\(**regedit.exe**\)에서 사용자 지정 로그 파일 경로를 설정하여 특정 클라이언트에 대해 이 동작을 변경할 수 있습니다.  이 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 모든 배포에 대한 활성화 성공 및 실패 정보를 한 파일에 기록합니다.  
  
> [!CAUTION]
>  레지스트리 편집기를 잘못 사용하면 심각한 문제가 발생하여 운영 체제를 다시 설치해야 할 수도 있습니다.  레지스트리 편집기를 사용할 때는 주의하십시오.  
  
> [!NOTE]
>  로그 파일이 너무 커지지 않도록 로그 파일을 가끔씩 자르거나 삭제해야 합니다.  
  
 다음 절차에서는 단일 클라이언트에 대해 사용자 지정 로그 파일의 위치를 설정하는 방법을 설명합니다.  
  
### 사용자 지정 로그 파일의 위치를 설정하려면  
  
1.  **Regedit.exe**를 엽니다.  
  
2.  `HKCU\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment` 노드로 이동합니다.  
  
3.  문자열 값 `LogFilePath`를 기본 사용자 지정 로그 위치의 전체 경로와 파일 이름으로 설정합니다.  
  
     사용자가 쓸 수 있는 권한이 있는 디렉터리 내의 경로로 설정해야 합니다.  예를 들어 Windows Vista에서는 C:\\Users\\\<username\>\\Documents\\Logs\\ClickOnce\\installation.log 폴더 구조를 만들고 `LogFilePath`를 이 폴더 구조로 설정합니다.  
  
## 참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)