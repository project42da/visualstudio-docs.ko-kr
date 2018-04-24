---
title: '방법: ClickOnce 배포 오류에 대 한 사용자 지정 로그 파일 위치를 설정 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- ClickOnce deployment, error logging
ms.assetid: 77424414-7f0e-4b99-94bb-ea130de92d09
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 647eed5145d9d80f9fc62249763726a5940a7345
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-set-a-custom-log-file-location-for-clickonce-deployment-errors"></a>방법: ClickOnce 배포 오류에 대한 사용자 지정 로그 파일 위치 설정
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 모든 배포에 대 한 정품 인증 로그 파일을 유지 관리합니다. 이러한 로그 문서를 설치 하 고 초기화 하는 모든 오류는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 합니다. 기본적으로 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 각 배포 활성화에 대해 하나의 로그 파일을 만듭니다. 이러한 로그 파일 임시 인터넷 파일 폴더에 저장합니다. 배포에 대 한 로그 파일 활성화 오류가 발생 하 고 사용자가 클릭할 때 사용자에 게 표시 됩니다 **세부 정보** 결과 오류 대화 상자에서 합니다.  
  
 레지스트리 편집기를 사용 하 여 특정 클라이언트에 대 한이 동작을 변경할 수 있습니다 (**regedit.exe**)를 사용자 지정 로그 파일 경로 설정 합니다. 이 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 활성화 성공 및 실패 한 모든 배포에 대 한 단일 파일에 기록 합니다.  
  
> [!CAUTION]
>  레지스트리 편집기를 잘못 사용 하면 운영 체제를 다시 설치 해야 하는 심각한 문제가 발생할 수 있습니다. 레지스트리 편집기를 사용할 때는 주의하세요.  
  
> [!NOTE]
>  자르거나에 너무 커지지 않도록 경우에 따라 로그 파일을 삭제 해야 합니다.  
  
 다음 절차에는 단일 클라이언트에 대 한 사용자 지정 로그 파일 위치를 설정 하는 방법을 설명 합니다.  
  
### <a name="to-set-a-custom-log-file-location"></a>사용자 지정 로그 파일 위치를 설정 하려면  
  
1.  열기 **Regedit.exe**합니다.  
  
2.  노드로 이동 `HKCU\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`합니다.  
  
3.  문자열 값으로 설정 `LogFilePath` 를 전체 경로 기본 사용자 지정 로그 위치의 파일 이름입니다.  
  
     이 위치는 사용자 쓰기 액세스 권한을 있는 디렉터리에 있어야 합니다. 예를 들어 Windows Vista에서 다음 폴더 구조를 만들고 설정 `LogFilePath` C:\Users를\\< 사용자 이름\>\Documents\Logs\ClickOnce\installation.log 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)