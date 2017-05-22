---
title: "오프라인 환경에서 Visual Studio 설치에 대한 특별 고려 사항 | Microsoft Docs"
description: '{{PLACEHOLDER}}'
ms.date: 05/09/2017
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 85576806818a6ed289c2f660f87b5c419016c600
ms.openlocfilehash: b596b6b6f9cff58525d253157534b6b990c68fcd
ms.contentlocale: ko-kr
ms.lasthandoff: 05/09/2017

---
# <a name="special-considerations-for-installing-visual-studio-in-an-offline-environment"></a>오프라인 환경에서 Visual Studio 설치에 대한 특별 고려 사항

Visual Studio는 많은 구성 요소가 정기적으로 업데이트되므로 주로 인터넷에 연결된 컴퓨터에서 설치하도록 설계되어 있습니다. 하지만 몇몇 추가 단계를 거치면 인터넷에 연결되지 않은 환경에 Visual Studio를 배포할 수 있습니다.

## <a name="create-a-network-installation-layout"></a>네트워크 설치 레이아웃 만들기
* 자세한 내용은 [Visual Studio의 네트워크 기반 설치 만들기](create-a-network-installation-of-visual-studio.md)를 참조하세요.

## <a name="install-certificates-needed-for-visual-studio-offline-installation"></a>Visual Studio 오프라인 설치에 필요한 인증서 설치
Visual Studio 설치 엔진은 신뢰할 수 있는 콘텐츠만 설치합니다.  다운로드되는 콘텐츠의 Authenticode 시그니처를 확인하고, 신뢰할 수 있는지 검증한 후 설치합니다.  인터넷에 연결된 컴퓨터에서는 파일 시그니처를 검증하는 데 필요한 모든 인증서를 자동으로 다운로드하여 설치합니다.  하지만 오프라인 환경 또는 인터넷 연결이 약한 시스템에서 운영하는 경우 이 작업이 가능하지 않을 수 있습니다.  해당 환경에 있는 사용자의 경우 필요한 인증서가 미리 설치되어 있는지 확인해야 합니다.  이러한 인증서는 실행 중인 컴퓨터에서 오프라인 설치를 만들 때 “certificates” 폴더로 다운로드됩니다.

수동으로 인증서 파일을 두 번 클릭하고 인증서 관리자 마법사를 클릭하여 인증서를 클라이언트에 설치할 수 있습니다. 암호를 묻는 메시지가 표시되면 비워 두세요.

인증서 설치를 스크립팅하려면 다음 단계를 수행합니다.

1. certmgr.exe를 설치 공유로 복사합니다(예: `\server\share\vs2017`). `certmgr.exe`는 _유니버설 Windows 플랫폼 개발_ 워크로드의 선택적 구성 요소로 설치될 수 있는 Windows SDK와 함께 제공됩니다. (예: `"C:\Program Files (x86)\Windows Kits\10\bin\x86\certmgr.exe"`)

2. 다음 명령으로 배치 파일을 만듭니다.

```cmd
\\server\share\vs2017\certmgr.exe -add -c \\server\share\vs2017\certificates\manifestSignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

\\server\share\vs2017\certmgr.exe -add -c \\server\share\vs2017\certificates\manifestSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

\\server\share\vs2017\certmgr.exe -add -c \\server\share\vs2017\certificates\manifestCounterSignCertificates.p12 -n "Microsoft Time-Stamp PCA" -s -r LocalMachine CA

\\server\share\vs2017\certmgr.exe -add -c \\server\share\vs2017\certificates\manifestCounterSignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root

\\server\share\vs2017\certmgr.exe -add -c \\server\share\vs2017\certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Code Signing PCA" -s -r LocalMachine CA

\\server\share\vs2017\certmgr.exe -add -c \\server\share\vs2017\certificates\vs_installer_opc.SignCertificates.p12 -n "Microsoft Root Certificate Authority" -s -r LocalMachine root
```

3. 관리자 명령 셸 또는 관리자 권한 프로세스를 통해 클라이언트에서 배치 파일을 실행합니다.

### <a name="why-are-the-certificates-from-the-certificates-folder-not-installed-automatically"></a>`certificates` 폴더의 인증서가 자동으로 설치되지 않는 이유는 무엇인가요?
시그니처가 온라인 환경에서 검증되면 Windows API를 사용하여 인증서를 다운로드하고 시스템에 추가합니다. 인증서가 신뢰할 수 있고 관리 설정을 통해 허용되는지에 대한 검증이 이 프로세스 중에 수행됩니다. 대부분의 오프라인 환경에서는 이 검증 프로세스를 수행할 수 없습니다. 인증서를 수동으로 설치하면 사용자는 인증서가 신뢰할 수 있고 관리자 요구 사항을 충족하는지 확인할 수 있습니다.

## <a name="install-visual-studio"></a>Visual Studio 설치
인증서가 설치되면 [여기에 제공된 지침](create-a-network-installation-of-visual-studio.md#deploying-from-a-network-installation)을 사용하여 추가적인 특별 단계 없이 Visual Studio 배포를 오프라인에서 진행할 수 있습니다.


## <a name="see-also"></a>참고 항목
* [Visual Studio 설치](install-visual-studio.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
* [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)

