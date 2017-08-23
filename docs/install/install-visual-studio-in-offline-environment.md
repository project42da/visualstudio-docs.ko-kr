---
title: "오프라인 환경에서 Visual Studio 설치에 대한 특별 고려 사항 | Microsoft Docs"
description: '{{PLACEHOLDER}}'
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '{{PLACEHOLDER}}'
- '{{PLACEHOLDER}}'
ms.assetid: 9750A3F3-89C7-4A8F-BA75-B0B06BD772C2
author: timsneath
ms.author: tims
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f23906933add1f4706d8786b2950fb3b5d2e6781
ms.openlocfilehash: 62fc2d38a628cfc28913a0a45e1e3cb5d3852330
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="special-considerations-for-installing-visual-studio-in-an-offline-environment"></a>오프라인 환경에서 Visual Studio 설치에 대한 특별 고려 사항

Visual Studio는 많은 구성 요소가 정기적으로 업데이트되므로 주로 인터넷에 연결된 컴퓨터에서 설치하도록 설계되어 있습니다. 하지만 몇몇 추가 단계를 거치면 인터넷에 연결되지 않은 환경에 Visual Studio를 배포할 수 있습니다.

## <a name="install-certificates-needed-for-visual-studio-offline-installation"></a>Visual Studio 오프라인 설치에 필요한 인증서 설치
Visual Studio 설치 엔진은 신뢰할 수 있는 콘텐츠만 설치합니다. 이렇게 하려면 다운로드되는 콘텐츠의 Authenticode 시그니처를 확인하고 모든 콘텐츠를 신뢰할 수 있는지 검증한 후 설치합니다. 그러면 다운로드 위치를 손상시키는 공격으로부터 환경을 보호할 수 있습니다. 따라서 Visual Studio를 설치하려면 여러 표준 Microsoft 루트 및 중간 인증서가 사용자 컴퓨터에 설치되고 최신 상태로 유지되어야 합니다. 컴퓨터가 Windows 업데이트를 통해 최신 상태로 유지된 경우 서명 인증서가 자동으로 업데이트되며 설치하는 동안 Visual Studio가 필요에 따라 인증서를 새로 고쳐 파일 시그니처를 확인합니다.

