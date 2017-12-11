---
title: "방화벽 또는 프록시 서버 뒤에 Visual Studio 설치 | Microsoft Docs"
description: 
ms.custom: 
ms.date: 08/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 4b203bbc3512ebc59a73a4e1420388a28fdf166b
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="install-visual-studio-behind-a-firewall-or-proxy-server"></a>방화벽 또는 프록시 서버 뒤에 Visual Studio 설치

Visual Studio 설치 관리자는 다양한 도메인 및 해당 다운로드 서버에서 파일을 다운로드합니다. 이 페이지에는 배포 스크립트에서 신뢰할 수 있는 도메인 URL을 “허용 목록”으로 나열합니다.

사용자 환경에 대해 가능한 경우 HTTP 및 HTTPS 프로토콜과 함께 다음 도메인을 추가해 보세요.

## <a name="microsoft-domains"></a>Microsoft 도메인
| 도메인 | 용도 |
| ------ | ------- |
| go.microsoft.com | 설치 URL 확인 |
| aka.ms | 설치 URL 확인 |
| download.visualstudio.microsoft.com | 설치 패키지 다운로드 위치 |
| download.microsoft.com | 설치 패키지 다운로드 위치 |
| download.visualstudio.com | 설치 패키지 다운로드 위치 |
| dl.xamarin.com | 설치 패키지 다운로드 위치 |
| visualstudiogallery.msdn.microsoft.com | Visual Studio 확장 다운로드 위치 |
| www.visualstudio.com | 문서 위치 |
| docs.microsoft.com | 문서 위치 |
| msdn.microsoft.com | 문서 위치 |
| www.microsoft.com | 문서 위치 |
| *.windows.net | 로그인 위치 |
| *.microsoftonline.com | 로그인 위치 |
| *.live.com | 로그인 위치 |


## <a name="non-microsoft-domains"></a>타사 도메인
| 도메인 | 이러한 워크로드 설치 |
| ------ | ------- |
| archive.apache.org |  JavaScript를 사용한 모바일 개발 <br />(Cordova) |
| cocos2d-x.org | C++를 사용한 게임 개발 <br />(Cocos) |
| download.epicgames.com | C++를 사용한 게임 개발 <br />(Unreal Engine) |
| download.oracle.com | JavaScript를 사용한 모바일 개발 <br />(Java SDK) <br /><br />.NET을 사용한 모바일 개발 <br />(Java SDK) |
| download.unity3d.com | Unity를 사용한 게임 개발 <br />(Unity) |
| netstorage.unity3d.com | Unity를 사용한 게임 개발 <br /> (Unity) |
| dl.google.com | JavaScript를 사용한 모바일 개발 <br />(Android SDK 및 NDK, 에뮬레이터) <br /><br />.NET을 사용한 모바일 개발 <br />(Android SDK 및 NDK, 에뮬레이터) |
| www.incredibuild.com | C++를 사용한 게임 개발 <br />(IncrediBuild) |
| incredibuildvs2017i.azureedge.net | C++를 사용한 게임 개발 <br />(IncrediBuild) |
| www.python.org | Python 개발 <br />(Python) <br /><br />데이터 과학 및 분석 응용 프로그램 <br />(Python) |

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지에서 문제 해결 팁을 참조하세요. 또한 Visual Studio IDE의 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 제품 문제를 보고하거나 [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 제안을 공유할 수 있습니다. [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다. [Gitter 커뮤니티](https://gitter.im/Microsoft/VisualStudio)([GitHub](https://github.com/) 계정 필요)의 Visual Studio 관련 대화를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.

## <a name="see-also"></a>참고 항목
* [Visual Studio 2017 설치](install-visual-studio.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)
  * [명령줄 매개 변수 예](command-line-parameter-examples.md)
  * [워크로드 및 구성 요소 ID 참조](workload-and-component-ids.md)
* [Visual Studio 2017의 네트워크 기반 설치 만들기](create-a-network-installation-of-visual-studio.md)
  * [Visual Studio 오프라인 설치에 필요한 인증서 설치](install-certificates-for-visual-studio-offline.md)
* [지시 파일을 사용하여 Visual Studio 설치 자동화](automated-installation-with-response-file.md)
* [Visual Studio를 배포할 때 제품 키를 자동으로 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Visual Studio 2017의 엔터프라이즈 배포에 대한 기본값 설정](set-defaults-for-enterprise-deployments.md)
* [패키지 캐시를 사용하지 않도록 설정 또는 이동](disable-or-move-the-package-cache.md)
* [Visual Studio의 네트워크 기반 설치 업데이트](update-a-network-installation-of-visual-studio.md)
* [Visual Studio 2017 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)
* [Visual Studio 인스턴스 검색 및 관리 도구](tools-for-managing-visual-studio-instances.md)
