---
title: "Visual Studio Tools for Unity Azure Walkthrough 보안| Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: F4FD6E1C-EA64-4613-BDDE-6E4E5CCF983E
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 1ffb0c57329a8453208978cee69daa771d8ee0e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="update-unity-mono-security-certificate-store"></a>Unity Mono 보안 인증서 저장소 업데이트

Unity의 Mono에는 빈 인증서 저장소가 기본 제공되므로 어떠한 사이트로 신뢰하지 않습니다. [Mono 보안 FAQ](http://www.mono-project.com/docs/faq/security/)에서 자세히 읽어 보세요.

TLS/SSL를 무시하지 않고 Azure에 연결하려면 Unity Mono 인증서를 업데이트해야 합니다.

## <a name="using-mozroots-to-install-certificates"></a>mozroots를 사용하여 인증서 설치

mozroots 도구는 Mono에 포함되어 있습니다. Mozilla의 루트 인증서 목록을 다운로드하고 설치합니다.

1. 명령 프롬프트 터미널을 엽니다.

2. 터미널에서 **C:\Program Files\Unity\Editor\Data\MonoBleedingEdge\bin>** 디렉터리로 이동합니다. 정확한 위치는 로컬 시스템에서 Unity를 설치한 위치에 따라 다를 수 있습니다.

3. 다음 명령을 입력하고 **Enter** 키를 눌러 실행합니다.

  `mono ..\lib\mono\4.5\mozroots.exe --sync --import`

4. 다음과 같이 출력됩니다(추가된 번호 또는 인증서는 다를 수 있음).

  ```
  Downloading from 'https://hg.mozilla.org/releases/mozilla-release/raw-file/default/security/nss/lib/ckfw/builtins/certdata.txt'...
  Importing certificates into user store...
  1 new root certificates were added to your trust store.
  Import process completed.
  ```

5. 이제 TLS 관련 오류를 수신하지 않고 예제 프로젝트를 실행할 수 있습니다.

## <a name="next-step"></a>다음 단계

* [클라이언트 연결 테스트](visual-studio-tools-for-unity-azure-connection.md)