최신 루트 인증서가 없는 오프라인 컴퓨터가 있는 엔터프라이즈의 경우 관리자는 [신뢰할 수 있는 루트 및 허용되지 않는 인증서 구성](https://technet.microsoft.com/en-us/library/dn265983.aspx) 페이지의 지침에 따라 인증서를 업데이트할 수 있습니다. 또는 네트워크 레이아웃을 만들 때 필요한 인증서가 `certificates` 폴더로 다운로드됩니다. 그러면 인증서 파일을 두 번 클릭하고 인증서 관리자 마법사를 통해 클릭하여 인증서를 수동으로 설치할 수 있습니다. 암호를 묻는 메시지가 표시되면 비워 두세요.

오프라인 환경에서 클라이언트 워크스테이션에 대한 Visual Studio 배포를 스크립팅할 경우 다음 단계를 수행해야 합니다.

1. [인증서 관리자 도구](https://msdn.microsoft.com/en-us/library/e78byta0.aspx)(`certmgr.exe`)를 설치 공유(예: `\\server\share\vs2017`)로 복사합니다. `certmgr.exe`는 Windows 자치의 일부로 포함되지 않지만 [Windows SDK](https://developer.microsoft.com/en-US/windows/downloads/windows-10-sdk)의 일부로 사용할 수 있습니다.

2. 다음 명령으로 배치 파일을 만듭니다.

   ```cmd
   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA 2011" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA 2010" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

   certmgr.exe -add -c certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
   ```

3. 일괄 처리 파일을 클라이언트에 배포합니다. 이 명령은 관리자 권한 프로세스에서 실행되어야 합니다.

### <a name="what-are-the-certificates-files-in-the-certificates-folder"></a>`certificates` 폴더에서 인증서 파일이란 무엇인가요?
이 폴더에 있는 세 개의 `.p12` 파일에는 각각 중간 인증서 및 루트 인증서가 포함됩니다. Windows 업데이트로 최신 상태가 유지되는 시스템은 대부분 이러한 인증서가 이미 설치되어 있습니다.

* `ManifestSignCertificates.p12`에는 다음이 포함됩니다.
    * 중간 인증서: **Microsoft Code Signing PCA 2011**
        * 필요하지 않음. 일부 시나리오(있는 경우)에서 성능을 향상합니다.
    * 루트 인증서: **Microsoft Root Certificate Authority 2011**
        * 최신 Windows 업데이트가 설치되지 않은 Windows 7 서비스 팩 1 시스템에 필요합니다.
* `ManifestCounterSignCertificates.p12`
    * 중간 인증서: **Microsoft Time-Stamp PCA 2010**
        * 필요하지 않음. 일부 시나리오(있는 경우)에서 성능을 향상합니다.
    * 루트 인증서: **Microsoft Root Certificate Authority 2010**
        * 최신 Windows 업데이트가 설치되지 않은 Windows 7 서비스 팩 1 시스템에 필요합니다.
* `vs_installer_opc.SignCertificates.p12`
    * 중간 인증서: **Microsoft Code Signing PCA**
        * 모든 시스템에 필요합니다. Windows 업데이트의 모든 업데이트가 적용된 시스템에는 이 인증서가 없을 수 있습니다.
    * 루트 인증서: **Microsoft Root Certificate Authority**
        * 필수 요소. 이 인증서는 Windows 7 이상을 실행하는 시스템과 함께 제공됩니다.

### <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>`certificates` 폴더의 인증서가 자동으로 설치되지 않는 이유는 무엇인가요?
시그니처가 온라인 환경에서 검증되면 Windows API를 사용하여 인증서를 다운로드하고 시스템에 추가합니다. 인증서가 신뢰할 수 있고 관리 설정을 통해 허용되는지에 대한 검증이 이 프로세스 중에 수행됩니다. 대부분의 오프라인 환경에서는 이 검증 프로세스를 수행할 수 없습니다. 인증서를 수동으로 설치하면 엔터프라이즈 관리자는 인증서가 신뢰할 수 있고 조직의 보안 정책을 충족하는지 확인할 수 있습니다.

### <a name="checking-if-certificates-are-already-installed"></a>인증서가 설치되어 있는지 확인
설치하는 시스템을 확인할 한 가지 방법은 다음 단계를 수행하는 것입니다.
1. `mmc.exe`를 실행합니다.<br/>
  a. 파일을 클릭한 다음 **스냅인 추가/제거**를 선택합니다.<br/>
  b. **인증서**를 두 번 클릭하고, **컴퓨터 계정**을 선택하고 **다음**을 클릭합니다.<br/>
  c. **로컬 컴퓨터**를 선택하고, **마침**을 클릭하고, **확인**을 클릭합니다.<br/>
  d. **인증서(로컬 컴퓨터)**를 확장합니다.<br/>
  e. **신뢰할 수 있는 루트 인증 기관**을 확장하고 **인증서**를 선택합니다.<br/>
    * 이 목록에서 필요한 루트 인증서를 확인합니다.<br/>
  
   f. **중간 인증 기관**을 확장하고 **인증서**를 선택합니다.<br/>
    * 이 목록에서 필요한 중간 인증서를 확인합니다.<br/>

2. 파일을 클릭하고 **스냅인 추가/제거**를 선택합니다.<br/>
  a. **인증서**를 두 번 클릭하고, **내 사용자 계정**을 선택하고, **마침**, **확인**을 차례로 클릭합니다.<br/>
  b. **인증서 – 현재 사용자**를 확장합니다.<br/>
  c. **중간 인증 기관**을 확장하고 **인증서**를 선택합니다.<br/>
    * 이 목록에서 필요한 중간 인증서를 확인합니다.<br/>

인증서 이름이 **발급 대상** 열에 없는 경우 이러한 인증서를 설치해야 합니다.  중간 인증서가 **현재 사용자** 중간 인증서 저장소에만 있는 경우에는 로그인한 사용자만 해당 인증서를 사용할 수 있고 다른 사용자를 위해 인증서를 설치해야 할 수 있습니다.

## <a name="install-visual-studio"></a>Visual Studio 설치
인증서를 설치한 후에는 “Visual Studio의 네트워크 설치 만들기” 페이지의 [네트워크 설치에서 배포]((create-a-network-installation-of-visual-studio.md#deploying-from-a-network-installation) 섹션에 있는 지침에 따라 특별한 추가 단계 없이 Visual Studio 배포를 오프라인으로 계속 진행할 수 있습니다.


## <a name="see-also"></a>참고 항목
* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)

